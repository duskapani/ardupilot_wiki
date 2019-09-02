# HIZLI BAŞLANGIÇ AYARLAMA

Bu makale, uçak gövdesini ayarlamaya başlamanıza yardımcı olacak bilgiler sağlar. Ana adımlara, araçlara ve kavramlara genel bir bakış içerir.

## Uçak Gövdesi Nasıl Ayarlanır

Plane varsayılan PID ayarlarıyla, hafif RC uçak gövdelerinin (tam boyutlu değil, çoğunu güvenle uçuracaktır. İyi uçmak için, sık sık navigasyon ve rüzgarda güvenilir performans ile otopilotunuzu ayarlamak isteyeceksiniz.

En önemli konfigürasyon Roll ve Pitch ayarıdır, çünkü etkili navigasyonun yanı sıra duyarlı ve istikrarlı uçuş içinde gereklidir. Roll ve pitch ayarlamanın en iyi yolu AUTOTUNE ile Otomatik Ayarlama kullanmaktır (gerekli anahtar değerleri öğrenmek için pilot tarafından uçuş durum girişindeki değişiklikleri kullanan bir uçuş modu).

**İPUCU:** Ayarlama yapmadan önce uçağınızın uçmasını sağlamak üzere kullanabileceğiniz [birçok yaygın hava aracı için yapılandırma](http://ardupilot.org/plane/docs/configuration-files-for-common-airframes.html#configuration-files-for-common-airframes) değerleri sunuyoruz. AUTOTUNE uçağınızla çalışmazsa [Roll, Pitch ve Yaw Kontrol Cihazı Ayarlama Kılavuzu](http://ardupilot.org/plane/docs/roll-pitch-controller-tuning.html#roll-pitch-controller-tuning)'nda tamamen manuel yaklaşım açıklanmaktadır.

Roll, Pitch (ve isteğe bağlı olarak Yaw) ayarladıktan sonra, [TECS ayarlama kılavuzunu](http://ardupilot.org/plane/docs/tecs-total-energy-control-system-for-speed-height-tuning-guide.html#tecs-total-energy-control-system-for-speed-height-tuning-guide) kullanarak yükseklik kontrolcüsünü ve [L1 kontrol cihazın ayarlama kılavuzunu](http://ardupilot.org/plane/docs/navigation-tuning.html#navigation-tuning) kullanarak yatay seyrüsefer ayarlamanız gerekir.

Uçağın diğer yönlerinin nasıl ayarlanacağına ilişkin bilgiler [Ayarlama başlangıç sayfasına](http://ardupilot.org/plane/docs/common-tuning.html#common-tuning) linklenmiştir.

## Mission Planner Konfigürasyon Ekranı

Mission Planner, tüm konfigürasyon ve ayarlama parametrelerine CONFIG / TUNING bölümünden erişim sağlar. Soldaki sütun tam parametre setine bağlanır. Sağdaki ekran, daha sık değiştirilen parametrelerin bazılarını (tümünü değil) listeler. Parametre değişikliğini yapmak için her iki tarafı da kullanabilirsiniz. Parametre güncellemeleri, “write params” tuşuna basar basmaz bağlı karta gönderilir, çoğu mevcut uçuşu (varsa) hemen etkiler ve kalıcı hafizaya yazılır, böylece güç döngüsünden kurtulurlar.

//////RESİM//////

Uçağı ayarlamak için başlangıç noktası, yukarıda gösterilen Uçak PID ekranıdır. Burası, FBW-A modunda uçuşu etkinleştirmek ve ayrıca daha hassas yatay konumlandırma için L1 Kontrolünün ayarlanmasını sağlamak için Servo Roll ve Servo Pitch PID kazancını ayarlayabileceğiniz yerdir.

Ayrıca, Advanced Parameters ekranından yapılandırma dosyalarını (bilgisayarınıza) kaydedebilir ve ordan yükleyebilirsiniz. Konfigürasyon dosyaları versiyonlanmıştır - eğer parametre versiyon numarası güncel değilse, Uçak tarafından bulunan daha eski parametre dosyası yoksayılır.

Bu parametrelerden birkaçının bir sonraki bölümde açıklanan PID (Proportional, Integral, Differantial) ayarları olduğunu unutmayın.

## PID kazanç değerleri

Roll veya pitch açısının kontrolü, [Oransal-İntegral-Türev (PID) Kontrolör](https://en.wikipedia.org/wiki/PID_controller) kullanılarak ayarlanır. 

Uçağın kontrol yüzeyine uygulanan son kontrol, üç kazanç değerinin etkilerinin birleşimidir:

- Oransal kazanç (P) en basit kontrol formudur, "mevcut" hatadır. Otopilot 10 derecelik pitch istiyor, 5 dereceye sahip, yani 5 derece hata: bir miktar elevator uygula (hata miktarı için uygulanan miktar P numarası tarafından belirlenir -ölçeklenir-.
- İntegral kazanç (I) önceki hataları dikkate alır ve istikrarlı hataları telafi edebilir. Otomatik trim ayarı olarak düşünülebilir. "I" kazancının dezavantajı, her zaman geçmiş hatalara tepki göstermesi nedeniyle, her zaman "yakalamaya" çalıştığı için kontrol döngüsünü sönümünü azaltır.
- Türev kazancı (D) açının değişme oranını geri beslediği için sönüm ekler. Ayrıca, açıdaki gelecekteki değişiklikleri tahimn etmeye çalışmak olarak da düşünülebilir. "D" kazancının dezavantajı, servoyu kullanan gürültü miktarını arttırmasıdır ve çok yüksek olursa, bazı durumlarda uçağa zarar verebilecek hızlı pitch veya roll salınımına neden olur.


P, PI veya PID değerlerinin ayarlanması, istenen attitude (pitch, hız, rulman, her neyse) ile gerçek davranış arasında gözlenen hatanın, aşırı salınım olmadan ne kadar çabuk bir şekilde iptal edilebileceğini iyileştirebilir.

