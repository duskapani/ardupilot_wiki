# GELİŞMİŞ FAILSAFE YAPILANDIRMASI 

> flight termination: uçuş sonlandırma

Temel failsafe işlevselliği, RTL'e dayanmaktadır. Uçak yer istasyonu ile temasını veya RC kontrolünü kaybederse, RTL başlatabilir. Bu, çoğu kullanıcı için iyidir, ancak bazı durumlarda daha gelişmiş failsafe özellikleri gerekir. Gelişmiş Failsafe ayarlarının amacı budur. Yarışma haricindede çok faydalı olabilirler.


## Arkaplan

Outback Chanllenge yarışması için uçaklara uygun gelişmiş failsafe ayarları eklendi ve özellikler yarışma kurallarına uyacak şekilde tasarlandı. Normalde failsafe, pilot tarafından kontrolün kaybedilmesi durumunda uçağın kurtarılmasına yönelik iken, OBC kurallarında daha çok belirli bir hava sahasında güvenli çalışmanın sağlanmasına yöneliktir. Bu, gelişmiş failsafe ayarlarının, coğrafi bir sınır ve maksimum irtifa ile tanımlanan hava sahası dışına çıkmaması için ayarlandığı anlamına gelir


## Göreve Dayalı

Normal failsafe ve gelişmiş failsafe (AFS) arasındaki temel fark, AFS seçeneklerinin göreve dayalı olmasıdır. Failsafe seçeneği gerçekleştiğinde, AFS seçenekleri uçağın geçeceği görevde bir waypoint numarası belirtir. Bu, pilotun failsafe bir olay gerçekleştiğinde yapacağı bir dizi kompleks eylemi yapılandırmasına olanak tanır - uçak görevi olarak yapılabilen her şey failsafe olaylarda gerçekleştirilebilir.

Tipik olarak bir pilot, AFS seçeneklerini failsafe koşullar için kurar, böylece uçak bir süre mevcut konumunda loiter yapar ve daha sonra önceden belirlenmiş uçuş yolu ile ev konumuna döner. Ayrıca, hava süratindeki değişiklikleri, irtifa değişikliklerini, otomatik inişi veya bir görevde programlanabilecek herhangi bir şey içerebilir. Failse olayı sona ererse (örn. GPS kilidi geri kazanılırsa), uçak daha önce uçmakta olduğu görev öğesine geri döner ve göreve devam eder.

Bu, AFS seçeneklerini yalnızca AUTO görevler için gerçekten verimli kılar. Birincil olarak CRUISE modunda veya diğer modlarda uçuyorsanız, standart failsafe ayarlarını kullanmalısınız.


## AFS Failsafe Sistemini Etkinleştirme

AFS failsafe sistemini etkinleştirmek için [AFS_ENABLE]() parametresini 1 olarak ayarlamanız gerekir. Varsayılan değer 0, diğer bir deyişle tüm diğer seçenekler devre dışı.

AFS sisteminin yalnızca PX4 ve Pixhawk gibi daha yüksek teknolojili  otopilot kartlarında varsayılan olarak içine konulduğuna dikkat edin.


## AFS Sonlandırma

"Uçuş sonlandırma" kavramı, AFS failsafe sistemini anlamanın anahtar noktasıdır. Sonlandırma, tüm kontrol yüzeylerini maksimuma ve dönüşe girmek için throttle'ı 0 ayarlayarak uçağın bilinçli şekilde yere daldığı yerdir.

AFS sistemi yalnızca [AFS_TERM_ACTION]() sihirli 42 değerine ayarlanmışsa sonlandırmaya başlayacaktır. Diğer herhangi bir değer için AFS sistemi YKİ konsolundan sonlandırmak istediğini belirten bir mesaj yazacaktır ancak kontrol yüzeylerini hiç değiştirmeyecektir. 42'den farklı bir değer kullanmak, uçağın failsafe bir olayda sonlandırılmasını istemediğiniz deneme uçuşlarında yararlıdır.

[AFS_TERM_ACTION]() 42 olarak ayarlanmamışsa, diğer normal failsafe kodların hala etkindir, örneğin etkin bir coğrafi sınırlandırma etkinleştirilmişse uçağın coğrafi sınırlandırma dönüş noktasına geri uçacağını unutmayın.

Etkinleştirildiğinde, AFS sonlandırma sistemi ayrıca, ana FMU mikrodenetleyicisi ile IO mikrodenetleyicisi arasında iletişim kesilirse, örneğin uçuş yazılımı çökerse, uçağın sonlandırılması için Pixhawk otopilotundaki ikincil IO mikrokontrolcüsünü de ayarlar.
 
Bir AFS uçuş sonlandırması kurtarılamaz. Uçağınız bir sonlandırmaya başladığında, kurtarmanın yolu yoktur.

## Failsafe Olay Tipleri

AFS failsafe sistemi beş tip failsafe olayını destekler:

- coğrafi sınırlandırma ihlali
- maksimum basınç irtifası ihlali
- GPS kaybı
- Yer istasyonuyla iletişim kaybı
- barometre arızası

Bu tip arızaların her birinin, aşağıda açıklanan kendine özgü çözüm şekli vardır.


### Coğrafi sınırlandırma ihlali

Coğrafi sınırlandırma etkinleştirilirse, AFS failsafe modülü, uçakları coğrafi sınır ihlali (ve eğer ayarlanmışsa coğrafi sınırlandırma alt ve üst irtifalarını) için izler. İhlal olursa, AFS sistemi derhal uçuşu sonlandırır (yukarıdaki sonlandırma konusuna bakın).


### Maksimum basınç irtifası ihlali

Hava sahasını diğer uçaklarla paylaşırken, mevcut uçuş irtifalarını ortak bir referans basıncı, genelde QNH (referans olarak “deniz yüksekliği"), olarak tanımlamak olağan bir uygulamadır. Milibar cinsinden ölçülen QNH referans basıncı, bir radyo mesajı ya da havacılık internet ve hava durumu siteleri aracılığıyla tüm uçaklara dağıtılmaktadır.

Hava aracı daha sonra bu QNH basıncına göre basıncı ölçmek için barometreleri kullanır ve bu, bölgedeki tüm uçakların kullanması gereken bir irtifa referansı verir.

AFS sistemi, [AFS_QNH_PRESSURE]() parametresindeki QNH basıncını milibar cinsinden bir değer olarak ayarlayarak bir basınç irtifa limiti uygulayabilir. Pilot daha sonra AFS_AMSL_LIMIT parametresini (metre cinsinden) kullanarak bir basınç yükseklik limiti belirlemelidir. Bu basınç yükseklik sınırının deniz seviyesine göre olduğuna dikkat edin (AMSL, “ortalama deniz seviyesinin üstünde” anlamına gelir).

Bu parametrelerin her ikisi de ayarlanmışsa, AFS sistemi basınç irtifasını izler ve [AFS_AMSL_LIMIT]()'in üstüne çıkarsa bir sonlandırma başlatır.

QNH basıncı farklı günlerde çok farklı olabileceğinden, uçuş gününüzdeki yerel hava şartları için doğru [AFS_QNH_PRESSURE]() ayarını yaparken çok dikkatli olmanız gerekir.

QNH basınç sınırına ek olarak, AFS sistemi barometrenizin sağlığını da izler. Barometre 5 saniyeliğine sağlıksızsa AFS sistemi [AFS_AMSL_ERR_GPS]() parametresini kontrol eder. Eğer -1 ise (varsayılan) uçak derhal sonlandırılır. -1 değilse, AFS sistemi AFS_AMSL_ERR_GPS değerini tolerans olarak GPS yüksekliğine eklemek için kullanır ve GPS irtifası artı AFS_AMSL_ERR_GPS değeri (metre cinsinden) AFS_AMSL_LIMIT değerinin altında olması durumunda uçuşun devam etmesine izin verir. Bu toleransın amacı GPS irtifalarının yanlışlığını hesaba katmaktır. AFS_AMSL_LIMIT basınç irtifasının ihlal edilmemesini sağlamak için güvenlik değeri olarak 200 makuldur.
 

### GPS kaybı

AFS sistemi, uçuş boyunca GPS alıcılarınızın sağlığını izler. Kullanılabilir tüm GPS alıcılarınız konum kilidini kaybederse, bu GPS arıza failsafe'ini başlatır.

GPS arızası meydana geldiğinde (3 saniye boyunca GPS kilidinin kaybı olarak tanımlanır) AFS sistemi [AFS_WP_GPS_LOSS]() parametresine bakar. Bu parametre, bir GPS arızası meydana geldiğinde kullanmak için görevinizde bir waypoint numarası belirtir. AFS_WP_GPS_LOSS sıfır değilse, uçak mevcut waypointi AFS_WP_GPS_LOSS içinde belirtilen waypoint numarasıyla değiştirir. Görevinizi, uçağın GPS kaybında ne tür bir eylem eylem gerçekleştireceğine ayarlamalısınız. Örneğin, 10 numaradan başlayan, önce 30 saniye loiter yapan daha sonra hava alanına doğru ilerleyen bir waypoint olabilir. Daha sonra GPS kilidi kaybı görevinin bu kısmını etkinleştirmek için AFS_WP_GPS_LOSS değerini 10 ayarlayın.

GPS kilidi için görev öğeleri ayarlarken bazen "geçerli konumda loiter" waypointlerini dahil etmek yararlı olabilir. LOITER görev komutlarınını hem enlem hem boylamlarını sıfıra ayarlayarak elde edilir.

Eğer bir GPS arızası başladıktan sonra GPS kurtarılırsa, uçak otomatik olarak bıraktığı yerdeki görevine devam eder.

GPS kaybı süresince yer istasyonuyla olan haberleşmede kaybedilirse, buna "çifte kayıp" denir ve uçak sonlandırılır.

AFS_MAX_GPS_LOSS sıfır harici bir sayıya ayarlanırsa, GPS kilidi yeniden tesis edildikten sonra göreve dönerken izin verilecek maksimum GPS arıza sayısı olarak kullanılır. Bu sayaç yalnızca 2. GPS arızasını öncekinden en az 30 saniye sonra meydana gelirse artar.

### Ground station communications loss
The AFS system monitors the health of the link between your ground station and your aircraft. It does this by looking for HEARTBEAT MAVLink messages coming from the ground station.

If the aircraft does not receive a HEARTBEAT message for a period of 10 seconds then it enters a GCS failsafe state. It then looks for a AFS_WP_COMMS parameter, and if that is non-zero it will change the current target waypoint to the one given in AFS_WP_COMMS. You should set up a section of your mission with whatever actions you want to take on loss of communications.

If GPS lock is lost at the same time as GCS communications is lost then that is considered a “dual loss”, and the aircraft will immediately terminate.

Note that the monitoring of HEARTBEAT messages only tells the autopilot that it can see messages from the ground station. It does not mean the ground station can see messages from the aircraft. So it is quite possible for your ground station to be reporting loss of communication while the aircraft is still receiving HEARTBEAT messages.

If AFS_MAX_COM_LOSS is set to a non-zero number, then it is used as a maximum count of the number of communication failures that will be allowed while returning to the mission after communications is re-established. This counter is only incremented if the 2nd comms failure happens at least 30 seconds after the previous one (to account for a short period of communications failure).

### RC Loss
If RC control is lost in a manual control mode for more than AFS_RC_FAIL_MS milliseconds, flight termination is activated. This termination mode is only enabled if AFS_RC_FAIL_MS is non-zero. For the OBC rules it should be set to 1500 (giving 1.5 seconds).

Monitoring the AFS system
The AFS system provides some additional parameters to make it easier to monitor the health of the failsafe system using external electronics (such as an external failsafe board).

The key parameters are:

AFS_TERM_PIN: This is a digital pin which is set to a high voltage if termination is started. Note that this pin will go high on termination even if the AFS_TERM_ACTION parameter is not set to 42.
AFS_HB_PIN: This is a digital pin number for a pin which is toggled at a rate of 10Hz by the failsafe system. If termination occurs and a AFS_TERM_PIN value is not set then the heartbeat pin will stop toggling.
AFS_MAN_PIN: This is a digital pin number for a pin which goes high when the aircraft is in MANUAL mode. It may be useful with some external failsafe boards to detect manual mode and behave differently.
Manual Termination
Apart from automatic termination it is also important for the aircrafts operator to be able to terminate the aircraft immediately if they think the aircraft is a danger to people or other aircraft. To force an immediate termination you should use the AFS_TERMINATION parameter. By setting that parameter to 1 the aircraft will immediately terminate.

Example AFS failsafe mission
Setting up a AFS failsafe mission takes time, and needs to be done very carefully. To help you understand what is possible you may find the following example files useful

A waypoint mission for the 2014 Outback Challenge with waypoints for different AFS failures commented in the file
A geofence file for the 2014 Outback Challenge
Testing the AFS system in SITL
It is highly recommended that you extensively test the AFS system using the SITL simulation system before using it on a real aircraft. You can simulate all types of in-flight failures using the SIM_ parameters. To start SITL in Kingaroy ready for OBC testing you would use:

sim_vehicle.py -L Kingaroy --console --map
The key parameters for failsafe testing in SITL are:

Test GPS failure: param set SIM_GPS_DISABLE 1
Test RC failure: param set SIM_RC_FAIL 1
Test comms failure: set heartbeat 0
Test fence failure: switch to CRUISE mode and fly across boundary
Test QNH failure: param set AFS_AMSL_LIMIT 100
Additional tips for AFS failsafe users
You need to ensure that your geofence is enabled before takeoff. This can either be done as part of your preflight checklist, or you could set a FENCE_CHANNEL and enable it from within your transmitter. This ensures that if your transmitter is out of range that the fence remains enabled.

Settings for Outback Challenge 2014
To be compliant with the OBC 2014 rules you should have the following settings:

AFS_ENABLE: 1
AFS_WP_COMMS: waypoint number for OBC comms hold followed by two minute loiter, then return to airfield home
AFS_WP_GPS_LOSS: waypoint number to loiter in place for 30 seconds, followed by return to airfield home
AFS_TERM_ACTION: 42
AFS_AMSL_LIMIT: 914
AFS_QNH_PRESSURE: correct QNH pressure for the day
AFS_RC_FAIL_MS: 1500
AFS_MAX_GPS_LOSS: 2
AFS_MAX_COM_LOSS: 2
