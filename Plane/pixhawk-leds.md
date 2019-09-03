# LEDler (Pixhawk)

Bu makale, ana LED'in renklerinin ve flaş sıralamasının nasıl yorumlanacağını açıklar.

## LEDlerin Anlamları

_Yanıp sönen kırmızı ve mavi: Jiroskopun kullanıma hazırlanması. Sensörler değerleri alırken aracı sabit ve düz tutun.

_Yanıp sönen mavi: Disarm edildi, GPS kilidi bulunamadı. Otopilot, loiter ve rtl modları GPS kilidi gerektirir.

_Sabit mavi: GPS kilidi yokken arm edildi.

_Yanıp sönen yeşil: Disarm edildi (arm'a hazır), GPS kilidi kazanıldı. Arm edili durumdan disarm edilirken hızlı çift ton.

_Hızlı yanıp sönen yeşil: Yukarıdakiyle aynı, ancak GPS SBAS kullanıyor (bu nedenle daha iyi konum ahmininde bulunmalı).

_Sabit yeşil - arm edilirken uzun tek bir tonla: Arm edildi, GPS kilidi kazanıldı. Uçuşa hazır!

_Çift yanıp sönen sarı: Arm öncesi kontroller başarısız (sistem arm edilmeyi reddediyor).

_Tek yanıp sönen sarı: Radyo failsafe aktif.

_Yanıp sönen sarı - hızlı bip sesiyle: Batarya failsafe aktif.

_Yanıp sönen sarı ve mavi - yüksek-yüksek-yüksek-düşük ton dizisiyle:  GPS arızalı veya GPS failsafe aktif.

_Yanıp sönen kırmızı ve sarı - yükselen ton: EKF veya Atalet Nav hatası.

__Yanıp sönen mor ve sarı__: Barometre arızası.

_Sabit kırmızı_: Hata

_Sabit kırmızı - SOS ton dizisiyle_: SD Kart kayıp.
