# İLK UÇUŞ

## Uçağı Kalibre Etme ve Çalıştırma
Bu makalede, uçağı kaldırmadan önce yapılması gereken temel kurulum ve kalibrasyon açıklanmaktadır.

### Zemin kalibrasyonu
Verici mod switch'inizi Manuel olarak ayarlayın. Bu, sistemi başlatmak için güvenli bir moddur.

Kartınızı alanda açarken LEDler mavi ve kırmızı renkte yanıp sönmeyi bırakana kadar (yaklaşık 30 saniye) uçağı zeminde hareketsiz bırakmalısınız. Bu, jiroskopların kalibre edildiği anlamına gelir.

### Güvenlik switchinin (mevcutsa) bağlantısını kesmek
Uçuş kontrol cihazına bağlı bir güvenlik switchi varsa, araç arm edilmeden önce bağlantısı kesilmelidir. 

* Güvenlik Switchi LED Göstergeleri:
  * Hızlı Yanıp Sönme: Hatalı durum, Güvenlik devre dışı bırakılamaz. Mutemelen kalibre edilmemiş veya sensor hatalı.
  * Yavaş Yanıp Sönme: Güvenli durum. Güvenlik Düğmesine 5 saniye boyunca basılarak güvenlik devre dışı bırakılabilir.
  * LEDin Sürekli Yanması: Güvenlik devre dışı bırakıldı. Uçuş kontrolcüsü Throttle aşağı ve sağa ile arm edilebilir.
  * LED sürekli Güvenlik Devre Dışı belirtmek için yanıyorsa, Güvenlik düğmesine 5 saniye basılarak Güvenli duruma geri döndürülebilir.
  
### Hava sürati sensörünü (varsa) kalibre edin ve kontrol edin
Araçta hava sürati sensörü varsa, burada açıklanan uçuş öncesi kontrolleri her uçuştan önce gerçekleştirilmelidir.

![](http://ardupilot.org/plane/_images/preflight.jpg)

### GPS kilidini beklemek
Uçuş kontrolünden önce Pixhawkın LED'lerinin yeşil renkte yanmasıyla belirtilen GPS kilidini beklemelisiniz. GPS kilidini beklemiyorsanız barometrik altimetre kalibrasyonu yanlış olur ve RTL, Loiter, Auto ve diğer GPS bağımlı modlar düzgün çalışmaz.

Uçağın ev konumu başlangıçta uçağın GPS kilidinin kazanıldığı sırada belirlenir. Otopilot disarm edildiği sürece sürekli güncellenir.

Bu, RTL görevinde uçağın bu noktaya döneceği anlamına gelir.

### Servo hareketlerini kontrol et
__HER UÇUŞTAN ÖNCE__: havalanmadan önce, uçağı elinizde tutun ve FBWA moduna geçin, ardından kontrol yüzeylerinin düz bir seviyeye dönmesi için doğru şekilde hareket ettiğini doğrulamak için uçağı eğin ve döndürün. (Aileronlar ve elevatörler hareket edecek; rudder yerde çok hareket etmez. Bu, yanlışlıkla bir kanalı tersine çevirmediğinizden emin olmanızı sağlar.

Hiçbir uçuşun ters gitmemesini sağlamak için kontrol yüzeylerinizi RC vericinizle birlikte hareket ettirirken, her uçuştan önce bunu yapmanız gerekir. Bunu yapmamak, kazaların 1 numaralı nedenidir.

Güvenlik önlemi olarak, throttle'nız zemindeyken sadece Manuel modda, Stabilize modda veya ototakeoff için Auto modda arm edilir. Havada hareket edene kadar başka hiçbir Auto modda açılmaz.

https://youtu.be/RUs62xmdnmg

### İlk uçuş
Stabilize veya  Fly By Wire moduna geçmeniz ve kontrol yüzeylerinin davranışını gözlemlemeniz önemle önerilir. Pitch veya roll yaptığınız zaman uçağı dengelemek için hareket etmeleri gerekir. Sağlam değilse, buradaki talimatları izleyerek kazançları ayarlayabilirsiniz.

PID kazancınızı ayarlamadıysanız, ilk takeoffu AUTOTUNE modunda yapmayı düşünebilirsiniz. Bu, kalktıktan hemen sonra ayar işlemine başlayacaktır.

### İkinci uçuş
İkinci uçuşunuz için, MP'ın mod kurulum sayfasındaki üçüncü modu (RC mod anahtarınızın 3.konumu) RTL olarak değiştirin.

Havadayken aracı RTL konumuna getirin. Bu navigasyonu test edecektir. Uçak, arm edildiği yere (ya da en yakındaki Rally noktasına) geri dönmeli ve sabit bir yükseklikte (MP'den ayarlanabilir) yörüngede dönmelidir. 

Düzenli bir şekilde ve mükkemmele yakın bir dairede dönmüyorsa, otopilotu uçak gövdenize özgü ayarlamanız gerekir. Bu genellikle [burada](http://ardupilot.org/plane/docs/roll-pitch-controller-tuning.html#roll-pitch-controller-tuning) açıklandığı gibi, Roll parametrelerini ayarlayarak yapılabilir.

Tüm bunlar kontrol edildikten sonra, waypoint görevlerini programlayabilir ve Auto modda test edebilirsiniz.
  
### Düzey ayarı

Uçağınız FBWA'da uçarken bir yere dönme eğiliminde olduğunu ve/veya verici çubukları ortalanmış iken irtifa kazandığını veya kaybettiğini görebilirsiniz. Bu durumda şunları yapın:

1. Otopilot açık ve mission plannera bağlıyken vericinizden FBWA seçin, FLIGHT DATA tuning penceresini seçin ve nav_roll ve nav_pitch verilirini çizin. Verici çubuklarınız ortalanmış durumdayken, bunların her ikiside bu ekran görüntüsünde gösterildiği gibi sıfır olmalıdır. Değilse, RC kalibrasyonunuzu tekrarlamanız veya verici trimlerinizi ayarlamanız ve FBWA uçuş testini tekrarlamanız gerekir.

![](http://ardupilot.org/plane/_images/CheckFBWADemands.jpg)

Sıfır iseler, düz ve dengeli uçarken otopilot kartı ve uçak durumu arasındaki açı farkı için <mark>AHRS_TRIM_X</mark> (roll) ve <mark>AHRS_TRIM_Y</mark> (pitch) ayarlamanız gerekir. Bunlar için __CONFIG/TUNING | Full Parameter List__ gidin ve parametreleri aşağıdaki ekran görüntüsünde gösterildiği gibi ayarlayın.

![](http://ardupilot.org/plane/_images/AdjustRollPitchTrims.png)

Bu parametreler radyan cinsindendir, bu nedenle başlangıçta 0.01'lik artışlarla ayarlayın. Uçak sola dönerse, AHRS_TRIM_X arttırılmalıdır. Uçak orta gaz ile irtifa kaybederse, AHRS_TRIM_Y artırılmalıdır.

## Uçağı Arm Etme

Uçağı uçurabilmeniz için önce arm etmeniz gerekir. Bunun iki amacı vardır:
* pilot uçmaya hazır değilken motorun çalışmasını önler (güvenlik özelliği)
* otopilot tamamen yapılandırılmadan ve uçmaya hazır olmadan takeoff yapmasını önler


Arming'in yaptığı en önemli şey, motoru etkinleştirmektir. Uçak arm edilene kadar motoru çalıştıramazsınız (örneğin, throttle kontrol edemezsiniz). 

### Armı reddetme nedenleri

Otopilotun arm etmeyi reddetmesinin olası nedenleri şunlardır:

* __barometer not healthy.__ Çok nadir görülür. Tekrar tekrar meydana gelirse, barometre donanım arızası olabilir.
* __airspeed not healthy.__ Hava hızı sensörünüz takılıysa ve otopilot hava hızı okuması almıyorsa, armı reddedecektir.
* __logging not available.__ MicroSD kart arızalandığında veya başarısız olduğunda arm yapılamaz.
* __gyros not healthy.__ Jiroskop başarısız olursa otopilot armı reddeder. Bu nadir görülür ve tekrar tekrar gerçekleşirse, bir donanım arızası olabilir.
* __gyros not calibrated.__ Başlangıçta otomatik gyro kalibrasyonu yapılmadığında gerçekleşir. Uçak hareketsiz dururken otopilotu yeniden başlatmayı deneyin.
* __accels not healthy.__ İvmeölçer arızalandığında otopilot armı reddeder. İvmeölçeri yeniden kalibre etmeyi deneyin.

* __GPS accuracy errors.__ Bildirilecek 4 tip GPS arm hatası vardır. Bunlar “GPS vert vel error”, “GPS speed error”, “GPS horiz error”, “GPS numsats”. Daha iyi GPS alımı için uçağı taşımayı ve GPS engelleyici şeyleri kapatmayı deneyin.
* __Mag yaw error.__ Pusulanız hizalanmıl olmadığında ortaya çıkar. Pusula yönünüzü kontrol edin ve kalibrasyonu tekrar yapın veya manyetik malzemeleri uçaktan uzaklaştırın.
* __EKF warmup.__ Bu, EKF hala hazırlanıyorsa olur. 10 saniye daha bekleyin ve tekrar deneyin.
* __AHRS not healthy.__ EKFnin sağlıklı olmadığı anlamına gelir. Hata devam ederse kartınızı yeniden başlatın.
* __3D accel cal needed.__ 3B ivmeölçer kalibrasyonu yapmadığınızda meydana gelir.


## AUTOTUNE ile Otomatik Ayarlama

Uçağınız için iyi roll/pitch ayar parametre seti almak, dengeli ve doğru bir uçuş için çok önemlidir. Bunu yapmanıza yardımcı olması için aşağıda belirtilen AUTOTUNE sistemini kullanmanız şiddetle tavsiye edilir.

### AUTOTUNE ne yapar

AUTOTUNE modu, FBWA ile aynı şekilde uçan bir uçuş modudur, ancak roll ve pitch ayarları için temel değerleri öğrenmek üzere pilot tarafından kullanılan girdi değişikliklerini kullanır. Pilot AUTOTUNE moduna geçer ve uçağı birkaç dakika uçurur. Pilot, uçağın autotune koduna nasıl tepki vereceğini öğrenebilmesi için olabildiğince keskin attitude değişikliğine girmeniz gerekir.

### AUTOTUNE için ayarlama

Uçağınızı AUTOTUNE'a ayarlamak için vericinizdeki uçuş modu switchi ile AUTOTUNE modunu seçmeniz gerekir.

Ayrıca, YKİ gelişmiş parametre ekranında AUTOTUNE_LEVEL parametresini ayarlayarak ayarlayarak tuning seviyesi seçmelisiniz. AUTOTUNE_LEVEL parametresi, ne kadar agresif olmasını istediğinizi kontrol eder. Varsayılan olarak seviye 6, orta düzey ayar üretir acemi ve orta seviye pilotlara uygundur. Daha deneyimli pilotsanız seviye 7'yi seçebilirsiniz; bu biraz daha keskin ayarlara neden olur (daha hızlı attitude değişiklikleri). 7'nin üzerindeki seviyeler, başlangıç için düşük seviyeli bir ayar yapana kadar önerilmez.

Ayrıca gövde için tüm temel ayarların doğru olduğundan emin olmanız gerekir. Özellikle, tüm yüzey yönlerinin doğru olduğundan ve minimum hava sürati için makul bir değere sahip olduğunuzdan emin olun. Autotune, ARSPD_FBW_MIN parametresinde ayarladığınız minimum hava hızının üzerine çıkana kadar hiçbir şey yapmaz. Hava hızı sensörünüz yoksa, yine de diğer sensörlerden alınan hava hızı tahmini ile birlikte bu değer hala kullanılır. Ayrıca, RC kalibrasyonunu yaptığınızdan emin olun, çünkü AUTOTUNE sadece verici çubuklarınızla tam kontrol hareketleriniz varsa işe yarar.

Diğer kontrol edilecekler:
* uygun hava hızı sensörünüz varsa, kalibre etmiş olursunuz. 
* ağırlık merkezinizin doğru olduğundan emin olun. Genelde burun ağırlığının kuyruk ağırlığından biraz daha fazla olması daha güvenlidir.
* yüzey trimlerinizi kontrol edin. Bu ayarın belgelerini okuduktan sonra TRIM_AUTO kullanmak isteyebilirsiniz.
* failsafe ayarlarınızın yapıldığından emin olun. Vericinizi uçağınız yerdeyken (pervane sökülmüş veya güvenli hale getirilmiş) kapatmayı deneyin ve uçağın tepkisini kontrol edin.
* gerekiyorsa RTL için güvenli bir yere rally noktası ayarlayın.

### AUTOTUNE'da uçuş

Tüm ayarlar tamamlandığında AUTOTUNE modunda uçmaya başlayabilirsiniz. AUTOTUNE modunda takeoff yapabilir, diğer modda takeoff yapabilir ve irtifa kazanınca AUTOTUNE'a geçiş yapabilirsiniz. 

AUTOTUNE moduna girdiğinizde birkaç şey olur:
* 
