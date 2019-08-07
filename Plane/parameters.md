# PARAMETRE LİSTESİ
> tune: kanal ayarı
> smoothing out: kolaylaştırmak
> pusher prop: itici pervane
> forward acceleration: ileri ivme
> hand launch: elden kalkış
> velocity: hız
> ground speed: yer sürati
> airspeed: hava sürati
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

LEVEL_ROLL_LIMIT: Level flight roll limit
ALT_CTRL_ALG: Altitude control algorithm
WP_RADIUS: Waypoint Radius
WP_MAX_RADIUS: Waypoint Maximum Radius
WP_LOITER_RAD: Waypoint Loiter Radius
RTL_RADIUS: RTL loiter radius
FENCE_ACTION: Action on geofence breach
FENCE_MINALT: Fence Minimum Altitude
FENCE_MAXALT: Fence Maximum Altitude
FENCE_RETALT: Fence Return Altitude
FENCE_AUTOENABLE: Fence automatic enable
FENCE_RET_RALLY: Fence Return to Rally
ARSPD_FBW_MIN: Minimum Airspeed
ARSPD_FBW_MAX: Maximum Airspeed
TERRAIN_FOLLOW: Use terrain following
THR_MIN: Minimum Throttle
THR_MAX: Maximum Throttle
TKOFF_THR_MAX: Maximum Throttle for takeoff
THR_SLEWRATE: Throttle slew rate
FLAP_SLEWRATE: Flap slew rate
THR_SUPP_MAN: Throttle suppress manual passthru
THR_FAILSAFE: Throttle and RC Failsafe Enable
TRIM_THROTTLE: Throttle cruise percentage
THROTTLE_NUDGE: Throttle nudge enable
LIM_ROLL_CD: Maximum Bank Angle
LIM_PITCH_MAX: Maximum Pitch Angle
LIM_PITCH_MIN: Minimum Pitch Angle
GROUND_STEER_DPS: Ground steer rate
RUDDER_ONLY: Rudder only aircraft
HOME_RESET_ALT: Home reset altitude threshold
TKOFF_ACCEL_CNT: Takeoff throttle acceleration count
TKOFF_TIMEOUT: Takeoff timeout



