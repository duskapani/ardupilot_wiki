# Otomatik İniş

Bu makale, Plane'da uçağın güvenli olarak indirilmesini sağlayacak bilgiler içerir.

## Otomatik İniş Yapılandırması

Plane, görev planının bir parçası olarak uçağı otomatik olarak indirebilir.

Uçağı indirmek için, görevin sonuna istediğiniz konma noktasının enlem, boylam ve irtifasını belirten bir [NAV_LAND]() komutu eklemeniz gerekir. Çoğu durumda, irtifa 0 olarak ayarlanmalıdır. İniş sırasında, otopilot uçak palye noktasına ulaştığında -aşağıda açıklanan parametrelerle kontrol edilir- gazı kesecek ve mevcut doğrultuyu koruyacaktır.


### Anahtar Parametreler

Otomatik inişi kontrol eden temel parametreler:

-  [LAND_FLARE_ALT]()
-  [LAND_FLARE_SEC]()
-  [LAND_PITCH_CD]()
-  [TECS_LAND_ARSPD]()
-  [TECS_LAND_SPDWGT]()

Bu parametrelerin her birinin anlamı ve önerilen değeri aşağıda açıklanmıştır.

### Palye Noktası Ayarlama

Flare: Palyeye geçmek

“Palye”, otopilotun gazı kestiği, pitch'i yükselttiği ve zemine yavaş yavaş inmek için uçağı yavaşlattığı inişin son aşamasıdır. "Palye" için uygun zaman uçağın tipine bağlıdır, [LAND_FLARE_ALT]() ve [LAND_FLARE_SEC]() parametreleri tarafından kontrol edilir.

Palyenin ilk kontrolü [LAND_FLARE_SEC]() parametresidir. Bu, uçağın mevcut iniş hızıyla devam ederse yere çarpmadan önceki süre. Uçak eğer 2 m/s'ye iniyorsa ve [LAND_FLARE_SEC]() değerini 3'e ayarlarsanız, uçak yerden 6 metre irtifada palyeye geçer. Palyeyi kontrol etmek için çarpma zamanı kullanılarak, uçak hızla iniyorsa daha yüksek irtifada, yavaşta düşük bir irtifada palyeye geçebilir. Bu palyenin yumuşak iniş yapmasını sağlamaya yardımcı olur.

İkinci kontrol [LAND_FLARE_ALT](). Bu, iniş hızına bakılmaksızın uçağın palyeye geçeceği irtifadır.

Bu iki parametre için uygun değerler, otopilotun irtifayı nasıl hesapladığına bağlıdır. Eğer otopilotun iyi bir mesafe ölçeri (LIDAR gibi) varsa güvenli bir şekilde oldukça küçük sayılar seçebbilir ve zemine yakın palyeye geçebilir. Bu genellikle daha iyi bir iniş sağlar. 
[LAND_FLARE_SEC]() için 1.5, [LAND_FLARE_ALT]() için 2, LIDAR ile başlamak için iyi bir seçimdir. İrtifa için barometre kullanıyorsanız, hatayı hesaba katmak için muhtemelen daha yüksek değerlere ihtiyacınız olacak.

### Süzülüş Açısını Kontrol Etme

glide slope: süzülüş açısı

Palye noktasını ayarlamada bir başka önemli, faktör süzülüş açısıdır. Süzülüş açısı, son waypointten iniş noktasına olan mesafenin ve son waypoint ve iniş noktası arasındaki yükseklik farkının oranıdır. Örneğin, iniş noktası son waypointten 300 metre uzaktaysa ve son waypoint yerden 30 metre yüksekteyse, süzülüş açısı %10'dur.

Süzülüş açısı çok dikse, uçak çarpmayı önleyemek için zamanında palyeye geçemeyecek, ayrıca otopilot uçağı doğru olarak süzülme teşebbüsünde tutamayabilir. En fazla 10%'luk bir süzülüş açısıyla başlamanız önerilir. Uçağınızın kullanabileceği kayma eğimi, pitch kontrolcüsü ayarınızın ne kadar iyi olduğuna, TECS ayarınızın ne kadar iyi olduğuna ve istediğiniz iniş hızına bağlıdır.

Uçağınızın istenen süzülüş açısını tam olarak yapmadığını tespit ederseniz, o zaman öncelikle günlüklerinizde pitch ayarlarını kontrol edin, ve iniş sırasında birkaç derece içinde istenen ve ulaşılan pitch eşleştiğinden emin olun. Eşleşmemesi halinde, pitch ayarlarıyla ilgili belgelere gözatın (veya bi ihtimal AUTOTUNE yeniden çalıştırın). Talep edilen ve ulaşılan pitch eşleşirse, hava hızının doğruluğunu kontrol etmek için TECS günlüklerinizi kontrol etmelisiniz.


### İniş Hava Hızı

landing approach: iniş yaklaşma hızı (süzülüş açısından gelen hız)
stall speed: motorlar durmuş haldeyken iniş hızı
landing speed: iniş hızı

Otomatik iniş, hava hızı sensöründen büyük ölçüde destek alır. Hava hızı sensörü kullanıldığında, iniş yaklaşma hızı (süzülüş açısından gelen hız) [TECS_LAND_ARSPD]() parametresi tarafından kontrol edilir, m/s olarak.

[TECS_LAND_ARSPD]() için uçağınızın motorlar durmuş haldeyken iniş hızının üstünde bir değer seçmeniz gerekir. Motorlar durduğunda iniş hızının uçağınızın ağırlığına bağlı olduğundan, uçağın ağırlığını önemli ölçüde değiştirirseniz (batarya veya kamera eklemek gibi) iniş hızını ayarlamanız gerekeceğini unutmayın.

İnişi daha da iyileştirmek için, palyeden hemen önce hava hızını azaltmak için Ön-Palye(Pre-Flare) kullanabilirsiniz. Bu [LAND_PF_ALT]() veya [LAND_PF_SEC]()'e belirli bir irtifada veya tahmini bir saniyede ön-palye durumuna girmek üzere ayarlanmasıyla etkinleştirilir. Ön-Palye tetiklendiğinde istenen hava hızı [LAND_PF_ARSPD]() olur. Bu değer [TECS_LAND_ARSPD]()'den düşük, ancak stall speedden yüksek olmalıdır. Bu reverse thrust olduğu durumlarda faydalıdır. Bununla birlikte, bazı uçaklar stall landing gerçekleştirebilir bu nedenle düşük bir sayıya (1) ayarlamak, uçağa palyeye geçmeden önce mümkün olduğunca hava hızı kadar gaz boşaltır. 

### Yaklaşma kontrolü

landing approach: iniş yaklaşması

İniş yaklaşması sırasında otopilotun istenen hava hızını ([TECS_LAND_ARSPD]() ile belirlenen) ve istenen süzülüş açısı ve iniş pozisyonu (önceki waypoint ve son waypoint noktası tarafından belirlenen) dengelemesi gerekir. Varsayılan yapılandırma bu iki talebi dengelemeye çalışır, ancak bazı uçaklarda diğerine öncelik vermek isteyebilirsiniz.

Hava hızı kontrolünün yükseklik kontrolüne karşı önceliği [TECS_LAND_SPDWGT]() parametresi kullanılarak belirlenir. 1 değeri(varsayılan) ikisi arasında denge demektir. İkiye yakın bir değer, hava hızına daha yüksek öncelik verirken, sıfıra yakın bir değer yükseklik kontrolüne öncelik verir. Örneğin stall speed'e daha yakın bir hızda iniş yapıyorsanız, hava hızı kontrolüne öncelik vermek isteyebilirsiniz. Bunu yapmak için [TECS_LAND_SPDWGT]() değerini 1.9 gibi bir değere ayarlamanız gerekir.

If what you want in a landing is precision in the position where it lands then you should set TECS_LAND_SPDWGT to a low number, such as 0.2 or even 0.0. In that case the plane will still try to achieve the target landing airspeed by using the throttle, but it will not try to control airspeed with pitch.

Bir planör (veya motorsuz herhangi bir uçağı) iniş yaptırıyorsanız, [TECS_LAND_SPDWGT]()'yi 2.0'a ayarlamalısınız, böylece hava hızı öncelikli olur ve hava hızını kontrol etmek için pitch kullanılır.

In most cases a value of -1 gives the best result. This special value will auto-adjust the value during the landing, scaling it from your normal TECS_SPDWEIGHT value down to zero at the point of landing. So up in the sky during approach you maintain good airspeed but by the time you land the emphasis is on a more accurate landing.


### Palyeye geçiş kontrolü

flare: palyeye geçmek
TECS: toplam enerji kontrol sistemi

İnişin son aşamasına "palye" denir. Palyeye geçiş sırasında uçak, son waypoint ile iniş waypointi arasındaki çizgi boyunca rota tutmaya çalışır ve sadece hedef iniş hızını kullanarak yüksekliği kontrol eder.

Uçuş kontrolcüsünün palyeye geçişteki ana görevi, TECS_LAND_SINK parametresinde belirtilen iniş hızını elde etmeye çalışmaktır. Bu, varsayılan olarak 0.25 m/s değeridir ve çoğu model için makul iniş anındaki dikey hızdır. Bu hıza ulaşmak için TECS kontrol kontrolcüsü sadece motor sıfıra zorlandığında pitch kontrolünü  kullanır.

Uçağın istenilen iniş hızına ulaşmasını etkileyen temel parametreleri LAND_PITCH_CD, TECS_LAND_DAMP ve ana pitch ayar parametreleridir.

LAND_PITCH_CD parametresi palyeye geçişteki minimum pitch hedefini ayarlar (santigrad derece). Bu parametre daha çok uçağın şekline özgüdür ve iniş anında uçağın iniş takımlarına zarar görmesini veya pervanenin kırılmasını engellemek üzere uçağın burnunun çok aşağıya inmesini engellemek için tasarlanmıştır. Çoğu uçak için küçük pozitif bir sayı olmalıdır(örneğin 300, 3 derece anlamına gelir), ancak bazı gövde üzerine iniş yapan uçaklar için, palye yerden çok uzaktaysa irtifa kaybetme ihtimalini azaltmak üzere burnun az miktarda aşağıda tutulmasını sağlamak için küçük negatif bir sayı iyi olabilir.

TECS kontrolcüsü iniş hızını kontrol etmeye çalıştığında uçağom gerçek pitch'inin LAND_PITCH_CD'den biraz daha yüksek olabileceğini unutmayın. Maksimum pitch, 0 değilse TECS_PITCH_MAX tarafından aksi takdirde LIM_PITCH_MAX tarafından kontrol edilir.

TECS_LAND_DAMP parametresi palye sırasındaki pitch kontrolü için bir 	sönüm katsayısıdır. Daha büyük bir sayı, pitch talebinin daha yavaş değişmesine neden olur. Bu parametre palye gerçekleştiğinde ani adım değişiklikleriyle ilgili sorunları azaltmak için kullanılabilir.

### Palye sonrası


Uçak palyeye geçtikten sonra hareket etmeye devam eder, ancak sıfır gazda. Navigasyon yönü, iniş noktasından son waypointe doğru tahmin yürütülen çizgidir. Navigasyon roll'ünün kanadı çarpmasını önlemek için LEVEL_ROLL_LIMIT ile sınırlı olacağına, bu nedenle önemli bir çapraz rüzgar varsa uçağın yolda düzgün olarak devam edemez.

Uçağınız sürekli uzun iniş yapıyorsa (çeşitli nedenlerden dolayı olabilir), o zaman TECS_LAND_SRC'yi, havada irtifa kaybı (negatif) veya aşağıya iniş (pozitif) zorlamaya ayarlayabilirsiniz.

Uçak LAND_DISARMDELAY saniye boyunca hareket etmeyi kestiğinde (varsayılan 20 saniye) motoru disarm eder. İsteğe bağlı olarak, LAND_THE_NEUTRL ayarlayarak LAND_DISARMDELAY tetiklendiğinde servo hareketini devre dışı bırakabilirsiniz.

### Uzaklıkölçer kullanımı

Uçağınıza bir uzaklıkölçer taktıysanız daha düzgün bir landing kontrolü için kullanabilirsiniz. Uzaklıkölçerin inişte kullanılmasına izin vermek için, RNGFND_LANDING parametresini 1 olarak ayarlamanız gerekir.

İniş için bir uzaklıkölçer kullanırken, uzaklıkölçer tarafından verilen rakım yalnızca iniş yaklaşmasında ve palye noktasını belirlemek için kullanılır ve uçağın süzülüş eğimini daha doğru şekilde takip etmesini ve doğru zamanda palyeye geçmesini sağlamak üzere tasarlanmıştır.


Ayrıca, daha uzun menzilli uzaklıkölçeriniz varsa, o zaman uzaklıkölçerin minimum menzilini sıfırın üstünde ayarlamak iyi bir fikirdir. Örneğin, PulsedLight Lidar'ın 40 metreden fazla menzili vardır ve yanlış okuma yaptığında, 1 metreden daha az aralıkları okumaya meyillidir. RNGFND_MIN_CM parametresinin 150 ye ayarlanması, 1.5 metrenin altındaki tüm uzaklıkölçer değerlerini gözardı eder ve Lidar'ın iniş için sağlamlığını büyük ölçüde geliştirir.

### İnişi iyileştirmek


İyi bir inişin anahtarı, yerden ne kadar uzakta olduğunu bilen otopilottur. Varsayılan kurulumda, irtifayı tespit edebilecek tek sensör barometredir. Ne yazıkkı barometreler üç ana hatadan muzdariptir:

-  atmosferik basınçtaki değişiklikler nedeniyle barometrik kayma
-  otopilot elektroniğinin sıcaklığındaki değişikliklerden dolayı barometrik kayma
-  barometre etrafındaki hava akışından kaynaklanan yerel basınç değişimlerinden dolayı barometrik hata

İyi otomatik iniş için ideal kurulum Lidara sahip olmaktır. Lidar, zemine olan mesafeyi çok doğru bir şekilde ölçebilir ve sürüklenmeden zarar görmez. Eğer bir Lidar kurulu ise RNGFND_LANDING = 1 ile iniş için kullanımını sağlayabilirsiniz.

Lidar takılı değilse, otomatik-iniş ile barometrik hata sorunlarını en aza indirmek için yapabileceğiniz birkaç şey vardır:

-  elektronik elemanlar ısındıktan sonra barometre kalibrasyonu yapın. Bunu Pixhawk ile yapmanın en kolay yolu, uçağı güvenlik şalteri ile disarm etmektir. Uçak disarm edildiğinde, yerde olduğunu varsayar ve barometreyi geçerli basınca sıfırlar.
-  hız ile ilgili basınç değişikliklerine neden olabilecek otopilot üzerinden doğrudan hava akışını önlemeye çalışın
-  daha kısa uçuşlar yapın, hava basıncı değişikliklerine daha az kez izin verin. Günlükleri kontrol edin ve inişin sürekli olarak sıfır irtifada olup olmadığını görün.

Ayrıca gövde üzerine inen uçaklarla, yüzeysel pitch ile iniş ayarlamak ve palyeyi biraz daha yüksek irtifaya ayarlamak için iyi çalışır. Bu, yalnızca motorlar durmuş haldeyken iniş hızının yeterince düşük olması durumunda işe yarar; süzülme bir süre güvenilir şekilde çalışacaktır. 

## DO_LAND_START kullanımı

Bazen RTL'in bir parçası olarak otomatik inişi tetiklemek yararlı olabilir. Bunu yapmak için iki şey yapmanız gerekir:

-  inişe başlamadan hemen önce görevinize DO_LAND_START görev öğesi ekleyin. 
-  RTL_AUTOLAND parametresini 1 veya 2 olarak ayarlayın.

Çalışma şekli, uçak RTL'e girdiğinde, RTL_AUTOLAND parametresinin 1 veya 2 olarak ayarlanıp ayarlanmadığını kontrol eder. Mevcut durumda DO_LAND_START tipi bir görev öğesi aranır. Eğer birisin bulunursa, uçak DO_LAND_START işaretinden hemen sonra görev bölümünden başlayarak otomatik olarak AUTO moda alır ve karaya iner.

Tam davranış RTL_AUTOLAND değerine bağlıdır:

-  eğer RTL_AUTOLAND = 1 ise, uçak ilk önce normal RTL yapar, sonra dönüş noktasını daire için almaya başladığında, DO_LAND_START'tan sonra AUTO görevine geçer ve iniş yapar.
-  eğer RTL_AUTOLAND = 2 ise, uçak RTL'yi tamamen atlayarak doğrudan iniş sıralamasına girer. 

İsteğe bağlı olarak, görevinize birden fazl DO_LAND_START öğesi ekleyebilirsiniz. Bu yapılırsa, DO_LAND_START görev öğelerinin enlem/boylamları iniş kullanılarak iniş sıralaması seçilir.  Geçerli konuma en yakın DO_LAND_START kullanılır. Farklı rüzgar koşulları veya farklı alanlar için birden fazla iniş diziniz varsa, bu faydalı olabilir.

## Otomatik-iniş nasıl iptal edilir

İniş sıralamasını güvenli ve kontrollü bir şekilde iptal etmenize izin veren bir iniş iptal mekanizması bulunmaktadır. Özel iptal durumu, görevin bir parçası olarak önceden programlanabilir veya varsayılan iptal mekanizması kullanılabilir. Bu özelliği etkinleştirmek için LAND_ABORT_THR = 1 ayarlayın.

Bu özellik üç adımdan oluşur:

1. İptali tetiklemek
2. İptal sırasındaki davranış
3. İptal tamamlandıktan sonra görev durumu

### Adım 1) İniş iptali tetikleyicileri

Otomatik iniş iptalini tetiklemenin üç yolu vardır. Hepsi sadece AUTO modda iken ve mevcutta bir LAND waypoint görev öğesi yürütülüyorsa çalışır:

* __YKİ kullanarak MAV_CMD_DO_GO_AROND komutunu gönderin.__ MP'ın FlightData ekranındaki Eylemler sekmesinde "Abort Landing" düğmesi bulunur.
* __RC Throttle girişi >90%.__ Bu AUTO modda iken iptali tetikleyecektir. Throttle'ı tetiklemek için sadece kısa bir süre high olması gerekir. Low'a çekmeyi unutmayın!
* __Mod değişimi.__ İnsan pilotlu iniş iptali için AUTO moddan, örneğin MANUEL/STABILIZE/FBWA moduna geçebilir ve istediğiniz gibi güvenle uçağı yönlendirebilirsiniz. Bu yöntemi kullanmak, Adım 2 yi atlayacaktır, çünkü elle yapılır. AUTO'ya geri dönmeniz durumunda görev aşağıdaki Adım 3 açıklandığı gibi devam edecektir.

### Adım 2) İniş iptali uçuş davranışı

Varsayılan iptal davranışı oto-takeoff simüle etmektir: pitch en az 10 derece arttırın ve throttle'ı TKOFF_THR_MAX değerine ayarlayın ve 30m hedef irtifaya ulaşana kadar doğrultuyu sabit tutun. Özelleştirilmiş bir davranışa izin vermek için pitch ve irtifayı geçersiz kılmak mümkündür.

- Pitch minimum. Bu görevde şimdiye kadar yürütülen bir NAV_TAKEOFF varsa, aynı adım burada tekrar kullanılacaktır.
- Hedef irtifa. NAV_LAND param1> 0 ise, metre cinsinden hedef irtifa olarak kullanılır. Değilse NAV_TAKEOFF bu görevde daha önce çalıştırıldıysa, aynı yükseklik burada tekrar kullanılacaktır.
  
Bu adım, iptal tetikleme mod değişikliği ile yapılırsa atlanır, çünkü pilotun manuel olarak devraldığı ve uçağı seçtikleri thorttle ve pitch ile güvenli bir irtifaya uçurduğu varsayılır.

### Adım 3) İniş iptali tamamlandıktan sonra görev durumu

İptal edilen bir iniş tamamlandığında, ya hedef irtifaya ulaşarak ya da tekrar AUTO moduna geçerek görev dizini değişmiş olacaktır ve artık NAV_LAND komutunu yürütme kalkar. Görev dizini bu üç seçenekten biri olacak ve sırayla kontrol edilecektir:

- NAV_LAND görev öğesini param1 = 0 veya 1 olan CONTINUE_AND_CHANGE_ALT görev öğesini izlerse, görev indeksi bir kez artırılır ve normal şekilde çalıştırılır. Bunu, özel planlı görev davranışları için iptal sonrası görev planlaması izleyebilir.
- Eğer DO_LAND_START görevde varsa, o zaman bu indekse atlanır.
- Aksi halde görev indeksi NAV_LAND'tan önceki indeks olacak şekilde bir azaltılır. Bu aynı iniş yaklaşımını tekrarlamasını sağlayacaktır.


## Ters İticili İniş (Reverse-Thrust Landing)

Bazı ESC'ler yönü ters çevirmeye izin verir. Pervane üzerinde ters çevirme kullanıldığında, hava hızınızı azaltmak için kullanılabilecek bir negatif itme meydana getirecektir. Dik iniş(steep landing) yaklaşması sırasında, bu yöntem çok daha yumuşak ve hassas bir şekilde iniş yapmanıza izin veren sabit ve düşük hava hızını korumak için kullanılabilir. Bu özelliği kullanmak için, doğru bir yükseklik için havahızı sensörü ve uzaklıkölçer kullanılması şiddetle tavsiye edilir.

Aşağıdaki video, 15 derecelik bir eğimle otomatik iniş paan Skywalker X8 örneğidir. Hedef, son pozisyon hatasının GPS konum hatası tarafından belirlendiği, tekrarlanabilir yüksek hassasiyetli inişlerin mümkün olduğunu gösteren, zemindeki başlıktır. Bu özel uçak 20deg ve 25 deg eğimde' de iniş yaptı. YMMV uçağın ağırlığından ve mevcut pervane/motordan itme elde edilebilir. Bir SkywalkerX8 tipik olarak, 6 ila 10 derece gibi sığ bir eğime ihtiyaç duyar.

https://www.youtube.com/watch?v=kdw8vjbttNo


### Anahtar Parametreler


Bölüm 1.1'de belirtilenlere ek olarak ters iticili inişi kontrol eden temel parametreler şunlardır:

- LAND_PF_ALT
- LAND_PF_SEC
- LAND_PF_ARSPD
- USE_REV_THRUST
- TECS_APPR_SMAX
- RC3_TRIM
- THR_MIN


### ESC (Elektronik Hız Kontrolcüsü)

Donanım seçimi ve programlama
++++++++++++++++++++++++++++++++++

Çoğu ESC düz ve ters yönde çalışabilir, ancak bu genellikte bir stok özellik değildir ve bunu yapmak için yeniden programlanması gerekebilir. Herhangi bir SimonK ve BLHeli uyumlu ESC, ters itmeyi desteklemek için flaşlanabilir.

[İşte BLHeli uyumlu olanlar hakkında bilgi.](https://blhelisuite.wordpress.com/)

Donanım yapılandırması
++++++++++++++++++++++

NOT: ESC'leri ve itme parametrelerini yapılandırırken pervaneyi çıkarın.

ESC'nizi nötr noktasını değiştirerek ters itme için yapılandırın. Birço ESC, bunu gerçekleştirmek için özel ürün yazılımı gerektirir. Özel ESC'nizi nasıl yapılandıracağınız ile ilgili talimatlar için Google bakın.

Şunları ayarlayın:

1. Minimum PWM 1000, ortası 1500 ve maksimum 2000.
2. THR_MIN'i -100 gibi negatif bir değere. Daha sonra RC3_TRIM'i (veya RCMAP_THROTTLE üzerinden kısmak üzere eşlendiği RCx'İ) ESC'nizin orta değerine ayarlayın.

### Maksimum süzülüş açısı belirleme

Dik bir iniş yaklaşması için sınırlama, istenen hava hızını ne kadar iyi koruyabileceğinizdir. Bu, uçağınızın ters itme (motor + destek itme kabiliyeti) yaratma kabiliyeti ve yavaşlamaya karşı direnciyle (uçak kütlesi) belirlenir. Çoğu durumda aşırı diklik gereksizdir, ancak mümkündür. Aşırı büyüklükte bir motor ve hafif bir uçakla 60 dereceye kadar dik gelebilirsiniz.

En dik yalşma açınızı belirlemek için, TECS_APPR_SMAX'ı sizi sınırlandırmayacak kadar yüksek ayarlayın (örn. 99). Ardından, normal yaklaşıma göre daha dik bir görev planlayın(15 dereceyi deneyin ve daha da yükseltin). Hava hızınızı yaklaşırken izleyin - uçak mevcut ters throttle menzilinin %75 ini aşmadan TECS_LAND_ARSPD'i koruyabilmelidir. Aksi halde, uçağınızın negatif itme-kütle oranı için çok dik geliyorsunuz. 

### Ön palye ayarlama

Bir uzaklıkölçer ve havahızı sensörleri takılıyken, ön palye noktasında doğru hava hızı ve irtifa okuması olacaktır. Bu bize momentumumuz hakkında iyi bir fikir verir ve nihai patlamaya karşı kararlı “başlangıç koşulları” sağlar. LAND_PF_ALT (veya LAND_PF_SEC) 'yi oldukça yüksek bir noktaya ayarlayın (örneğin 10 m) ve oraya adapte edin. 

LAND_PF_ALT'a ulaşıldığında hava hızı talebi anında TECS_LAND_ARSPD'den LAND_PF_ARSPD'ye gidecektir. Bu, hava hızını istenen hava hızına indirgeyecek şekilde artan ters itme ile frenlere çarpmasına neden olur.

İşin püf noktası, LAND_FLARE_ALT'da (bu biraz düşük bir irtifada meydana gelir - yaklaşık 1 veya 2 metre) throttle'ı kesmeden önce LAND_PF_ALT'ı LAND_PF_ARSPD'e ulaştığı bir irtifaya ayarlamaktır.

Örnek, TECS_LAND_ARSPD = 15, LAND_PF_ARSPD = 12, LAND_PF_ALT = 12, LAND_FLARE_ALT = 2. Eğiminize, uçak kütlesine ve motor+pervanenin itme kabiliyetine bağlı olarak, uçağın 10m den 2m ye düşerken hava hızını 15m/s den 12m/s düşürmesini beklemelisiniz. Bunlar, 2m irtifanın altında yumuşak ve yavaş bir palyeye geçiş için ayarlanacak kritik paragraflardır.


### Palye

Artık palyeyi sabit ve tahmin edilebilir bir hava hızıyla başlattığınıza göre palyeyi kontrol etmek çok daha kolaydır. Palyenizi önceden oto-iniş için ters itme olmadan ayarladıysanız, yeniden ayarlamak isteyeceksiniz. Çok daha yavaş geldiğinizi fark edeceksiniz, ve ayarlaması daha kolay olacaktır.


Uçağın gerçek stall hızını belirleme
+++++++++++++++++++++++++++++++++++++++++++++++

Ne yaptığınızı gerçekten bilmiyorsanız, stall hızını tahmin etmek zor olabilir. Geleneksel olarak, bu gerçek değeri belirlemek için, motorlar kapanana kadar hava hızınızı yavaşça azaltmanız gerekir ancak bu, uçağın aşağıya çakılmasına neden olabilir.

LAND_PF_ALT ve LAND_PF_ARSPD ile stall hızınızı yerden çok daha düşük bir şekilde kontrol edebilirsiniz. Motorların durduğu anda hava hızını bilmek için, gerçek roll ve istenen roll karşılaştırılarak kanadın kalkış ve inişteki hava hızı için veri günlüklerinizi kontrol edin.
