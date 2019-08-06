# OTOMATİK TAKEOFF
Plane, otomatik kalkış başlatabilir. Aşağıdaki talimatlar ile nasıl yapılacağı öğretilecektir.

## Temel Talimatlar
Temel fikir otopilotun throttle ı maksimuma getirmesi ve belirlenen irtifaya ulaşana kadar tırmanmasıdır. Uçağın takeoff yapmasını sağlamak için, görevinize [**NAV_TAKEOFF**]() komutu ekleyin. Bu komutun iki parametresi vardır - miminum pitch ve takeoff irtifası. Minimum pitch takeoff sırasında uçağın ne kadar dik tırmanacağını kontrol eder. Çoğu uçak için 10 ila 15 derece arası bir değer önerilir. Takeoff irtifası, takeoff eksiksiz olduğu kabul edildiğinde evden yüksekliği kontrol eder. Bunun uçağın kalkıştan sonra güvenle dönebileceği kadar yüksek olduğundna emin olun. 40 metre irtifa çoğu uçak için iyidir.

Kalkış sırasında kanatlar [**LEVEL_ROLL_LIMIT**]() derece dahilinde tutulacaktır. Bu, keskin bir roll kanatların yerden kalkarken piste vurmaması için keskin bir roll yapmasını önler.

Takeoff yönünün, otomatik kalkış komutu başlatıldığında uçağın başının doğrultusu yönünde ayarlandığını unutmayın. Bu yüzden önce uçağı doğru yöne çevirip ardından AUTO moda geçmeniz gerekir. Takeoff'un ilk aşamasında otopilot uçağı düz tutmak için ana mekanizma olarak jiroskopu kullanacaktır. İyi bir GPS rotası için yeterli hıza ulaşıldıktan sonra, uçak rüzgarın hesaba katılmasını sağlayan GPS yer izi kullanmaya dönecektir.


Mümkün olduğunca rüzgara doğru fırlatmalısınız.

## Pist kalkışı (CTOL)

Tekerlekli kalkışta veya konvansiyonel kalkış da denir.

Pist kalkışıyla ilgili önemli bir husus uçağın taildragger(kuyruk tekerlekli yönlendirme) veya tricycle undercarriage(burun tekerlekli yönlendirme) olmasıdır. Tricycle undercarriage ototakeoff daha kolaydır.

Anahtar parametreler ise:
* [**TKOFF_TDRAG_ELEV**]()
* [**TKOFF_TDRAG_SPD1**]()
* [**TKOFF_THR_SLEW**]()
* [**TKOFF_ROTATE_SPD**]()
* [**TECS_PITCH_MAX**]()
* [**GROUND_STEER_ALT**]()

Bu parametrelere ek olarak, zemin yönlendirme(ground steering) ayarını yapmanız gerekir, böylece uçak güvenli şekilde yönlendirilebilir. Zemin yönlendirme kurulumu ile ilgili sayfaya bakın. Bu ayarın bir parçası olarak [**GROUND_STEER_ALT**]() parametresini ayarlamanız gerekir.

İlk iki parametre ağırlıklı olmak üzere taildragger içindir, ancak diğer uçakların burnunu takeoffta aşağıda tutmak için de kullanılabilir.

[**TKOFF_TDRAG_ELEV**]() parametresi, pist üzerinde yönlendirmek için yeterli tutuş sağlamak üzere, taildragger kuyruğunu pistte sabit tutmak için kullanılır. Taildragger için bu varsayılan olarak 100 dür, yani kalkışın ilk aşamalarında %100 yukarı elevator uygulanır. Tricycle undercarriage uçak için, burun üzerine biraz daha fazla ağırlık gerektirdiği için -20 (20% aşağı elevator) değerinin yardımcı olacağını görebilirsiniz.

Takeoff başladığında, otopilot uçak saniyede [**TKOFF_TDRAG_SPD1**]() metre hıza ulaşana kadar [**TKOFF_TDRAG_ELEV**]() elevator (yüzde olarak) uygulayacak. [**TKOFF_TDRAG_SPD1**]()'i takeoff hızının altındaki bir hıza, ancak uçak dümen kullanarak yönlendirilebileceği hızın üzerinde bir hıza ayarlamanız gerekir. Uçak [**TKOFF_TDRAG_SPD1**]()'e ulaştığında, elevatorü serbest bırakacak ve pitch seviyesini tutmaya çalışmak için normal flight pitch controller kullanacaktır. Bu, taildragger uçakta kuyruğu yükseltme etkisine sahip olacaktır.

[**TKOFF_ROTATE_SPD**]() parametresi, otopilotun zemini terk etmek için ne zaman burnu kaldırmaya (pitch up) çalışacağını kontrol eder. Bunun, uçağın tırmanışı sürdürebileceği bir hız olması gerekir, bu nedenle uçağın durma hızının üstünde, en az 2 m/s tercihen ise daha fazla olmalıdır. Daha yüksek bir değer daha uzun bir takeoff anlamına gelir (ve bu nedenle daha uzun pist gerektirir).

[**TKOFF_THR_SLEW**]() parametresi, takeoff sırasında throttle değişim hızını (saniye olarak yüzde olarak) kontrol eder. Bu, uçağınıza throttle'ı uygun bir hızda arttırmaya izin vermek için kullanılır. 20 değeri (saniyede %20 throtte değişimi) birçok taildragger için iyidir. Tricycle undercarriage uçağı, daha büyük bir throttle değişim hızının üstesinden gelebilir.

[**TECS_PITCH_MAX**]() parametresi takeoff sırasında tırmanırken kullanılan maksimum pitch'i kontrol eder. Uçağın tam gazda tırmanmak için kullanabileceği bir değerle sınırlı olduğundan emin olun. 20 derecelik bir değer, çeşitli uçaklar için iyidir.

## FBWA modunda Zemin Takeoff testi

FBWA uçuş modu kullanarak takeoff kodunu test etmek bazen yararlı olabilir. Bunu yapma şekliniz [**FBWA_TDRAG_CHAN**]() parametresini bir switch için vericinizdeki bir RC giriş kanalına ayarlamaktır (genellikle buton anahtar). FBWA modunda takeoff için pistte beklerken RC kanalı high olduğunda, otopilot [**TKOFF_TDRAG_ELEV**]() ve [**TKOFF_TDRAG_SPD1**]() parametrelerini yapılandırıp yapılandırmadığınızı kontrol edecektir. Sıfır dışında bir değer verilmişse, elevator FBWA'da AUTO kalkış için kontrolcüyle aynı şekilde kontrol edilecek. Elevator, RC kanalı high olur olmaz [**TKOFF_TDRAG_ELEV**]() değerine (taildragger için genelde %100) gider, ve uçak saniyede [**TKOFF_TDRAG_SPD1**]() m/s yer hızına ulaşana kadar orada kalacaktır.

Bu, FBWA modunda oto takeoff testi yapmak için uygun bir yoldur, ayrıca genel olarak FBWA modunda daha iyi zemin yönlendirmesi elde etmek için iyi bir yoldur.
