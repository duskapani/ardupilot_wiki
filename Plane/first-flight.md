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
* autotune sistemi, roll ve pitch I ve D kazançlarınız ve maksimum roll ve pich dereceleriniz için varsayılan değerler ayarlayacaktır. Bu değerler AUTOTUNE_LEVEL bağlıdır.
* autotune sistemi, istenen roll ve pitch derecenizi izler(vericinin stcik hareketlerinin belirlediği şekilde). İstenen roll ve pitch derecesi maksimum derecenin %80'ini aştığında, autotune sistemi roll ve pitch ayar değerlerini öğrenmek için uçağın tepkisini kullanır.
* autotune sistemi her 10 saniyede 10 saniye önce sahip olduğunuz parametreleri kaydeder. Bu, eğer uçak dengesizleşmesine neden olursa başma moda geçmek ve kurtarmak için 10 saniyeniz var demektir. AUTOTUNE modundan çıktığınızda, kaydedilen son parametreler geri yüklenir.
* eğer roll ve pitch için varsayılan parametrelerle başlıyorsanız, AUTOTUNE'a ilk girdiğinizde uçağın oldukça ağır ilerliyor olduğunu görebilirsiniz. Tuning aşaması ilerledikçe bunun iyileşeceğini göreceksiniz. Uçuş alanınızın uzun ve yavaş dönüşler için bol alanı olduğundan emin olun.

Başarılı bir auotune için anahtar şey, verici sticklerinizle hızlı roll veya pitch hareketleri yapmaktır. Tek seferde roll veya pitch hareketlerinden birini yapmalı ve çubuğu hızlıca maksimum sapmaya kaydırmalısınız.

Bu nedenle, önce aileron çubuklarıyla roll yönünde sertçe sağa dönmelisiniz, ardından kısa bir süre sonra aileron çubuğunu sola döndürmek için diğer tarafa sertçe ittirin. Her bir çubuk hareketinden sonra uçağın yana yatmasını beklemeniz gerketiğini unutmayın. Tek bir yönde 2 saniye çubuk hareketinden sonra hızlıca tersin çevirebilirsiniz. Uçak sağa yatacak, daha sonra aileron çubuğunu hareket ettirirken sertçe sola doğru yönlendirilir. Her geri dönüş ile tuning değerlerini yaklaşık %5 artıracaktır. Bu yüzden makul bir tuning değeri öğrenmek için en az 20 tam (sağ sol) çubuk hareketine ihtiyacınız var.

Pitch ayarları için uçağı inişli çıkışlı bir yolculuğa çıkarmak üzere verici pitch çubuğunu kullanmak gerekir. Çubuğu sertçe yukarı çekin ve ardından kısa bir süre sonra aşağıya doğru bastırın. Bunu en az 20 kez tekrarlayın.

Başlangıç tuning değerlerleriniz çok düşükse, AUTOTUNE modunda uçarken uçağın giderek daha duyarlı hale geldiğiniz fark etmelisiniz. Uçak uçmaya devam etmenin tehlikeli olduğunu düşündürecek kadar kararsız hale gelirse, AUTOTUNE modundan çıkmalısınız. Bu, 10 saniye öncesinde sahip olduğunuz parametreleri geri yükler.

### Çok erken durdurmayın

En az 20 hızlı roll hareketi ve en az 20 hızlı pitch hareketi yapmalısınız, tercihen çok daha fazla tavsiye edilir. Uçağın iyi uçtuğunu düşündüğünüz noktadan sonra AUTOTUNE modunda uçmaya devam edin.

### Ayarlamayı tamamlama

Autotune ile makul roll ve pitch ayar parametrelerini öğrendikten sonra, diğer bazı temel parametreleri elle ayarlayarak tuningi tamamlamanız gerekir.

Çoğu uçak şekli için gereken parametreler şunlardır:

__NAVL1_PERIOD:__ Varsayılan olarak 25tir, kötü ayarlanmış uçaklarla baş etmek için tasarlanmış aşırıya kaçmayan bir değerdir. Uçağın otomatik modlarda (AUTO, RTL ve LOITER gibi) ne kadar keskin döneceğini kontrol eder. Çoğu uçak çok daha düşük bir değer kullanmalıdır. Başarılı bir roll ve pitch değeri ayarlama işlemini tamamladığınızda, henüz yapmadıysanız NAVL1_PERIOD değerini 18'e düşürmelisiniz. Bu seviyenin ötesine geçmek için AUTO modda dikdörtgen gridde uçurmalı ve uçaktan memnun olduğunuz bir hızda dönene ve uçuş sırasında "wag its tail" olmayıncaya kadar NAVL1_PERIOD'u her seferde 1 düşürmelisiniz.

__PTCH2SRV_RLL:__ Bu parametre, burun seviyesini korumak için dönüşte ne kadar elevator ekleyeceğini kontrol eder. Pek çok uçak, varsayılan olarak 1.0 olan bu parametrede küçük bir değişiklik gerektirir. Bu değeri ayarlamanız gerekip gerekmediğini görmek için FBWA modunda, herhangi bir elevator girişi yapmazken, aileron çubuğunu sertçe tutarak sabit bir daire çizmelisiniz. Uçak irtifa kazanıyorsa, PTCH2SRV_RLL değerini az miktarda azaltmanız gerekir (başlangıçta 0,95'e düşürmeyi deneyin). Uçak daire çizerken irtifa kaybederse, PTCH2SRV_RLL değerini az miktarda yükseltin (başlangıçta 1,05'i deneyin). Eğer 1.3'ün üzerinde veya 0.8'in altına inmeniz gerekiyorsa, kurulumunuzla ilgili bir sorun vardır 


Uçağınızın performansını artırabilecek birçok başka parametre var, ancak bunlar çoğu kişinin ihtiyaç duyduğu parametreler. Lütfen daha fazla bilgi için normal manuel tuning belgelerini okuyun.

### Manuel tuning vs AUTOTUNE

