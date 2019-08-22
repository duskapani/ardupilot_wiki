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


### Yer kontrol istasyonu iletişim kaybı

AFS sistemi, yer istasyonunuz ile uçağınız arasındaki bağlantının sağlığını izler. Bunu, yer istasyonundan gelen HEARTBEAT MAVLink mesajlarına bakarak yapar.

Uçak 10 saniyeliğine HEARTBEAT mesajı almazsa, YKİ failsafe durumuna girer. Daha sonra AFS_WP_COMMS parametresine bakar, sıfır değilse, mevcut hedef waypointi AFS_WP_COMMS'da verilenle değiştirir. İletişim kaybı konusunda hangi işlemleri yapmak istediğinizle ilgili olarak görevinizin bir bölümünü oluşturmalısınız.

GPS kilidi YKİ iletişimiyle aynı anda kaybedilirse, o zaman "ikili kayıp" olarak kabul edilir ve uçuş sonlandırılır.

Unutmayın ki HEARTBEAT mesajlarının izlenmesi sadece otomatik pilota yer istasyonundan gelen mesajları görebileceğini söyler. Bu, yer istasyonunun uçaktan gelen mesajları görebileceği anlamına gelmez. Bu nedenle, yer istasyonunuz uçaktan hala HEARTBEAT mesajlarını alırken iletişim kaybını rapor etmesi oldukça muhtemeldir.

[AFS_MAX_COM_LOSS]() sıfır olmayan bir sayıya ayarlanırsa, iletişim yeniden kurulduktan sonra göreve dönmesine izin verilecek maksimum iletişim hatası sayısı olarak kullanılır. Bu sayaç sadece 2. haberleşme hatası öncekinden en az 30 saniye içinde meydana gelirse artar (kısa süreli iletişim kesintisi için).


### RC kaybı

RC kontrolü manuel kontrol modunda [AFS_RC_FAIL_MS]() milisaniyeden daha fazla bir süre boyunca kaybolursa, uçuş sonlandırma etkinleştirilir. Bu sonlandırma modu yalnızca [AFS_RC_FAIL_MS]() sıfır olmadığında etkindir. OBC kuralları için 1500'e (1,5 saniye vererek) ayarlanmalıdır. 


## AFS sisteminin izlenmesi

AFS sistemi, harici elektronik aksamlar (harici bir failsafe kartı gibi) kullanarak failsafe sisteminin sağlığını izlemeyi kolaylaştırmak için bazı ek parametreler sunar.

Anahtar parametreler:

- **AFS_TERM_PIN**: Sonlandırma başlatıldığında high voltaja ayarlanan dijital pindir. [AFS_TERM_ACTION]() parametresi 42 olarak ayarlanmamış olsa bile, bu pinin sonlandırma sırasında high olacağını unutmayın.

- **AFS_HB_PIN**: Failsafe sistemi tarafından 10Hz hızında değiştirilen pin için dijital pin numarasıdır. Sonlandırma meydana gelirse ve bir AFS_TERM_PIN değeri ayarlanmamışsa, heartbeat pini geçişi durduracaktır.

- **AFS_MAN_PIN**: Uçak MANUEL moddayken high olan pin için dijital pin numarasıdır. Manuel modu algılamak ve farklı davranmak bazı harici güvenli olmayan kartlarda yararlı olabilir.


## Manuel Sonlandırma

Otomatik sonlandırma dışında, hava taşıtı operatörünün, hava taşıtının insanlar veya diğer hava taşıtları için tehlike oluşturduğunu düşünmeleri durumunda, hava aracını derhal sonlandırabilmesi de önemlidir. Anında sonlandırmaya zorlamak için [AFS_TERMINATION]() parametresini kullanmanız gerekir. Bu parametreyi 1 olarak ayarlayarak uçak derhal sonlandırabilirsiniz.


## Örnek AFS Failsafe Görevi

AFS failsafe görevi oluşturmak zaman alır ve çok dikkat edilmesi gerekir. Neyin mümkün olduğunu anlamak için aşağıdaki örnek dosyaları bakmanız yararlı olabilir:

- Dosyada yorumlanmış farklı AFS hataları için waypointler içeren 2014 Outback Challenge için bir [waypoint görevi](https://github.com/tridge/cuav/blob/master/cuav/data/way.txt)
- 2014 Outback Challenge için bir [coğrafi sınırlandırma dosyası](https://github.com/tridge/cuav/blob/master/cuav/data/fence.txt)


## AFS Sistemini SITL’de Test Etme

Gerçek bir uçakta kullanmadan önce SITL simülasyon sistemini kullanarak AFS sistemini kapsamlı bir şekilde test etmeniz önerilir. SIM_ parametrelerini kullanarak tüm uçuş hatalarını simüle edebilirsiniz. Kingaroy'da SITL'i OBC testine hazır hale getirmek için kullanacağınız:

> sim_vehicle.py -L Kingaroy --console --map

SITL’de failsafe testi için anahtar parametreler şunlardır:
 
- Test GPS arızası: SIM_GPS_DISABLE 1 ayarla
- Test RC arızası: SIM_RC_FAIL 1 ayarla
- Test iletişim arızası: heartbeat 0 ayarla
- Test çit arızası: CRUISE moda geç ve sınırın içine uç
- Test QNH arızası: AFS_AMSL_LIMIT 100 ayarla


## AFS Failsafe Kullananlar için Ek İpuçları

Kalkıştan önce coğrafi sınırlandırmanızın etkin olduğundan emin olmalısınız. Önuçuş kontrol listenizin bir parçası olarak yapılabilir veya bir FENCE_CHANNEL ayarlayabilir ve vericinizin içinden etkinleştirebilirsiniz. Bu, vericinizin menzil dışında kalması durumunda çitin etkin kalmasını sağlar.
 

## Outback Challenge 2014 için Ayarlar
 
OBC 2014 kurallarına göre aşağıdaki ayarlara sahip olmalısınız:

AFS_ENABLE: 1
AFS_WP_COMMS: waypoint number for OBC comms hold followed by two minute loiter, then return to airfield home
AFS_WP_GPS_LOSS: waypoint number to loiter in place for 30 seconds, followed by return to airfield home
AFS_TERM_ACTION: 42
AFS_AMSL_LIMIT: 914
AFS_QNH_PRESSURE: o gün için uygun QNH basıncı
AFS_RC_FAIL_MS: 1500
AFS_MAX_GPS_LOSS: 2
AFS_MAX_COM_LOSS: 2
