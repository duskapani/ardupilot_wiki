# PARAMETRE LİSTESİ
> tune: kanal ayarı
> smoothing out: kolaylaştırmak
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
