# Coğrafi Sınırlandırma

GPS konumlarının kapalı bir poligonu artı minimum ve maximum irtifa olarak uçmak istenilen alan etrafına sanal bir "çit" yapmanıza izin verir.

Çalışması için çizilmiş bir çit poligonunun olması GEREKİR. 

Çit etkin olduğunda, uçağınız çitle çevrili alanın dışına çıkarsa, GUIDED moduna geçer ve önceden tanımlanmış bir noktaya döner ve tekrar ele geçirmeniz için loiter yapar. Daha sonra kumandanızla veya YKİ ile kontrolü geri alın.

![](resimler/geofence1.jpg)

## R/C Eğitimi İçin Kullanmak

Kumanda eğitimi için bir alan çevirip güvenle uçuş yapabilirsiniz.

Coğrafi sınırlandırma, herhangi APM uçuş moduyla birleştirilebilir. Manuel modla birleştirirseniz yalnızca çitle çevrili alanın dışına veya irtifa aralığının dışına çıakrsanız kontrol altına alır.

## Sınırlama İçin Kullanma

Tamamen otonom uçuş sırasında, emniyet önlemi olarak kullanılabilir. Bunun için FENCE_AUTOENABLE parametresini kullanın; uçak kalkış tamamlandıktan sonra otomatik olarak çiti çalıştırır ve iniş noktasına ulaşıldıında çiti otomatik olarak devre dışı bırakır. Bu öze lliği kullanmak için FENCE_AUTOENABLE parametresini 1 olarak ayarlayın. 

Yarı otonom uçuşlarda ise çit YKİ veya kumanda üzerinden etkinleştirebilir/devre dışı bırakılabilir - bu durumda FENCE_AUTOENABLE isteğe bağlıdır.

## Coğrafi Sınırlandırma Oluşturmak

Coğrafi çit oluşturmak için birkaç şey yapılandırmanız gerekir:

1. çit sınırı, GPS noktaları kümesi olarak
2. çit ihlalinde yapılacak eylem
3. dönüş noktası konumu; isteğe bağlı olarak uçağın çit dönüş noktası yerine en yakın Rally noktasına dönmesi için FENCE_RET_RALLY parametresini kullanabileceğinizi unutmayın.
4. çitle çevrili alanın min ve maks irtifası
5. coğrafi sınırlandırmayı etkinleştirmek için kullanılacak RC kanalı (varsa)
6. sınırlandırmayı otokalkıştan sonra otomatik olarak etkinleştirecek ve otoiniş sonrası otomatik olarak devre dışı bırakacak şekilde yapılandırmak istediğinizde isteğe bağlı bir ayar (FENCE_AUTOENABLE)
7. sınır ihlali sırasında kontrolün nasıl geri alınacağı

Çit sınırınızı oluştururken uymanız gereken birkaç kural vardır:

1. dönüş noktası çit sınırı içerisinde olmalı
2. çit sınırı tamamen kapalı olmalı. yani 4 noktanın ilk ve son noktası aynı yerde olmalı.
3. sınır içerisinde en fazla 18 nokta olabilir.

Çitinizi oluştururken uçağınızın çite çarptığında momentum göstereceğini ve dönüş noktasına geri dönmesinin zaman alacağını unutmayın.
SkyWalker gibi bir uçak için uçmak istediğiniz gerçek sınırın içinde yaklaşık 30 metre ek güvenlik yapı öneririz. Aynısı irtifa içinde geçerli.

Çit sınırından ayrı olarak, aşağıdaki MAVLink parametreleri coğrafi sınırlandırma davranışını kontrol eder:
1. FENCE_ACTION - çit ihlalinde yapmak için eylem. Varsayılan olarak coğrafi sınırlandırmayı devre dışı bırakan 0 ayarlanır. Coğrafi sınır özelliğini etkinleştirmek için 1 olarak ayarlayın ve sınır ihlali durumunda dönüş noktasına uçun. YKİ'ye ihlali bildirmek için 2 olarak ayarlayın, ancak başka işlem yapma. Uçağın başının ihlal noktasından dönüş noktasına gelmesi için 3 e ayarlayın, ancak pilot bu durumda manuel gaz kontrolü sağlayacaktır.
2. FENCE_MINALT  - metre cinsinden minimum irtifa. Eğer bu 0 ise, minimum irtifa olmayacak.
3. FENCE_MAXALT  - metre cinsinden maksimum irtifa. Eğer bu 0 ise, maksimum irtifa olmayacak.
4. FENCE_CHANNEL - coğrafi sınırı etkinleştirmek için RC giriş kanalı. Bu, coğrafi çitleri devre dışı bırakan varsayılan olarak 0 ayarlanır. Vericinizdeki iki konum anahtarına bağlı yedek bir RC giriş kanalına ayarlamanız gerekir. Bu kanal 1750 PWM değerinin üzerinde çıktığında çit etkin olacaktır. Eğer vericiniz destekliyorsa, bu kanal etkin olduğunda sesli geri bildirimi etkinleştirmekde iyi bir fikirdir.
5. FENCE_TOTAL - çitinizin içindeki nokta sayısı (geri dönüş noktası artı kapalı sınır). Çit oluştururken planlayıcı tarafından sizin için ayarlanmalıdır. 
6. FENCE_RETALT - dönüş noktasına uçarken ve dönüş noktasında loiter yaparken uçağın uçacağı irtifa (metre cinsinden). FENCE_RET_RALLY 1 olarak ayarlandığında, bu parametrenin yok sayıldığını ve bunun yerine en yakın Rally noktasının loiter irtifasının kullanıldığını unutmayın. Bu parametre 0 ise ve FENCE_RET_RALLY de 0 ise, FENCE_MAXALT ve FENCE_MINALT parametrelerinin orta noktası dönüş yüksekliği olarak kullanılır.
7. FENCE_AUTOENABLE - 1 ayarlanırsa, uçak çit devre dışı bırakılmış olarak açılır. Otokalkış tamamlandıktan sonra çit otomatik devreye girer. Oto iniş noktasına gelince çit otomatik olarak devre dışı kalır.
8. FENCE_RET_RALLY - 1 olarak ayarlanırsa, çite çarptığı zaman çit dönüş noktası yerine en yakın Rally noktasına gidecektir. Rally noktasının loiter irtifasının dönüş rakımı olarak kullanıldığına dikkat edin.

