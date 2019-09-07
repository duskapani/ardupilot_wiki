# YAPILANDIRMA

## Zorunlu Donanım Yapılandırması

Otomatik pilotun doğru çalışması için gerekli bileşenlerin nasıl konfigüre edileceğini açıklar.

### İvmeölçer kalibrasyonu

1. __Initial Setup | Mandatory Hardware__ girin, sol menüden __Accel Calibration__ seçin.

![](http://ardupilot.org/plane/_images/mp_accelerometer_calibration.png)

2. Kalibrasyonu başlatmak için __Calibrate Accel__ tıklayın.

MP sizden aracı her kalibrasyon konumuna getirmenizi isteyecektir. Otopilot istenilen konumda olduğunu belirtmek için herhangi bir tuşa basın ve ardından bir sonraki yöne geçin.

Kalibrasyon konumları: düz, sol tarafta, sağ tarafta, burun aşağı, burun yukarı ve sırt üstü.

![](http://ardupilot.org/plane/_images/accel-calib-positions-e1376083327116.jpg)

* Her adım için tuşa basıldıktan hemen sonra aracın hareketsiz kalması önemlidir.
* Aracın boyutu/şekli bunu zorlaştırırsa, kartı monte etmeden önce kalibre etmeniz gerekebilir.

3. Gerekli konumları yapın (tamamlandığında __Click When Done__ düğmesini kullanmanız gerekmez).

![](http://ardupilot.org/plane/_images/mp_accel_calibration_press_any_key.jpg)

4. Kalibrasyon tamamlandığında, MP'de "Calibration Successful!" görünmelidir.

https://www.youtube.com/watch?v=uyFZMQxRsC0

### Radyo kontrol kalibrasyonu

RC vericileri, pilotun uçuş modunu ayarlamasını, aracın hareketini ve yönünü kontrol etmesini ve ayrıca yardımcı işlevleri açıp kapamasını sağlar.

RC kalibrasyonu, her RC giriş kanalının minimum, maksimum ve "trim" değerlerini yakalamayı içerir, böylece ArduPilot girişi doğru bir şekilde yorumlayabilir.

#### transmitter kurulumunu kontrol etme

* Bataryanın bağlantısını kesin.
* RC alıcının uçuş kontrol cihazına bağlı olduğundan emin olun.
* RC vericinizi açın ve “trim tabs” varsa ortada olduklarından emin olun.
* Uçuş kontrol cihazını USB kablosu kullanarak PC'ye bağlayın.
* MPde “Connect” düğmesine basın ve __INITIAL SETUP | Mandatory Hardware | Radio Calibration__ ekranını açın.
* Ardupilot'un verici/alıcıdan girdi aldığını gösteren bazı yeşil barlar görünmelidir. Bar görünmezse alıcının LED'ini kontrol edin:
  * Işık olmaması otopilotun yanlış bağlandığını göstermez. Ters takılmış olabilecek konektörleri kontrol edin.
  * Kırmızı veya yanıp sönen bir LED, RC vericinizin/alıcınızın bağlı olmadığını gerektiğini gösterebilir. Talimatlar için RC ekipmanınızla birlikte verilen kılavuza bakın.
  
![](http://ardupilot.org/plane/_images/mp_radio_calibration.png)

* Vericideki kanal eşlemesini kontrol edin, yeşil barları gözlemleyin (hangi kanalları ne kontrol ediyor). 
 * Vericinizin Mod 1 veya Mod 2 olup olmadığını belirleyin.
 * Roll çubuğu kontrol etmeli: kanal 1
 * Pitch çubuğu kontrol etmeli: kanal 2
 * Throttle çubuğu kontrol etmeli: kanal 3
 * Yaw çubuğu kontrol etmeli: kanal 4
 * 3 konumlu switch (uçuş modlarını kontrol etmek için) Kanal 8'e ayarlanmalı.
* Yeşil barların doğru hareket ettiğini kontrol edin:
 * roll, throttle ve yaw kanalları için, yeşil barlar fiziksel verici çubuğuyla aynı yönde hareket etmelidir.
 * pitch kanalı için, yeşil bar fiziksel verici çubuğuyla ters yönde hareket etmelidir.
 * yanlış yönde hareket eden çubuk varsa, vericideki kanalı ters çevirin. Vericideki kanalı ters çevirmek mümkün değilse, "Reversed" onay kutusunu işaretleyerek ters çevirebilirsiniz. Onay kutusu görünmüyorsa, doğrudan RCx_REVERSED parametresini değiştirerek kanalı tersine çevirebilirsiniz (x 1 ve 4 arasında).

![](http://ardupilot.org/plane/_images/mp_radio_calibration.png)

#### kalibrasyon

* __INITIAL SETUP | Mandatory Hardware | Radio Calibration__ ekranını açın.
* Sağ alttaki "Calibrate radio" düğmesine tıklayın.
* RC cihazın açık olduğunu, bataryanın bağlı olmadığını ve pervanelerin çıkık olduğunu kontrol etmeniz istendiğinde "OK" tıklayın.

![](http://ardupilot.org/plane/_images/mp_calibrate_radio.jpg)

* Limitlerini belirlemek için verici kontrol çubuklarını, düğmelerini ve switchlerini hareket ettirin. Şimdiye kadar belirlenen min ve maks değerleri göstermek için kalibrasyon çubuklarında kırmızı çizgiler gözükecektirtir.

![](http://ardupilot.org/plane/_images/mp_radio_calibration_click_when_done.jpg)

* __Click when Done__ seçin.
* "Tüm çubuklarınızın ortalandığından ve throttle kapalı olduğundan emin olun ve devam etmek için tamam tıklayın." yazılı pencere açılacaktır. Throttle sıfır ayarlayıp "OK" tıklayın.
* MP kalibrasyon verilerinin özeini gösterecektir. Nomral değerler min için 1100, maks için 1900 civarındadır.

![](http://ardupilot.org/plane/_images/radi-calib-results.png)

#### mod1 ve mod2 vericiler

İki ana verici konfigürasyonu vardır:
* Mod 1: sol çubuk pitch ve yaw, sağ çubuk throttle ve roll
* Mod 2: sol çubuk throttle ve yaw, sağ çubuk pitch ve roll

![](http://ardupilot.org/plane/_images/radio_setup_mode_1.png)

#### kanal eşleşmeleri

Varsayılan uçak kanal eşleşmeleri:

* Kanal 1: Roll
* Kanal 2: Pitch
* Kanal 3: Throttle
* Kanal 4: Yaw
* Kanal 8 (varsayılan): uçuş modları

### Pusula kalibrasyonu

*  __Initial Setup | Mandatory Hardware__ altında __Compass__ seçin.
* Kartınız için en önemli konfigürasyon bilgilerini otomatik olarak girmesi için uçuş kontrol cihazınızın konfigürasyonunu seçin:
 * Modern uçuş kontro cihazları için __Pixhawk/PX4__ seçin.
 
![](http://ardupilot.org/plane/_images/MissionPlanner_CompassCalibration_MainScreen.png)

Normalde "Genel Pusula Ayarları"nı veya belirli pusula değerlerini (örn. "Compass #1" kısmı) değiştirmeniz gerekmez, ancak __Enbale compasses__ ve __Obtain declination automatically__ kutularının işaretli olduğunu onaylamak isteyebilirsiniz.

Sık sık "inconsistent compasses" pre-arm mesajını görüyorsanız ve harici pusulanın oryantasyonunun doğru olduğundan eminseniz, Compass #2 (dahili pusula) devre dışı bırakmak isteyebilirsiniz.

#### yerleşik (onboard) kalibrasyon

Bu yöntem, yer istasyonundaki eski “Offboard Calibration” dan (yani “Live Calibration”) daha doğrudur çünkü ofsetlere ek olarak ölçeklendirme de hesaplanır.

Bu kalibrasyonu gerçekleştirmek için:
* "Onboard Mag Calibration" bölümündeki "Start" düğmesine tıklayın.
* aracı havada tutun ve her bir tarafı (ön, arka, sol, sağ, üst ve alt) sırasıyla birkaç saniye boyunca yere bakacak şekilde döndürün.

![](http://ardupilot.org/plane/_images/accel-calib-positions-e1376083327116.jpg)

* araç döndürülürken yeşil barlar kalibrasyon tamamlanana kadar sağa doğru ilerlemelidir.
* başarılı bir şekilde tamamlandığında, “Please reboot the autopilot” penceresi görünecek ve aracı kullanabilmeniz için otopilotu yeniden başlatmanız gerekecektir.

Kalibrasyon hatalı olursa:

* birden fazla denemeden sonra kalibre edemiyorsanız, "Cancel" düğmesine tıklayın ve "Fitness" açılır menüsünü Relaxed ayara getirin ve tekrar deneyin.
* pusula kalibrasyonu hala başarısız olursa, COMPASS_OFFS_MAX 850'den 2000'e ve hatta 3000'e yükseltimesi yardımcı olabilir.

### Failsafe işlevi

Uçak üç şey yapacak şekilde tasarlanmış kısa süreli bir arızaya karşı koruma fonksiyonuna sahiptir:
1. RC sinyalinin tamamen kaybolduğunu tespit edin ve AUTO mod yanıtı tanımlayın. Bazı RC ekipmanları bunu yapabilir bazıları ise yapamaz.
2. Telemetrei kaybını FS_LONG_TIMEOUT saniyeden daha uzun bir süre boyunca tespit edin ve RTL moda geçin.
3. GPS kaybını 20 saniyeden uzun süre tespit edin ve GPS sinyali tekrar kazanılana kadar Dead Reckoning moda geçin.









