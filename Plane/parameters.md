# PARAMETRE LİSTESİ
> tune: kanal ayarı
> smoothing out: kolaylaştırmak
> pusher prop: itici pervane
> forward acceleration: ileri ivme
> hand launch: elden kalkış
> velocity: hız
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

Otomatik takeoff'ta throttle'ı bastırmayan/önlemeyen hız kontrolü tarafından kullanılan m/s cinsinden minimum GPS yer hızı. Bu, motorun uçağın mancınığı terk etmesinden sonra devreye alınmasını istediğiniz mancınık fırlatmalarında kullanılabilir, ancak GPS ölçümleriyle ilgili hatalar nedeniyle mancınık başlatmalarında TKOFF_THR_MINACC ve TKOFF_THR_DELAY parametrelerinin kullanılması tercih edilir. İtici pervaneyle elden kalkışlarda, vaktinden önce motorun çalışmasına karşı ek koruma sağlamak için bu parametrenin 4m/s den daha az olmayan bir değere ayarlanması şiddetle tavsiye edilir. GPS süratinin gerçek sürati yaklaşık 0.5 saniye geciktireceğini unutmayın. Zemin hızı kontrolü, TKOFF_THR_DELAY parametresi tarafından ertelenir.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s   |

**`TKOFF_THR_MINACC: Takeoff throttle minimum ivme`**  

Otomatik takeoffta yer hız kontrolü arm etmeden önce m/s/s cinsinden minimum ileri ivme. Bu, elden kalkışlarda kullanılmak içindir. 0 olması, ivme testini devre dışı bırakır, Bu GPS hız atlamalarının motorun çalıştırılmasına izin verebilecek yer hız kontrolünü her zaman arm edeceği anlamına gelir. Elden kalkışlarda ve bungee kalkışlarda 15 civarında ayarlanmalıdır. Ayrıca tam "arm için sallanma" kontrolü için TKOFF_ACCEL_CNT parametresine bakın.

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s2  |

**`TKOFF_THR_DELAY: Takeoff throttle gecikmesi`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-127    | 1   | desisaniye  |

**`TKOFF_TDRAG_ELEV: Takeoff taildragger elevator`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-100-100    | 1   | yüzde  |

**`TKOFF_TDRAG_SPD1: Takeoff tail dragger hız1`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s  |

**`TKOFF_ROTATE_SPD: Takeoff dönüş hızı`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-30    | 0.1   | m/s  |

**`TKOFF_THR_SLEW: Takeoff throttle değişim hızı`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|-1-127    | 1   | saniye başına yüzden  |

**`TKOFF_PLIM_SEC: Takeoff pitch limit reduction`**

| Aralık | Artış | Birim |
|:------:|:-----:|:-----:|
|0-10    | 0.5   | saniye|

**`TKOFF_FLAP_PCNT: Takeoff flap yüzdesi`**

| Aralık | Birim |
|:------:|:-----:|
|0-100   | yüzde |
