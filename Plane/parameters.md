# PARAMETRE LİSTESİ
> tune: kanal ayarı  
> smoothing out: kolaylaştırmak  
> pusher prop: itici pervane  
> forward acceleration: ileri ivme  
> hand launch: elden kalkış  
> velocity: hız  
> ground speed: yer sürati  
> airspeed: hava sürati  
> slew rate: yetişme hızı  
> heading: uçağın burun yönü (pusula yönü) derece olarak ifade edilir.
> track: uçağın uçtuğu yön
> avoidance calculation: kaçınma hesaplaması
> emitter: yayıcı
> transceiver: alıcı-verici
> geofence: coğrafi sınırlama
> attitude: durum

## ArduPlane Parametreleri

**`AUTOTUNE_LEVEL: autotune düzeyi`**  

Pitch ve Roll PID'lerinin agresiflik seviyesi. Düşük değerler 'daha yumuşak' ayar sağlar. Çoğu uçak için Seviye 6 önerilir.

| Aralık | Artış |
|:------:|:-----:|
|  1-10  |   1   |

**`TELEM_DELAY: telemetri başlangıç gecikmesi`**  

Bir Xbee'nin güç açık durumunda kullanılamaz hale getirilmesini önlemek için radyo telemetrisini geciktirme süresi (saniye).

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|  1-10  |   1   |saniye |

**`KFF_RDDRMIX: telemetri başlangıç gecikmesi`**  

Aileron hareketi sırasında eklenecek rudder miktarı. ~Increase if nose initially yaws away from roll. Reduces adverse yaw.~

| Aralık | Artış |
|:------:|:-----:|
|  0-1   | 0.01  |

**`GLIDE_SLOPE_MIN: minimum süzülüş eğimi`**  

Bu, şimdiki irtifa değişikliği yerine süzülüş eğimi kullanılmadan önce/önceki bir waypointin minimum irtifa değişikliğini kontrol eder. Varsayılan değer 15 metredir, küçük irtifa değişikliklerinin gerçekleştiği waypointlerin yakınında waypoint görevlerini düzeltmeye yardımcı olur. Eğer süzülüş eğimini görevlerde kullanmak istemiyorsanız, sıfıra ayarlayabilirsiniz, süzülüş eğimi hesaplamalarını devre dışı bırakacaktır. Aksi takdirde, bunu süzülüş açısı irtifa değiştirmek için kullanılmadan önce irtifa hata metresini minimum sayıya ayarlayabilirsiniz.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-1000  |   1   | metre |

**`GLIDE_SLOPE_THR: Süzülüş eğimi eşiği`**  

Süzülüş eğimini yeniden oluşturmadan (rebuilding) önce uçağın olabileceği süzülüş eğiminin üzerindeki yüksekliği kontrol eder. Bu otomatik takeoff'u kolaylaştırmak için kullanışlıdır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-100   |   1   | metre |

**`TKOFF_THR_MINSPD: Takeoff throttle minimum hızı`** 

Otomatik takeoff'ta throttle'ı bastırmayan/önlemeyen hız kontrolü tarafından kullanılan m/s cinsinden minimum GPS yer sürati. Bu, motorun uçağın mancınığı terk etmesinden sonra devreye alınmasını istediğiniz mancınık fırlatmalarında kullanılabilir, ancak GPS ölçümleriyle ilgili hatalar nedeniyle mancınık başlatmalarında TKOFF_THR_MINACC ve TKOFF_THR_DELAY parametrelerinin kullanılması tercih edilir. İtici pervaneyle elden kalkışlarda, vaktinden önce motorun çalışmasına karşı ek koruma sağlamak için bu parametrenin 4m/s den daha az olmayan bir değere ayarlanması şiddetle tavsiye edilir. GPS süratinin gerçek sürati yaklaşık 0.5 saniye geciktireceğini unutmayın. Zemin hızı kontrolü, TKOFF_THR_DELAY parametresi tarafından ertelenir.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s   |

**`TKOFF_THR_MINACC: Takeoff throttle minimum ivme`**  

Otomatik takeoffta yer sürati kontrolü arm etmeden önce m/s/s cinsinden minimum ileri ivme. Bu, elden kalkışlarda kullanılmak içindir. 0 olması, ivme testini devre dışı bırakır, Bu GPS hız atlamalarının motorun çalıştırılmasına izin verebilecek yer sürati kontrolünü her zaman arm edeceği anlamına gelir. Elden kalkışlarda ve bungee kalkışlarda 15 civarında ayarlanmalıdır. Ayrıca tam "arm için sallanma" kontrolü için TKOFF_ACCEL_CNT parametresine bakın.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s2  |

**`TKOFF_THR_DELAY: Takeoff throttle gecikmesi`**  

Bu parametre, TKOFF_THR_MINACC tarafından kontrol edilen ileri ivme kontrolden sonra, yer sürati kontrolünün geciktirileceği zaman gecikmesini (saniyenin 1/10'unda) ayarlar. İtici pervanelerle elden kalkış için motor çalışmaya başkamadan önce uçağın atıcılarının güvenli şekilde arm edilmesini sağlamak için bunun 2 (0.2 saniye) olmayan bir değere ayarlanması önemlidir. Bungee kalkışları için, bungee'nin motor çalıştırılmadan önce uçaktan salınması için zaman vermek üzere daha büyük değer kullanılabilir (30 gibi).

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-127    | 1   | desisaniye  |

**`TKOFF_TDRAG_ELEV: Takeoff taildragger elevator`**

Bu parametre kalkışın ilk aşamasında uygulanacak elevator miktarını belirler. Kalkışın başlangıç aşamalarında maksimum dümen vermek için, ilk takeoff aşamasında bir taildraggerin kuyruk tekerleğini zeminde tutmak için kullanılır. Bu seçenek, yer dümen kontrolcüsünün ayarlanmasıyla birlikte TKOFF_TDRAG_SPD1 seçeneği ve GROUND_STEER_ALT seçeneği ile kombine edilmelidir. Sıfır değeri, kalkıştaki ilk "kuyruk tutma" aşamasını atlamak anlamına gelir. Elden veya mancınık başlatmaları için sıfıra ayarlayın. Taildraggerlar için normalde 100'e ayarlamalısınız, yani takeoff'un ilk aşamasında tam elevator anlamına gelir. Çoğu tricycle undercarriage için sıfır değeri iyi çalışır, ancak bazıları için küçük negatif bir değer (-20 ila -30 civarı) ilk ivmede burun tekerleğini sıkıcı yere sabitleyen elevator down uygulanacaktır. Burun tekerinin kalkışta iyi şekilde tutunmadığını tespit ederseniz negatif değer kullanın. Tricycle undercarriage aşırı down elevator kullanmak uçak burun tekerleğiyle döndüğü için dümende dengesizliğe neden olabilir. Bir seferde yüzde 10 down elevator ekleyin.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-100-100    | 1   | yüzde  |

**`TKOFF_TDRAG_SPD1: Takeoff tail dragger hız1`**

Bu parametre, kuyruğu zeminde tutmayı bırakacak ve zeminde dümen kontrolüne geçiş yapacağı hava hızını ayarlar. TKOFF_TDRAG_SPD1'e ulaşıldığında uçağın pitch seviyesini TKOFF_ROTATE_SPD ulaşılana kadar korur, bu noktada görevde belirtilen takeoff pitch'i kalkış tırmanışı için pitch döndürmek için kullanılacaktır. Doğrudan dönüşe geçmek için TKOFF_TDRAG_SPD1'i sıfıra ayarlayın. Bu, elden kalkışlar ve mancınık fırlatmaları için sıfıra ayarlanmalıdır. Ayrıca, burun tekerleğini tutmak için yukarıdaki yöntemi kullanmıyorsanız, tricycle undercarriage uçaklarda sıfıra ayarlanmalıdır. Taildragger uçaklar için stall hızının hemen altına ayarlanmalıdır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s  |

**`TKOFF_ROTATE_SPD: Takeoff dönüş hızı`**

Bu parametre, görevde belirlenen tırmanma mesafesini ayarlayarak uçağın "döneceği" hava süratini belirler. TKOFF_ROTATE_SPD sıfır ise, takeoff başlar başlamaz tırmanış pich kullanılacaktır. El ve mancınık fırlatmaları için TKOFF_ROTATE_SPD sıfır olmalıdır. Tüm zemin kalkışları için TKOFF_ROTATE_SPD stall hızının üstünde, genellikle %10 ila %30 arasında ayarlanmalıdır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s  |

**`TKOFF_THR_SLEW: Takeoff throttle değişim hızı`**

Bu parametre otomatik takeoff'ta throttle değişim hızını ayarlar. Sıfır olduğunda, kalkış sırasında THR_SLEWRATE parametresi kullanılır. Roll takeofflar için, zemin dümen kontrolünü iyileştirebilecek daha yavaş bir ivmelenme sağlamak üzere takeoff için daha düşük değişim hızı ayarlamak iyi bir fikirdir. Değer saniyede yüzde throttle değişimidir, bu nedenle 20 değeri, throttle'ı kalkışta 5 saniyenin üzerinde arttıracağı anlamına gelir. 20 'nin altındaki değerler, uçağın çok az throttle kullanarak tırmanmaya çalışmasına neden olabileceğinden önerilmez. -1 değeri, kalkışta dönüş hızı sınırının olmadığı anlamına gelir.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-1-127    | 1   | saniye başına yüzden  |

**`TKOFF_PLIM_SEC: Takeoff pitch limit düşürme`**

Bu parametre, otomatik takeoff'un minimum pitch sınırını hedef irtifaya ulaşmadan birkaç saniye önce azaltır. Bu, uçuş kontrolcüsünün hedef yüksekliğe ulaşmadan birkaç saniye önce dengelemeye başlamasına izin vererek hedeften sapmayı azaltır. Sıfır olarak ayarlandığında, görev pitch minimumu yol boyunca hedef irtifaya zorlanır, aksi takdirde, pitch minimumu yaklaşma bölümünde yavaşça sıfıra düşer. Bu pitch_min değeridir, talep(demand) değildir. Uçuş kontrolcüsünün kalkış işlemini tamamlamak için irtifa kazanmaya devam etmesi gerekir, ancak bu parametre ile olmak istediğinden daha fazlasına zorlanmaz.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-10    | 0.5   | saniye|

**`TKOFF_FLAP_PCNT: Takeoff flap yüzdesi`**

Otomatik kalkışta uygulanacak flap miktarı.

| Aralık | Birim |
|:------:|:-----:|
|0-100   | yüzde |


**`LEVEL_ROLL_LIMIT: Yatay uçuş roll sınırı`**

Bu, inişin son aşamalarında ve otomatik takeoff sırasında olduğu gibi, yatay uçuş istenen uçuş modları sırasında derece cinsinden maksimum yatış açısını kontrol eder. Kalkış veya iniş sırasında kanatların piste çarpmasını önlemek için küçük bir açı (5 derece gibi) olmalıdır. Bunu sıfıra ayarlamak, otomatik kalkış ve son iniş yaklaşmasında rota tutumunu tamamen devre dışı bırakacaktır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-10    | 0.5   | saniye|


**`WP_MAX_RADIUS: Waypoint maksimum yarıçap`**

Tamamlanmış sayılan waypoint için bir waypointe maksimum uzaklığını ayarlar. Bu, normalde bir waypointin tamamlandığını düşünmek için kullanılan "bitiş çizgisini geç" mantığını geçersiz kılar. Normal AUTO davranış için bu parametre sıfıra ayarlanmalıdır. Sıfır olmayan bir değerin kullanılması, yalnızca uçağın verilen yarıçap içine yaklaşması kritik olduğunda ve tamamlanana kadar etrafta dolaşılması gerektiğinde önerilir.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0 - 32767	   | 1   | metre|

**`WP_LOITER_RAD: Waypoint loiter yarıçapı`**

Waypoint merkezinden uzaklığı tanımlar, uçak loiter sırasında sürdürür. Bu değer negatifse, varsayılan loiter saatin tersi yönünde olur.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-32767 - 32767	    | 1   | metre|

**`RTL_RADIUS: RTL loiter yarıçapı`**

RTL modundayken loiter dairesinin yarıçapını tanımlar. Eğer bu sıfır ise, WP_LOITER_RAD kullanılır. Yarıçap negatifse, saatin tersi yönünde yapılır. Eğer pozitifse, saat yönünde loiter yapılır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-32767 - 32767	    | 1   | metre|


**`ARSPD_FBW_MIN: Minimum hava sürati`**

Otomatik throttle modlarında talep edilen minimum hava sürati. Uçuş stall hızından %20 daha yükseğe ayarlanmalıdır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|5 - 100    | 1   | m/s|

**`ARSPD_FBW_MAX: Maksimum hava sürati`**

Otomatik throttle modlarında talep edilen maksimum hava sürati. Hassas TECS irtifa kontrolü sağlamak için THR_MAX'taki yatay uçuş hızından biraz daha düşük, ARSPD_FBW_MAX'ın en az %50 üzerine ayarlanmalıdır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|5 - 100   | 1  | m/s|

**`TERRAIN_FOLLOW: Use terrain following`**

Bu, CRUISE modu, FBWB modu, RTL ve ralli noktaları için araziyi takip eder. Bu seçeneği kullanmak için, ayrıca YKİ'den arazi verilerini almayı sağlayan TERRAIN_ENABLE değerini 1'e ayarlamanız ve uçağa arazi verileri göndermeyi destekleyek YKİ kullanmanız gerekir. Arazi takibi etkinleştirildiğinde CRUISE ve FBWB modu, ev konumundan yükseklikten ziyade zeminden yüksekliği tutar. RTL'de, kalkış yerine dönüş irtifası, arazinin üstündeki yükseklik olarak kabul edilir. Rally noktası irtifaları arazinin üstündeki yükseklik olarak alınır. Bu seçenek, ev konumunun üstündeki yüksekliği mi yoksa arazinin üstündeki yüksekliği mi olduğu konusunda waypoint bayrağı taşıyan görev öğelerini etkilemez. Görevlerde arazi takibi kullanmak için görevi oluştururken waypoint türünü arazi yüksekliği waypointi olarak ayarlayabilecek bir yer istasyonuna ihtiyacınız vardır.

| Değer | Anlamı |
|:------:|:-----:|
|0    | Pasif  |
|1    | Etkin  |

**`THR_MIN: Minimum throttle`**

THR_PASS_STAB ayarlanmadığı sürece, manuel hariç tüm modlarda kullanılan minimum thorttle yüzdesi. Negatif değerler, donanım destekliyorsa ters itme yapar.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-100-100    | 1   | yüzde|

**`THR_MAX: Maksimum throttle`**

Otomatik throttle modlarında kullanılan maksimum throttle yüzdesi.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-100    | 1   | yüzde|

**`TKOFF_THR_MAX: Takeoff için maksimum throttle`**

Otomatik kalkış sırasında maksimum throttle ayarı. Eğer sıfırsa, THR_MAX kalkış içinde kulalnılır.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-100   | 1   | yüzde|

**`THR_SLEWRATE: Throttle yetişme hızı`**

Throttle'daki maksimum saniye başına yüzde değişimi. Döngü başına 1 mikrosend servo artışına dayalı alt limit. Ulaşılabilir minimum değeri belirlemek için SCHED_LOOP_RATE değerini yaklaşık 10'a böl.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-127    | 1   | saniye başına yüzde|

**`FLAP_SLEWRATE: Flap yetişme hızı`**

Flap çıkışındaki maksimum saniye başına yüzde değişimi. 25 ayarlamak, flap'in bir asniyede tam flap aralığının %25'ten daha fazla değiştirilmemesi anlamına gelir. 0 değeri, hız sınırlaması olmaması anlamına gelir.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-100    | 1  | saniye başına yüzde|

**`LIM_ROLL_CD: Maksimum yatış açısı`**

Stabilize limitleri olan modlarda kumanda edilen maksimum yatış açısı. Daha keskin dönüşler için bu değeri arttırın, ancak ivmeli stall'ları önlemek için azaltın.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0 - 9000	    | 1  | santi derece|

**`LIM_PITCH_MAX: Maksimum pitch açısı`**

Stabilize limitlere sahip modlarda kumanda edilen maksimum pitch down açısı.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0 - 9000	    | 1  | santi derece|

**`LIM_PITCH_MIN: Minimum pitch açısı`**

Stabilize limitlere sahip modlarda kumanda edilen minimum pitch down açısı.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-9000 - 0	    | 1  |  santi derece|

**`GROUND_STEER_DPS: Yer dümen hızı`**

Tam rudder için saniye başına derece cinsinden yer dümen hızı.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|10 - 360   | 1   | derece/saniye|

**`HOME_RESET_ALT: Ev konumu ayarlama irtifa eşiği`**

Uçak, ev waypointinin bu irtifası içinde olduğunda, disarm durumda iken, otomatik olarak ev konumunu güncelleyecektir. Sürekli olarak yeniden ayarlamak için 0 olarak ayarlayın.

| Aralık | Değerler | Birim |
|:------:|:-----:|:-----:|
|-1-127  | -1: Yeniden ayarlama, 0: Her zaman yeniden ayarla   | metre|

**`TKOFF_ACCEL_CNT: Takeoff throttle ivme sayısı`**
Bu, TKOFF_THR_MINACC ile arm etmek için gereken ivme olaylarının sayısıdır. Varsayılan değer olan 1, TKOFF_THR_MINACC'ın üstünde tek bir ileri ivmenin devreye gireceği anlamına gelir. Bunu 1'den daha yükseğe ayarlarak arm için daha fazla ileri/geri hareketi talep edebilirsiniz.


| Aralık |
|:------:|
|1-10    |

**`TKOFF_TIMEOUT: Takeoff zaman aşımı`**

Bu otomatik kalkış için zaman aşımıdır. Eğer bu sıfır değilse ve uçak bu süre içinde en az 4 m/s'lik bir yer hızına ulaşmazsa, kalkış iptal edilir ve araç disarm edilir. Değer sıfır ise, zaman aşımı geçerli olmaz.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-120   | 1     | saniye|



## ADSB_ Parametreleri

**`ADSB_ENABLE: ADSB'yi etkinleştir`**

ADSB'yi etkinleştirir.

| Değer | Anlamı |
|:------:|:-----:|
|0   | Pasif     |
|1   | Etkin     |

**`ADSB_LIST_MAX: ADSB araç listesi büyüklüğü`**

En yakın araçların ADSB araç listesi büyüklüğü. Uzun listelerin düşük SRx_ADSB değerleriyle yenilenmesi uzun sürer.

| Aralık |
|:------:|
|  1-100 |

**`ADSB_LIST_RADIUS: ADSB araç listesi yarıçap filtresi`**

Bu yarıçapın dışında tespit edilen araçlar tamamen göz ardı edilir.  SRx_ADSB akışında YKİ'ye görünmezler ve kaçınma hesaplamalarında dikkate alınmazlar. 0 değeri bu filtreyi devre dışı bırakır.

| Aralık | Birim |
|:------:|:-----:|
|0 - 100000	   | metre     |


**`ADSB_ICAO_ID: ICAO_ID araç kimlik numarası`**

ICAO_ID bu uçağın özgün araç kimlik numarasıdır. Bu, 24 bit ile sınırlı bir sayıdır. Eğer 0 olarak ayarlanırsa, rastgele sayı üretilecektir. -1 olarak ayarlanırsa, statik bilgi gönderilmez, alıcı-verici önceden programlandığı varsayılır.

| Aralık |
|:------:|
|-1 - 16777215|

**`ADSB_EMIT_TYPE: Yayıcı türü`**

Transponder sinyalini yayan araç tipi için ADSB sınıflandırması. Varsayılan değer 14 (İHA).

|Değer|	Anlamı|
|:------:|:-----:|
|0	| NoInfo| 
|1	| Light| 
|2	| Small| 
|3	| Large| 
|4	| HighVortexlarge| 
|5	| Heavy| 
|6	| HighlyManuv| 
|7	| Rotocraft| 
|8	| RESERVED| 
|9	| Glider| 
|10	| LightAir| 
|11	| Parachute| 
|12	| UltraLight| 
|13	| RESERVED| 
|14	| İHA| 
|15	| Space| 
|16	| RESERVED| 
|17	| EmergencySurface| 
|18	| ServiceSurface| 
|19	| PointObstacle|

**`ADSB_LEN_WIDTH: Hava taşıtı uzunluğu ve genişliği`**

Uçağın metre cinsinden uzunluk ve genişlik ölçü seçenekleri. Çoğu durumda, en küçük boyut için 1 değerini kullanın.

|Değer|	Anlamı|
|:------:|:-----:|
|0	| VERİ_YOK| 
|1	| L15W23| 
|2	| L25W28P5| 
|3	| L25W34| 
|4	| L35W33| 
|5	| L35W38| 
|6	| L45W39P5| 
|7	| L45W45| 
|8	| L55W45| 
|9	| L55W52| 
|10	| L65W59P5| 
|11	| L65W67| 
|12	| L75W72P5| 
|13	| L75W80| 
|14	| L85W80| 
|15	| L85W90| 

**`ADSB_OFFSET_LAT: GPS anteni yanal offset***`**

GPS anteni yanal offset. Bu, fiziksel konumun uçaktaki GPS antenininin merkezinden dengelenmesini tarif eder.

|Değer|	Anlamı|
|:------:|:-----:|
|0	|VeriYok|
|1	|Sol2m|
|2	|Sol4m|
|3	|Sol6m|
|4	|Merkez|
|5	|Sağ2m|
|6	|Sağ4m|
|7	|Sağ6m|

**`ADSB_OFFSET_LON: GPS anteni boylamsal offset***`** 

GPS anteni uzunlamasına offset. Bu genellikle 1 olarak ayarlanır, Sensör Tarafından Uygulanan.

|Değer|	Anlamı|
|:------:|:-----:|
|0	|VERİ_YOK|
|1	|SensörTarafındanUygulanan|


**`ADSB_RF_SELECT: Alıcı-verici RF seçimi`**

Rx etkin ve/veya Tx etkinleştirmek için alıcı-verici RF seçimi. Bu sadece Tx ve Rx yapabilen cihazları etkiler. Yalnızca Rx bulunan cihazlar, bunu her zaman yalnızca Rx olacak şekilde düzeltir.

|Değer|	Anlamı|
|:------:|:-----:|
|0	|Pasif|
|1	|Sadece-Rx|
|2	|Sadece-Tx|
|3	|Rx ve Tx etkin|


**`ADSB_RF_CAPABLE: RF kabiliyetler`**

Donanımınızın RF giriş/çıkış kabiliyetlerini açıklar.

|Değer|	Anlamı|
|:------:|:-----:|
|0	|Bilinmeyen|
|1	|Sadece Rx UAT|
|3	|Rx UAT ve 1090ES|
|7	|Rx&Tx UAT ve 1090ES|


**`ADSB_LIST_ALT: ADSB araç listesi irtifa filtresi`**

Bu irtifa üzerinde tespit edilen araçlar göz ardı edilir. SRx_ADSB akışında YKİ'ye görünmezler ve kaçınma hesaplamalarında dikkate alınmazlar. 0 değeri bu filtreyi devre dışı bırakır.

| Aralık | Birim |
|:------:|:-----:|
|0 - 32767	   | metre     |


**`ADSB_ICAO_SPECL: Özel araç ICAO_ID'si`**

ADSB_LIST_RADIUS ve ADSB_LIST_ALT'yi gözardı eden özel aracın ICAO_ID'si. Araç her zaman izlenir. Devre dışı bırakmak için 0 kullanın.


**`ADSB_LOG: ADS-B günlüğü tutma`**

0: kayıt yok, 1: sadece özel ID kaydeder, 2:hepsini kaydeder

|Değer|	Anlamı|
|:------:|:-----:|
|0	|kayıt yok|
|1	|sadece özel ID kaydeder|
|2	|hepsini kaydeder|


## AFS_ Parametreleri

**`AFS_ENABLE: Gelişmiş Failsafe'i etkinleştirme`**

Gelişmiş failsafe sistemini mümkün kılar. Sıfıra ayarlanırsa (devre dışı bırakılırsa) diğer AFS seçeneklerinin etkisi olmaz.

**`AFS_MAN_PIN: Manuel pin`**

Manuel moddayken high ayarlamak için dijital çıkış pini ayarlar.

**`AFS_HB_PIN: Heartbeat Pin***`**
> termination: sonlandırma

Bu, sonlandırma etkinleştirilmediğinde 10Hz'de çevrilen bir dijital çıkış pinini ayarlar. Bir FS_TERM_PIN ayarlanmışsa, heartbeat pini, sonlandırma etkinleştirildiğinde sonlandırma kartının, sonlandırma ve otopilotun çökmesi arasındaki ayrım yapmasını sağlamak için 10Hz'de dönmeye devam edeceğini unutmayın.

|Değer|	Anlamı|
|:------:|:-----:|
|-1	| Pasif|
|49	| BB Blue GP0 pin 4|
|50	| AUXOUT1|
|51	| AUXOUT2|
|52	| AUXOUT3|
|53	| AUXOUT4|
|54	| AUXOUT5|
|55 | AUXOUT6|
|57	| BB Blue GP0 pin 3|
|113	| BB Blue GP0 pin 6|
|116	| BB Blue GP0 pin 5|

**`AFS_WP_COMMS: İletişim kaybı waypoint'i`**

İletişim kaybında gidilecek waypoint numarası.

**`AFS_GPS_LOSS: GPS kaybı waypoint'i`**

GPS kilidi kaybında gidilecek waypoint numarası.

**`AFS_TERMINATE: Zorla sonlandırma`**

Heartbeat sinyalinin sonlandırmaya zorlamak için uçuşta ayarlanabilir.

**`AFS_TERM_ACTION: Sonlandırma eylemi`**

Uçuş sonlandırmasında eyleme zorlamak için kullanılabilir. Normalde bu harici failsafe kartı tarafından gerçekleştirilir, ancak APM'yi bunu gerçekleştirmek üzere ayarlayabilirsiniz. Parametrenin olası değerleri hakkında daha fazla bilgi için lütfen vikiye danışın.

**`AFS_TERM_PIN: Sonlandırma pini`**

Uçuş sonlandırmayı high yapmak içini dijital çıkış pini ayarlar.

|Değer|	Anlamı|
|:------:|:-----:|
|-1	| Pasif|
|49	| BB Blue GP0 pin 4|
|50	| AUXOUT1|
|51	| AUXOUT2|
|52	| AUXOUT3|
|53	| AUXOUT4|
|54	| AUXOUT5|
|55 | AUXOUT6|
|57	| BB Blue GP0 pin 3|
|113	| BB Blue GP0 pin 6|
|116	| BB Blue GP0 pin 5|

**`AFS_AMSL_LIMIT: Ortalama deniz seviyesi üzeri sınırı`**

AMSL(above mean sea level) irtifa sınırını belirler. QNH tarafından belirlenen basınç irtifası bu sınırı aşarsa, uçuş sonlandırmaya zorlanır. Bu sınırın metre cinsinden olduğunu, basınç yükseklik irtifasının genellikle feet cinsinden verildiğini unutmayın. Sıfır değeri basınç irtifa sınırını devre dışı bırakır.

|Birim|
|:------:|
| metre |

**`AFS_AMSL_ERR_GPS: GPS tabanlı AMSL sınırı için hata payı***`**

GPS kaynaklı irtifa sınırındaki hata için payı belirler. Bu hata payı yalnızca barometre arızalandığında kullanılır. Barometre arızalanırsa, GPS, AMSL_LIMIT'i zorla uygulayacaktır, ancak verilen pay miktarında bile basınç irtifasının ihlal edilmemesini sağlamak için bu pay ilk önce AMSL_LIMIT'den düşülecektir. OBC kullanıcıları bunu D2 güvenlik durumlarına uyacak şekilde ayarlamalıdır. -1 değeri, barometre arızasının derhal sonlandırılmasına neden olacağı anlamına gelir.

|Birim|
|:------:|
| metre |

**`AFS_QNH_PRESSURE: QNH basıncı`**

İrtifa sınırında basınç irtifası için kullanılacak olan QNH basıncını milibar olarak ayarlar. 0 değeri, irtifa sınırını devre dışı bırakır.

|Birim|
|:------:|
| milibar |

**`AFS_MAX_GPS_LOSS: Maksimum GPS kaybı olayı sayısı`**

Uçağın GPS kurtarma görevine geri dönmeyi bırakmadan önceki maksimum GPS kaybı olayı sayısı. Herhangi bir sayıda GPS kaybına izin vermek için 0 kullanın.

**`AFS_MAX_COM_LOSS: Maksimum iletişim kaybı olayı sayısı`**

Uçağın iletişimi kurtarma görevine geri dönmeyi bırakmadan önceki maksimum iletişim kaybı olayı sayısı. Herhangi bir sayıda iletişim kaybı olayına izin vermek için 0 kullanın.

**`AFS_GEOFENCE: Gelişmiş failsafe coğrafi sınırlamayı etkinleştirir`**

AFS'nin coğrafi sınırlama kısmını etkinleştirir. Yalnızca AFS_ENABLE 1 ise etkili olur.

**`AFS_RC: Gelişmiş failsafe RC etkinleştirir`**

AFS'nin RC kısmını etkinleştirir. Yalnızca AFS_ENABLE 1 ise etkili olur.

**`AFS_RC_MAN_ONLY: Yalnızca manuel kontrol modlarında RC sonlandırma etkinleştirme***`**

Bu parametre 1 ayarlanırsa, RC kaybı yalnızca uçağın manuel kontrol modlarında sonlandırılmasına neden olur. Eğer 0 ise, uçak herhangi bir uçuş modunda sonlandırılacaktır.

**`AFS_DUAL_LOSS: Aynı anda GPS ve YKİ arızalanması nedeniyle çifte kayıp sonlandırmayı etkinleştirme`**

AFS sisteminin çifte kayıp sonlandırma kısmını etkinleştirir. Bu parametre 1 ise ve hem GPS hem de YKİ aynı anda arızalanırsa, bu "çifte kayıp" olarak kabul edilir ve sonlandırmaya neden olur.

**`AFS_RC_FAIL_TIME: RC arıza süre`**

RC girişi kaybedilirse failsafe sonlandırmasının manuel modda devreye gireceği saniye cinsinden süre. OBC kuralları için bu (1.5) olmalıdır. Devre dışı bırakmak için 0 kullanın.

|Birim|
|:------:|
| saniye |


## AHRS_ Parametreleri

**`AHRS_GPS_GAIN: AHRS GPS kazancı`**

Uçağın durumunu düzeltmek için GPS'in ne kadar kullanılacağını ifade eder. Uçaklar için hiçbir zaman 0 ayarlanmamalıdır, çünkü bu dönüşte uçağın kontrolü kaybetmesine neden olur. Lütfen 1.0 varsayılan değerini kullanın.

| Değer | Artış |
|:------:|:-----:|
|0.0-1.0 | .01   |

**`AHRS_GPS_USE: AHRS seyrüsefer için GPS kullanma`**

Bu, konum tahmini veya GPS tabanlı seyrüsefer kullanılıp kullanılmayacağını kontrol eder. 0'a ayarlanırsa, GPS seyrüsefer için kullanılmaz ve sadece konum tahmini kullanılır. Normal uçuş için hiçbir zaman sıfır değeri kullanılmamalıdır. Şu anda bu sadece DCM-tabanlı AHRS'yi etkiler: EKF, mümkün olduğunda GPS kullanır.

| Değer  | Anlamı|
|:------:|:-----:|
|0 | Pasif|
|1 | Etkin|

**`AHRS_YAW_P: Yaw P`**

GPS veya pusulanın burun yönü üzerindeki etkisini kontrol eder. Daha yüksek bir değer, rotanın yaw kaynağını (GPS veya pusula) daha hızlı takip edeceği anlamına gelir.

| Aralık | Artış |
|:------:|:-----:|
|0.1 - 0.4	   | .01     |

**`AHRS_RP_P: AHRS RP_P`**

İvmeölçerin attitude'u ne kadar hızlı düzelteceğini kontrol eder.

| Aralık | Artış |
|:------:|:-----:|
|0.1 - 0.4	   | .01     |

**`AHRS_WIND_MAX: Maksimum rüzgar`**

Yer sürati ve hava sürati arasındaki izin verilen maksimum farkı belirler. Uçağın arızalı bir hava sürati sensörü ile idare etmesini sağlar. 0 değeri, hava süratinin olduğu gibi kullanılacağı anlamına gelir.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|0 - 127			| 1     | m/s|

**`AHRS_TRIM_X: AHRS Trim Roll`**

Kontrol kartı ve frame arasındaki roll açısı farkını telafi eder. Pozitif değerler aracın doğru roll yapmasını sağlar.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-0.1745 - +0.1745		| 0.01     | radyan|

**`AHRS_TRIM_Y: AHRS Trim Pitch`**

Kontrol kartı ve frame arasındaki pitch açısı farkını telafi eder. Pozitif değerler aracın yukarı/aşağı pitch yapmasını sağlar.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-0.1745 - +0.1745		| 0.01     | radyan|

**`AHRS_TRIM_Z: AHRS Trim Yaw`**

---

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-0.1745 - +0.1745		| 0.01     | radyan|

  **`AHRS_ORIENTATION: kart oryantasyonu`**

Kart tipi için oryantasyonu açısı. Kartın aracınızda 90 veya 45 derecelik bir açıyla yönelmesini sağlamak için IMU ve pusula okumalarını çevirir. Bu seçenek bir sonraki başlangıçta etkili olur. Değiştirdikten sonra aracınızı re-level etmeniz gerekecektir.

| Değer | Anlamı |
|:------:|:-----:|
|0	|Yok|
|1	|Yaw45|
|2	|Yaw90|
|3	|Yaw135|
|4	|Yaw180|
|5	|Yaw225|
|6	|Yaw270|
|7	|Yaw315|
|8	|Roll180|
|9	|Roll180Yaw45|
|10	|Roll180Yaw90|
|11	|Roll180Yaw135|
|12	|Pitch180|
|13	|Roll180Yaw225|
|14	|Roll180Yaw270|
|15	|Roll180Yaw315|
|16	|Roll90|
|17	|Roll90Yaw45|
|18	|Roll90Yaw90|
|19	|Roll90Yaw135|
|20	|Roll270|
|21	|Roll270Yaw45|
|22	|Roll270Yaw90|
|23	|Roll270Yaw135|
|24	|Pitch90|
|25	|Pitch270|
|26	|Pitch180Yaw90|
|27	|Pitch180Yaw270|
|28	|Roll90Pitch90|
|29	|Roll180Pitch90|
|30	|Roll270Pitch90|
|31	|Roll90Pitch180|
|32	|Roll270Pitch180|
|33	|Roll90Pitch270|
|34	|Roll180Pitch270|
|35	|Roll270Pitch270|
|36	|Roll90Pitch180Yaw90|
|37	|Roll90Yaw270|
|38	|Yaw293Pitch68Roll180|
|39	|Pitch315|
|40	|Roll90Pitch315|
|100	|Özel|

**`AHRS_COMP_BETA: AHRS hız tamamlayıcı filtre beta katsayısı`**

AHRS'yi (hava sürati ve burun yönü) sigortalamak için kullanılan geçiş frekansı ve yer hızını tahmin etmek üzere GPS verileri için zaman sabitini kontrol eder. Zaman sabiti 0.1/beta'dır. Daha büyük bir zaman sabiti daha az GPS verisi kullanır, küçük zaman sabiti ise daha az hava verisi kullanır.

| Aralık | Artış |
|:------:|:-----:|
|0.001 - 0.5	   | .01     |

**`AHRS_GPS_MINSATS: AHRS GPS minimum uydu`**

Hız temelli attitude düzeltmesi için GPS kullanmak üzere görünür minimum uydu sayısı. Bu, varsayılan değer olarak 6'dır; GPS'den gelen hız sayılarının, ivmeölçerlerin doğruluğunun düzeltilmesi için fazla güvenilmez hale geldiği nokta ile ilgilidir.

| Aralık | Artış |
|:------:|:-----:|
|0 - 10	   | 1     |

**`AHRS_EKF_TYPE: durum ve konum tahmini için NavEKF Kalman filtresi kullan`**

Hangi NavEKF Kalman filtre versiyonunun durum ve pozisyon tahmini için kullanıldığını kontrol eder.

| Değer | Anlamı |
|:------:|:-----:|
|0 | Pasif     |
|1 | EKF2 etkin     |
|2 | EKF3 etkin     |

**`AHRS_CUSTOM_ROLL: Kart oryantasyonu roll offseti`**
Otopilot montaj pozisyonu roll offseti. Pozitif değerler = sağ roll, negatif değerler = sol roll. Bu parametre yalnızca AHRS_ORIENTATION, CUSTOM olarak ayarlandığında kullanılır.


| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-180 - 180	| 1     | derece|

**`AHRS_CUSTOM_PIT: Kart oryantasyonu pitch offseti`**

Otopilot montaj pozisyonu pitch offseti. Pozitif değerler = yukarı pitch, negatif değerler = aşağı pitch. Bu parametre yalnızca AHRS_ORIENTATION, CUSTOM olarak ayarlandığında kullanılır.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-180 - 180	| 1     | derece|

**`AHRS_CUSTOM_YAW: Kart oryantasyonu yaw offseti`**

Otopilot montaj pozisyonu yaw offseti. Pozitif değerler = sağ yaw, negatif değerler = sol yaw. Bu parametre yalnızca AHRS_ORIENTATION, CUSTOM olarak ayarlandığında kullanılır.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|-180 - 180	| 1     | derece|


## ARMING_ Parametreleri

**`ARMING_REQUIRE: Motor arm etme gereksinimi`**
Gereksinimler yerine getirilinceye kadar arm etme devre dışı. 0 ise herhangi gereksinim yok (anında arm). 1 ise, motorları çalıştırmadan önce rudder stick veya YKİ arm etme gerektirir ve devre dışı bırakıldığındaa mininum gaz PWM değerini throttle kanalına gönderir. 2 ise, rudder çubuğu veya YKİ arm etme gerektirir ve devre dışı bırakıldığında throttle kanalına 0 PWM gönderir. Arm etmeden önce hangi kontrollerin yapıldığını görmek için ARMING_CHECK_* parametrelerine bakın. Bu parametrenin 0 olarak ayarlanması durumunda, uçağı arm etmek için yeniden başlatma gerektirir. Ayrıca, bu parametre 0 olduğunda, ARMING_CHECK parametresi sıfır değilse, ön arm kontrol arızası nedeniyle uçak throttle arm ederken önyüklemede başarısız olabilir.

| Değer | Anlamı |
|:------:|:-----:|
|0	   | Devre dışı    |
|1	   | Disarm edildiğinde THR_MIN PWM     |
|2    | Disarm edildiğinde 0 PWM     |

**`ARMING_ACCTHRESH: İvmeölçer hata eşiği`**
Tutarsız ivmeölçer belirlemek için kullanılan ivmeölçer eşiği. Donanım hatası veya kalibrasyon hatasını tespit etmek için bu hata aralığını diğer ivmeölçerlerle karşılaştırır. Düşük değer, daha sıkı kontrol ve arm kontrolünden geçişin zorlaşması demektir. Tüm ivmeölçerler eşit yaratılmamıştır.

| Aralık | Birim |
|:------:|:-----:|
|0.25-3.0| m/s2  |

**`ARMING_RUDDER: Rudder ile arm etme etkinleştirme/devre dışı bırakma`**
Rudder girişiyle arm/disarm'a izin verir. Etkinleştirildiğinde, sağ rudder ile arm yapılabilir, sol rudder ile disarm yapılabilir. Rudder ile arm etme sadece throttle sıfır +- deadzone(RCx_DZ) konumunda olan manuel throttle modlarında çalışır. 

| Değer  | Anlamı |
|:------:|:-----:|
|0| Devre Dışı  |
|1| Sadece Arm  |
|2| Arm veya Disarm  |

**`ARMING_MIS_ITEMS: Gerekli görev öğeleri`**
Hava aracını arm etmek için planlanması gereken görev öğelerinin bit maskesi.

| Değer  | Anlamı |
|:------:|:-----:|
|0| Land  |
|1| VTOL Land  |
|2| DO_LAND_START  |
|3| Takeoff  |
|4| VTOL Takeoff  |
|5| Rallypoint  |


**`ARMING_CHECK: Gerçekleştirilmesi gereken arm kontrolleri (bitmask)`**
Motoru arm etmeden önce kontrol eder. Bu, arm etmeye izin vermeden önce yapılacak olan kontrollerin bitmaskesidir. Varsayılan ayarda kontrol edilmez ve herhangi bir zamanda devreye alınmasına izin verir. Bu parametreyi ayarlamak için her bir kontrol tipinin değerlerini bir araya getirerek tercih ettiğiniz kontrolleri seçebilirsiniz. Örneğin, sadece GPS kilidiniz varsa ve RC failsafe değilse, ARMING_CHECK değerini 72 olarak ayarlamalısınız. Tüm kontrolleri etkinleştirmek için 1 olarak ayarlamanız önerilir.


## STEER2SRV_ Parametreleri
> steering angle: direksiyon açısı   
> ground handling: yer taşıması   

**`STEER2SRV_TCONST: Direksiyon Süre Sabiti`**
İstenenden erişilen direksiyon açısına saniye cinsinden zaman sabitini kontrol eder. Hava araçlarındaki zemin yönlendirme için küçük değer önerilir, sabit kanatlı hava taşıtlarında en iyi zemin taşıma için 0.5 değeri önerilir. 0.75 değeri, kontrolcünün istenen ve gerçek seyir açısı arasındaki sapmayı 0.75 saniye içinde düzeltmeye çalışacağı anlamına gelir.

| Aralık  | Artış | Birim |
|:-------:|:-----:|:-----:|
|0.4 - 1.0		| 0.1     | saniye|

**`STEER2SRV_P: Direksiyon dönüş kazancı`**
Direksiyon için oransal kazanç. Düşük hızda ve maksimum direksiyon açısında aracın dönüş dairesinin çapına yaklaşık olarak eşit olmalıdır.

| Aralık  | Artış |
|:-------:|:-----:|
|0.1 - 10.0		| 0.1     |

**`STEER2SRV_D: Sönüm kazancı`**


**`STEER2SRV_IMAX: Integrator limit`**


**`STEER2SRV_MINSPD: Minimum speed`**


**`STEER2SRV_FF: Steering feed forward`**


**`STEER2SRV_DRTSPD: Derating speed`**


**`STEER2SRV_DRTFCT: Derating factor`**


**`STEER2SRV_DRTMIN: Minimum angle of whe`**


# TECS_ Parametreleri

**`TECS_CLMB_MAX: Maksimum tırmanış hızı (metre/saniye)`**
Talep edilen maksimum tırmanma oranı. Batarya düşük voltajda iken, THR_MAX'ta TRIM_ARSPD_CM'de tırmanma hızından daha yükseğe ayar yapmayın. Hava sürati yükselişte muhafaa edilemiyorsa değeri azaltın. Throttle yükselmek için önemli ölçüde artmıyorsa değeri arttırın.

| Aralık  | Artış |
|:-------:|:-----:|
|0.1 - 20.0		| 0.1     |

**`TECS_SINK_MIN: Minimum alçalma hızı (metre/saniye)`**
THR_MIN ve TRIM_ARSPD_CM'de iken minimum alçalma hızı.

| Aralık  | Artış |
|:-------:|:-----:|
|0.1 - 10.0		| 0.1     |

**`TECS_TIME_CONST: Kontrolcü zaman sabiti (saniye)`**
TECS kontrol algoritmasının zaman sabiti. Küçük değerler, daha hızlı irtifa düzeltmeleri yapar, ancak pistten dışarı çıkmaya ve agresif davranışa neden olabilir.

| Aralık  | Artış |
|:-------:|:-----:|
|3.0 - 10.0			| 0.2     |

**`TECS_THR_DAMP: Kontrolcü throttle sönümü`**
Throttle talep döngüsü için sönüm kazancı. Hız ve yüseklik salınımlarını düzeltmek için throttle tepkisini yavaşlatır.

| Aralık  | Artış |
|:-------:|:-----:|
|0.1 - 10.0		| 0.1     |

**`TECS_INTEG_GAIN: Controller integrator`**
Uzun vadeli hız ve yükseklik hatalarını düzeltmek için integratör kazancı.

| Aralık  | Artış |
|:-------:|:-----:|
|0.0 - 0.5		| 0.02     |

**`TECS_VERT_ACC: Dikey ivme limiti (metre/saniye^2)`**
Hız ve yükseklik hatalarını düzeltmek için kullanılan maksimum dikey ivme.

| Aralık  | Artış |
|:-------:|:-----:|
|1.0 - 10.0			| 0.5     |

**`TECS_SPD_OMEGA: Speed complementary filter frequency (radians/sec)`**
**`TECS_RLL2THR: Bank angle compensation gain`**
**`TECS_SPDWEIGHT: Weighting applied to speed control`**
**`TECS_PTCH_DAMP: Controller pitch damping`**
**`TECS_SINK_MAX: Maximum Descent Rate (metres/sec)`**
**`TECS_LAND_ARSPD: Airspeed during landing approach (m/s)`**
**`TECS_LAND_THR: Cruise throttle during landing approach (percentage)`**
**`TECS_LAND_SPDWGT: Weighting applied to speed control during landing.`**
**`TECS_PITCH_MAX: Maximum pitch in auto flight`**
**`TECS_PITCH_MIN: Minimum pitch in auto flight`**
**`TECS_LAND_SINK: Sink rate for final landing stage`**
**`TECS_LAND_TCONST: Land controller time constant (sec)`**
**`TECS_LAND_DAMP: Controller sink rate to pitch gain during flare`**
**`TECS_LAND_PMAX: Maximum pitch during final stage of landing`**
**`TECS_APPR_SMAX: Sink rate max for landing approach stage`**
**`TECS_LAND_SRC: Land sink rate change`**
**`TECS_LAND_TDAMP: Controller throttle damping when landing`**
**`TECS_LAND_IGAIN: Controller integrator during landing`**
**`TECS_TKOFF_IGAIN: Controller integrator during takeoff`**
**`TECS_LAND_PDAMP: Pitch damping gain when landing`**
