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
