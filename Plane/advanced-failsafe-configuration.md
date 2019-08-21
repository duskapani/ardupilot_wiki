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


## AFS Termination

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

### Maximum pressure altitude breach
When sharing airspace with other aircraft it is usual practice to define the available flight altitudes in terms of a common reference pressure, typically QNH (a reference to “nautical height”). The QNH reference pressure, measured in millibar, is distributed to all aircraft either via a radio message or through aviation internet and weather sites.

Aircraft then use their barometer to measure the pressure relative to that QNH pressure, which gives them an altitude reference which all aircraft in the area should be using.

The AFS system is able to enforce a pressure altitude limit by setting the QNH pressure in the AFS_QNH_PRESSURE parameter, as a value in millibars. The pilot should then also set a pressure altitude limit using the AFS_AMSL_LIMIT parameter (in meters). Note that this pressure altitude limit is relative to sea level (AMSL stands for “above mean sea level”).

If both of these parameters are set then the AFS system fill monitor pressure altitude and will initiate a termination if the pressure altitude rises above the AFS_AMSL_LIMIT.

You need to be very careful to set the right AFS_QNH_PRESSURE for your local conditions on the day of your flight, as the QNH pressure can be very different on different days.

In addition to the QNH pressure limit, the AFS system also monitors the health of your barometer. If the barometer is unhealthy for 5 seconds then the AFS system will check the AFS_AMSL_ERR_GPS parameter. If it is -1 (the default) then the aircraft will terminate immediately. If it is not -1 then the AFS system will use the AFS_AMSL_ERR_GPS value as a margin to add to the GPS height, and will allow the flight to continue if the GPS altitude plus the AFS_AMSL_ERR_GPS value (in meters) is below the AFS_AMSL_LIMIT value. The purpose of this margin is to account for the inaccuracy of GPS altitudes. A value of 200 is reasonable for safety to ensure the AFS_AMSL_LIMIT pressure altitude is not breached.

### GPS Loss
The AFS system monitors the health of your GPS receivers throughout the flight. If all of your available GPS receivers lose position lock then this initiates a GPS failure failsafe.

When a GPS failure occurs (which is defined as loss of GPS lock for 3 seconds) the AFS system will look at the AFS_WP_GPS_LOSS parameter. This parameter species a waypoint number in your mission to use when a GPS failure occurs. If AFS_WP_GPS_LOSS is non-zero the aircraft will change current waypoint to the waypoint number specified in AFS_WP_GPS_LOSS. You should setup your mission so that the aircraft will perform whatever actions you want on GPS loss. For example, you could have a set of waypoints starting at number 10 which first loiter on the spot for 30 seconds, and then proceed back to the airfield. You would then set AFS_WP_GPS_LOSS to 10 to enable that part of the mission on loss of GPS lock.

When setting up mission items for GPS lock it is sometimes useful to include “loiter at the current location” waypoints. That is achieved by setting both the latitude and longitude of LOITER mission commands to zero.

If the GPS recovers after a GPS failsafe has started, then the aircraft will automatically resume its mission where it left off.

If during a period of GPS loss the aircraft also loses communications with the ground station then this is termed a “dual loss”, and the aircraft will terminate.

If AFS_MAX_GPS_LOSS is set to a non-zero number, then it is used as a maximum count of the number of GPS failures that will be allowed while returning to the mission after GPS lock is re-established. This counter is only incremented if the 2nd GPS failure happens at least 30 seconds after the previous one (to account for a short period of GPS failure).

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
