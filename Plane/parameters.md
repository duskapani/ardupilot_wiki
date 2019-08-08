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
## ArduPlane Parametreleri

**`AUTOTUNE_LEVEL: autotune düzeyi`**  

~Level of aggressiveness of pitch and roll PID gains.~ Düşük değerler 'daha yumuşak' ayar sağlar. Çoğu uçak için Seviye 6 önerilir.

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

Bu parametre, kuyruğu zeminde tutmayı bırakacak ve zemindeki dümen kontrolüne geçiş yapacağı hava hızını ayarlar. TKOFF_TDRAG_SPD1'e ulaşıldığında, uçağın pitch TKOFF_ROTATE_SPD'e, görevde belirlenen takeoff pitch takeoff tırmanışı için pitch "döndürmek" için kullanılan noktaya, ulaşılana kadar seviyesi sabitlenir. Doğrudan dönüşe geçmek için TKOFF_TDRAG_SPD1'i sıfıra ayarlayın. Bu, elden kalkışlar ve mancınık fırlatmaları için sıfıra ayarlanmalıdır. Ayrıca, burun tekerleğini tutmak için yukarıdaki yöntemi kullanmıyorsanız, tricycle undercarriage uçaklarda sıfıra ayarlanmalıdır. Taildragger uçaklar için stall hızının hemen altına ayarlanmalıdır.

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
|-1-127  | -1: Sıfırlama, 0: Her zaman sıfırla   | metre|

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
