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
