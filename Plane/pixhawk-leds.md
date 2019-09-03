# LEDler (Pixhawk)

Bu makale, ana LED'in renklerinin ve flaş sıralamasının nasıl yorumlanacağını açıklar.

## LEDlerin Anlamları

__Yanıp sönen kırmızı ve mavi__: Jiroskopun kullanıma hazırlanması. Sensörler değerleri alırken aracı sabit ve düz tutun.  
__Yanıp sönen mavi__: Disarm edildi, GPS kilidi bulunamadı. Otopilot, loiter ve rtl modları GPS kilidi gerektirir.  
__Sabit mavi__: GPS kilidi yokken arm edildi.  
__Yanıp sönen yeşil__: Disarm edildi (arm'a hazır), GPS kilidi kazanıldı. Arm edili durumdan disarm edilirken hızlı çift ton.  
__Hızlı yanıp sönen yeşil__: Yukarıdakiyle aynı, ancak GPS SBAS kullanıyor (bu nedenle daha iyi konum ahmininde bulunmalı).  
__Sabit yeşil - arm edilirken uzun tek bir tonla__: Arm edildi, GPS kilidi kazanıldı. Uçuşa hazır!  
__Çift yanıp sönen sarı__: Arm öncesi kontroller başarısız (sistem arm edilmeyi reddediyor).  
__Tek yanıp sönen sarı__: Radyo failsafe aktif.  
__Yanıp sönen sarı - hızlı bip sesiyle__: Batarya failsafe aktif.  
__Yanıp sönen sarı ve mavi - yüksek-yüksek-yüksek-düşük ton dizisiyle__:  GPS arızalı veya GPS failsafe aktif.  
__Yanıp sönen kırmızı ve sarı - yükselen ton__: EKF veya Atalet Nav hatası.  
__Yanıp sönen mor ve sarı__: Barometre arızası.  
__Sabit kırmızı__: Hata  
__Sabit kırmızı - SOS ton dizisiyle__: SD Kart kayıp.  
