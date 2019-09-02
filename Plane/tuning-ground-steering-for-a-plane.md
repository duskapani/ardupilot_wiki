# UÇAK İÇİN ZEMİN YÖNLENDİRME AYARI

> ground steering: zemin yönlendirme

Plane firmware uçağınızda kuyruk veya burun tekerleği varsa zemin yönlendirme özelliğini kontrol edebilir. Zemin yönlendirme MANUEL hariç tüm modlarda etkinleştirilir ve düzgün şekilde ayarlandığında uçağın kalkışı ve inişi için pist boyunca düz bir yolda tutulmasını çok daha kolay hale gelir.

Uçak için zemin yönlendirme ayarlanırken, doğru yapmanız gereken 4 temel parametre vardır. Bu kılavuz, bu parametreleri doğru almak için bir dizi adım sunar, böylece uçağınız zemindeki pisti tam olarak takip eder.

## Yönlendirme Kontrolü

Zemin yönlendirme etkinleştirmek için GROUND_STEER_ALT parametresini sıfırın üzerinde bir değere ayarlamanız gerekir. ~This is the barometric altitude above the initial altitude at which the steering changes from ground steering of a wheel to rudder steering for aerodynamic control.~ Biraz barometrik kayma sağlamak için bunu 5 metreye ayarlamanız önerilir.

Zemin yönlendirme etkin olduğunda, rudder veya aileron girişi olmadığında pusula yönüne kilitlenir. Bu nedenle, taksi yaparken istikamet değiştirmek için rudder kullanmalı, sonrasında pusula yönünü tutmak için aileron ve rudderdan elinizi çekmelisiniz. Zemin yönlendirmesi ancak etkin bir pusulanız varsa düzgün çalışacaktır.

## Anahtar Parametreler

> damping: sönüm

* __STEER2SRV_P__: Koda dönüş dairesinin (metre cinsinden çarp olarak) uçağınız için ne olduğunu söyler. İstenen dönüş hızını elde etmek için hangi direksiyon açısını seçeceğinizi belirttiğinden bu parametreyi doğru almanız çok önemlidir.

* __STEER2SRV_I__: Direksiyon açısının integralinden kazançtır. ~Increasing this gain causes the controller to trim out steady offsets due to an out of trim vehicle.~ 

* __STEER2SRV_D__: Direksiyon kontrol döngüsünün sönümünü ayarlar. Bu kazanç, yönlendirme titreşimini azaltmaya yardımcı olur. 0.01'lik artışlarla arttırılmalıdır, çünkü büyük bir değer aracı aşırı gerebilecek yüksek frekanslı direksiyon salınımına neden olabilir.

* __STEER2SRV_IMAX__: İntegratörün çalışacağı direksiyon derecesini (santi derece cinsinden) sınırlar. Varsayılan 1500 santi derece ayarında, integratör +-15 derece servo hareketiyle sınırlı olacaktır. ~The maximum servo deflection is +- 45 centi-degrees, so the default value represents a 1/3rd of the total control throw which is adequate unless the vehicle is severely out of trim.~

* __STEER2SRV_MINSPD__: Bu direksiyon için metre/saniye cinsinden minimum yer süratidir. Minimum sürate sahip olmak, araç ilk harekete başladığında salınımları önler. Araç hala bu sınırdan daha yavaş sürüş yapabilir, ancak direksiyon hesaplamaları bu minimum hıza göre yapılacaktır.

* __STEER2SRV_TCONST__: İstenenden erişilen direksiyon açısına saniye cinsinden zaman sabitini kontrol eder. Hava araçlarındaki zemin yönlendirme için küçük değer önerilir, sabit kanatlı hava taşıtlarında en iyi zemin taşıma için 0.5 değeri önerilir. 0.5 değeri, kontrolcünün istenen ve gerçek seyir açısı arasındaki sapmayı 0.5 saniye içinde düzeltmeye çalışacağı anlamına gelir. 

* __GROUND_STEER_ALT__: Zemin direksiyon kontrolcüsünün rudder üzerinde kullanılacağı irtifa. Sıfır değilse STEER2SRV kontrolcüsü rudderi ev irtifasının bu limiti dahilindeki irtifaları kontrol etmek için kullanılır.

## Adım 1: İLK PARAMETRELERİN AYARLANMASI

Ayarlama işlemini başlatmak için aşağıdaki değerleri ayarlayın:

* __STEER2SRV_P__: = Adım 2'ye bakın
* __STEER2SRV_I__: = 0.1
* __STEER2SRV_D__: = 0.02
* __STEER2SRV_IMAX__: = 1500
* __STEER2SRV_MINSPD__: = 1
* __STEER2SRV_TCONST__: = 0.5
* __GROUND_STEER_ALT__: = 5

Bunlar, çoğu UÇAK için size makul davranışlar verecek optimal değerlerdir.

## Adım 2: STEER2SRV_P AYARLANMASI

STEER2SRV_P parametrenizi ayarlamak için uçağınızın dönüş dairesinin çağını ölçmeniz gerekir.

Motor kapalıyken uçağı MANUAL moduna getirin ve rudderi bir tarafa sabitleyin. Ardından uçağınızı yavaşça bir daire şeklinde itin. Bu dairenin çapını ölçmek için bir şerit metre kullanın ve STEER2SRV_P'yi metre cinsinden bu değere ayarlayın. Uçakların çoğu 4 metre çapında bir dönme çapına sahiptir. Dönme çapınız 4'ten uzunsa, oranları ruddera yanlış atmış olabilirsiniz.

## ~Fixing Problems with weaving~

Zemin yönlendirme ile ilgili genel bir problem, direksiyonun yumuşak bir şekilde dönmek yerine bir yandan diğer yana dönerek ‘weaves' çizmesidir. Bunun gerçekleşmesinin birkaç olası nedeni olabilir.

Çözmeniz gereken ilk şey, sorunun düşük hızla sınırlı olup olmadığı veya yüksek hızda sürüşü etkilemesidir. Sadece çok düşük hızda meydana gelirse, en büyük sorun STEER2SRV_MINSPD'nin çok düşük olmasıdır. Varsayılan değer 1.0m/s'dir ve oldukça düşüktür. GPS yönünüz düşük hızda güvenilir değilse, değeri yükseltmeniz gerekebilir. 2.0 deneyin ve düşük hızlı zikzak için yardımcı olup olmadığını görün.

Yönlendirme kontrolcüde weaving kontrol edecek 3 temel parametre vardır:
* Daha küçük bir STEER2SRV_P weaving yapmayı azaltacaktır, tek seferde 0.1 azaltmayı deneyin.
* Daha büyük bir STEER2SRV_D weaving'i söndürür, ancak çok büyük yaparsanız yüksek hızda salınım elde edersiniz. Örneğin, 0.1 değerinin sönümü azalttığını görebilirsiniz, ancak 0.2 değeri direksiyon servosunda yüksek hızlı salınımlara neden olabilir. Hızlı salınım olursa, STEER2SRV_D değerini % 50 azaltın.
* Daha büyük bir STEER2SRV_TCONST direksiyon kontrolünü yavaşlatır bu da weaving azaltır. 0.1 arttırarak yükseltmeyi deneyin.

Mevcut kontrolcü sistemiyle istediğiniz davranışı elde etmek için bu değerlerle biraz deneme yapmanız gerekir.


## Otomatik kalkış için ayarlama

Zemin direksiyonunu otomatik kalkış için ayarlamak üzere FBWA modunda ayar yapmak genellikle en iyisidir ve FBWA modunda direksiyon tamamen geçersiz kılmadan kalktıktan sonra otomatik kalkışa geçin.

FBWA modundayken oto kalkışta kullanılanla aynı otomatik elevator davranışını ayarlamak için FBWA_TDRAG_CHAN seçeneğini kullanmak da çok yararlı olabilir. Bu, taildragger uçakta kuyruk tekerleğini (tricycle da ise burun tekerleğini) zeminde tutmaya yardımcı olur.

## Limiting the steering to prevent a roll on a wing 


* __DRTSPD__ - bu hızdan sonra direksiyon açısı azalır.
* __DRTFCT__ - her bir m/s hız artışı başına azaltılacak derece miktarı
* __DTRMIN__ - daha fazla azaltılmayacak minimum direksiyon açısı
