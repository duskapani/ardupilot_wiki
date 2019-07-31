Otomatik İniş
=================

Bu makale, Plane'da uçağın güvenli olarak indirilmesini sağlayacak bilgiler içerir.

Otomatik İniş Yapılandırması
=================================

Plane, görev planının bir parçası olarak uçağı otomatik olarak indirebilir.

Uçağı indirmek için, görevin sonuna istediğiniz konma noktasının enlem, boylam ve irtifasını belirten bir [NAV_LAND]() komutu eklemeniz gerekir. Çoğu durumda, irtifa 0 olarak ayarlanmalıdır. İniş sırasında, otopilot uçak palye noktasına ulaştığında -aşağıda açıklanan parametrelerle kontrol edilir- gazı kesecek ve mevcut doğrultuyu koruyacaktır.


Anahtar Parametreler
--------------

Otomatik inişi kontrol eden temel parametreler:

-  [LAND_FLARE_ALT]()
-  [LAND_FLARE_SEC]()
-  [LAND_PITCH_CD]()
-  [TECS_LAND_ARSPD]()
-  [TECS_LAND_SPDWGT]()

Bu parametrelerin her birinin anlamı ve önerilen değeri aşağıda açıklanmıştır.

Palye Noktası Ayarlama
-----------------------
Flare: Palyeye geçmek

“Palye”, otopilotun gazı kestiği, pitch'i yükselttiği ve zemine yavaş yavaş inmek için uçağı yavaşlattığı inişin son aşamasıdır. "Palye" için uygun zaman uçağın tipine bağlıdır, [LAND_FLARE_ALT]() ve [LAND_FLARE_SEC]() parametreleri tarafından kontrol edilir.

Palyenin ilk kontrolü [LAND_FLARE_SEC]() parametresidir. Bu, uçağın mevcut iniş hızıyla devam ederse yere çarpmadan önceki süre. Uçak eğer 2 m/s'ye iniyorsa ve [LAND_FLARE_SEC]() değerini 3'e ayarlarsanız, uçak yerden 6 metre irtifada palyeye geçer. Palyeyi kontrol etmek için çarpma zamanı kullanılarak, uçak hızla iniyorsa daha yüksek irtifada, yavaşta düşük bir irtifada palyeye geçebilir. Bu palyenin yumuşak iniş yapmasını sağlamaya yardımcı olur.

İkinci kontrol [LAND_FLARE_ALT](). Bu, iniş hızına bakılmaksızın uçağın palyeye geçeceği irtifadır.

Bu iki parametre için uygun değerler, otopilotun irtifayı nasıl hesapladığına bağlıdır. Eğer otopilotun iyi bir mesafe ölçeri (LIDAR gibi) varsa güvenli bir şekilde oldukça küçük sayılar seçebbilir ve zemine yakın palyeye geçebilir. Bu genellikle daha iyi bir iniş sağlar. 
[LAND_FLARE_SEC]() için 1.5, [LAND_FLARE_ALT]() için 2, LIDAR ile başlamak için iyi bir seçimdir. İrtifa için barometre kullanıyorsanız, hatayı hesaba katmak için muhtemelen daha yüksek değerlere ihtiyacınız olacak.

Süzülüş Açısını Kontrol Etme
---------------------------
glide slope: süzülüş açısı

Palye noktasını ayarlamada bir başka önemli, faktör süzülüş açısıdır. Süzülüş açısı, son waypointten iniş noktasına olan mesafenin ve son waypoint ve iniş noktası arasındaki yükseklik farkının oranıdır. Örneğin, iniş noktası son waypointten 300 metre uzaktaysa ve son waypoint yerden 30 metre yüksekteyse, süzülüş açısı %10'dur.

Süzülüş açısı çok dikse, uçak çarpmayı önleyemek için zamanında palyeye geçemeyecek, ayrıca otopilot uçağı doğru olarak süzülme teşebbüsünde tutamayabilir. En fazla 10%'luk bir süzülüş açısıyla başlamanız önerilir. Uçağınızın kullanabileceği kayma eğimi, pitch kontrolcüsü ayarınızın ne kadar iyi olduğuna, TECS ayarınızın ne kadar iyi olduğuna ve istediğiniz iniş hızına bağlıdır.

Uçağınızın istenen süzülüş açısını tam olarak yapmadığını tespit ederseniz, o zaman öncelikle günlüklerinizde pitch ayarlarını kontrol edin, ve iniş sırasında birkaç derece içinde istenen ve ulaşılan pitch eşleştiğinden emin olun. Eşleşmemesi halinde, pitch ayarlarıyla ilgili belgelere gözatın (veya bi ihtimal AUTOTUNE yeniden çalıştırın). Talep edilen ve ulaşılan pitch eşleşirse, hava hızının doğruluğunu kontrol etmek için TECS günlüklerinizi kontrol etmelisiniz.


İniş Hava Hızı
----------------

landing approach: iniş yaklaşma hızı (süzülüş açısından gelen hız)
stall speed: motorlar durmuş haldeyken iniş hızı
landing speed: iniş hızı

Otomatik iniş, hava hızı sensöründen büyük ölçüde destek alır. Hava hızı sensörü kullanıldığında, iniş yaklaşma hızı (süzülüş açısından gelen hız) [TECS_LAND_ARSPD]() parametresi tarafından kontrol edilir, m/s olarak.

[TECS_LAND_ARSPD]() için uçağınızın motorlar durmuş haldeyken iniş hızının üstünde bir değer seçmeniz gerekir. Motorlar durduğunda iniş hızının uçağınızın ağırlığına bağlı olduğundan, uçağın ağırlığını önemli ölçüde değiştirirseniz (batarya veya kamera eklemek gibi) iniş hızını ayarlamanız gerekeceğini unutmayın.

İnişi daha da iyileştirmek için, palyeden hemen önce hava hızını azaltmak için Ön-Palye(Pre-Flare) kullanabilirsiniz. Bu [LAND_PF_ALT]() veya [LAND_PF_SEC]()'e belirli bir irtifada veya tahmini bir saniyede ön-palye durumuna girmek üzere ayarlanmasıyla etkinleştirilir. Ön-Palye tetiklendiğinde istenen hava hızı [LAND_PF_ARSPD]() olur. Bu değer [TECS_LAND_ARSPD]()'den düşük, ancak stall speedden yüksek olmalıdır. Bu reverse thrust olduğu durumlarda faydalıdır. Bununla birlikte, bazı uçaklar stall landing gerçekleştirebilir bu nedenle düşük bir sayıya (1) ayarlamak, uçağa palyeye geçmeden önce mümkün olduğunca hava hızı kadar gaz boşaltır. 

Yaklaşma kontrolü
------------------------
landing approach: iniş yaklaşması

İniş yaklaşması sırasında otopilotun istenen hava hızını ([TECS_LAND_ARSPD]() ile belirlenen) ve istenen süzülüş açısı ve iniş pozisyonu (önceki waypoint ve son waypoint noktası tarafından belirlenen) dengelemesi gerekir. Varsayılan yapılandırma bu iki talebi dengelemeye çalışır, ancak bazı uçaklarda diğerine öncelik vermek isteyebilirsiniz.

Hava hızı kontrolünün yükseklik kontrolüne karşı önceliği [TECS_LAND_SPDWGT]() parametresi kullanılarak belirlenir. 1 değeri(varsayılan) ikisi arasında denge demektir. İkiye yakın bir değer, hava hızına daha yüksek öncelik verirken, sıfıra yakın bir değer yükseklik kontrolüne öncelik verir. Örneğin stall speed'e daha yakın bir hızda iniş yapıyorsanız, hava hızı kontrolüne öncelik vermek isteyebilirsiniz. Bunu yapmak için [TECS_LAND_SPDWGT]() değerini 1.9 gibi bir değere ayarlamanız gerekir.

If what you want in a landing is precision in the position where it lands then you should set TECS_LAND_SPDWGT to a low number, such as 0.2 or even 0.0. In that case the plane will still try to achieve the target landing airspeed by using the throttle, but it will not try to control airspeed with pitch.

Bir planör (veya motorsuz herhangi bir uçağı) iniş yaptırıyorsanız, [TECS_LAND_SPDWGT]()'yi 2.0'a ayarlamalısınız, böylece hava hızı öncelikli olur ve hava hızını kontrol etmek için pitch kullanılır.

In most cases a value of -1 gives the best result. This special value will auto-adjust the value during the landing, scaling it from your normal TECS_SPDWEIGHT value down to zero at the point of landing. So up in the sky during approach you maintain good airspeed but by the time you land the emphasis is on a more accurate landing.


Controlling the flare
---------------------

The final stage of the landing is called the "flare". During the flare
the aircraft tries to retain a course along the line between the last
waypoint and the landing waypoint, and it controls it's height solely
using a target descent rate. Once the flare is started the throttle is
"disabled" - set to some value between :ref:`THR_MIN <THR_MIN>` and
zero.

The main job of the flight controller in the flare is to try to achieve
the descent rate specified in the
:ref:`TECS_LAND_SINK <TECS_LAND_SINK>` parameter. That defaults to 0.25 meters/second, which is a reasonable
touchdown vertical speed for most models. To achieve that speed the TECS
controller uses pitch control only as the motor has been forced to zero.

The primary parameters which affect the ability of the aircraft to
achieve the desired descent rate are
:ref:`LAND_PITCH_CD <LAND_PITCH_CD>`, 
:ref:`TECS_LAND_DAMP <TECS_LAND_DAMP>`
and the main pitch tuning parameters.

The ``LAND_PITCH_CD`` parameter sets the minimum pitch target in the
flare (in centi-degrees). This parameter is very airframe specific and
is designed to prevent the nose of the aircraft being too far down on
touchdown causing issues with damaging the landing gear or breaking a
propeller.  For most aircraft this should be a small positive number
(such as 300, meaning 3 degrees), but for some belly landing aircraft a
small negative number can be good, to allow the nose to be kept down a
small amount to reduce the chance of stall if the flare happens too far
off the ground.

Note that the actual pitch of the aircraft can be quite a bit above
``LAND_PITCH_CD`` as the TECS controller tries to control the descent
rate. The maximum pitch is controlled by the
:ref:`TECS_PITCH_MAX <TECS_PITCH_MAX>`
parameter if it is non-zero, otherwise by the
:ref:`LIM_PITCH_MAX <LIM_PITCH_MAX>` parameter.

The ``TECS_LAND_DAMP`` parameter is a damping constant for the pitch
control during flare. A larger number will cause the pitch demand to change
more slowly. This parameter can be used to reduce issues with sudden
pitch changes when the flare happens.

After the Flare
---------------

After the plane flares it continues to navigate, but with zero throttle.
The navigation direction is a line extrapolated forward through the
landing point from the last waypoint. Note that the navigation roll will
be limited to
:ref:`LEVEL_ROLL_LIMIT <LEVEL_ROLL_LIMIT>`
(which defaults to 5 degrees) to prevent wing strike, so if there is a
significant cross-wind then it is likely that the aircraft will not be
able to maintain the exact path.

If your aircraft is consistently landing long (which can happen for a
variety of reasons) then you can adjust
:ref:`TECS_LAND_SRC <TECS_LAND_SRC>` to
either force a stall (negative) or bring it down (positive). This value
will adjust your ``TECS_LAND_SINK`` proportional to the distance from
the LAND point. This helps ensure you land in a reasonable distance from
the LAND point.

.. note::

   Possible causes of landing long include ground effect giving the
   aircraft more lift as it is close to the ground or simply the aircraft
   traveling very fast.

When the plane has stopped moving for
:ref:`LAND_DISARMDELAY <LAND_DISARMDELAY>`
seconds (default 20 seconds) it will disarm the motor. Optionally, you
can disable servo movement once LAND_DISARMDELAY has triggered by
setting :ref:`LAND_THEN_NEUTRL <LAND_THEN_NEUTRL>`.

Using a rangefinder
-------------------

If you have :ref:`fitted a rangefinder <common-rangefinder-landingpage>`
to your aircraft then you can use it for much more accurate landing
control. To allow the rangefinder to be used for landing you need to set
the :ref:`RNGFND_LANDING <RNGFND_LANDING>` parameter to 1.

When using a rangefinder for landing the altitude given by the
rangefinder is used only in the landing approach and to determine the
flare point, and is designed to allow the aircraft to more accurately
follow the glide slope and to flare at the right time.

.. note::

   The effectiveness of a rangefinder can depend on the surface you
   are flying over, so it is a good idea to do some low passes in a flight
   mode such as FBWA first, then examine the logs to check that the
   rangefinder is working correctly.

Also note that if you have a longer range rangefinder then it is a very
good idea to set the minimum range of the rangerfinder well above zero.
For example, the PulsedLight Lidar has a typical range of over 40
meters, and when it gets false readings it tends to read ranges of less
than 1 meter. Setting :ref:`RNGFND_MIN_CM <RNGFND_MIN_CM>`
to 150 will discard any rangerfinder readings below 1.5 meters, and will
greatly improve the robustness of the Lidar for landing.

Improving the landing
---------------------

The key to a good landing is the autopilot knowing how far off the
ground it is. With the default setup the only sensor available to detect
altitude is the barometer. Unfortunately barometers suffer from three
main types of error:

-  barometric drift due to changes in atmospheric pressure
-  barometric drift due to changes in the temperature of the autopilot
   electronics
-  barometric error due to local pressure changes from airflow around
   the barometer

The ideal setup for good automatic landing is to have a
:ref:`Lidar <common-rangefinder-landingpage>`. A Lidar can measure
the distance to the ground very accurately, and doesn't suffer from
drift. If you have a Lidar installed you can enable its use for landing
with ``RNGFND_LANDING=1``.

If a Lidar isn't fitted then there are a few things you can do to
minimise barometric error problems with auto-land

-  perform a barometer calibration after the electronics have warmed up.
   The easiest way to do this with a Pixhawk is to disarm the plane with
   the safety switch. When the plane is disarmed it assumes it is on the
   ground and will zero the barometer to the current pressure.
-  try to prevent direct airflow over the autopilot that could cause
   speed related pressure changes
-  fly shorter flights, allowing for less time for airpressure changes.
   Check your logs and see if the landing is happening at zero altitude
   consistently

With planes that belly land it can also work well to setup the landing
with a shallow pitch (in ``LAND_PITCH_CD``) and set a slightly higher
altitude to flare at. That will only work if your stall speed is low
enough that gliding for a while will work reliably.

Using DO_LAND_START
===================

Sometimes it is useful to trigger an automatic landing as part of an RTL
(return to launch). To do this you need to do two things:

-  add a :ref:`DO_LAND_START <mav_cmd_do_land_start>`
   mission item to your mission, just before the start of your landing
   sequence
-  set the :ref:`RTL_AUTOLAND <RTL_AUTOLAND>`
   parameter to 1 or 2

The way it works is that when the plane enters an RTL it checks to see
if the parameter RTL_AUTOLAND is set to 1 or 2. If it is then the
current mission is searched for a mission item of type DO_LAND_START.
If one is found then the plane will automatically enter AUTO mode and
land, starting at the part of the mission just after the
``DO_LAND_START`` marker.

The exact behaviour depends on the ``RTL_AUTOLAND`` value:

-  If ``RTL_AUTOLAND=1`` then the plane will first RTL as normal, then
   when it starts circling the return point (home or a rally point) it
   will then switch to the AUTO mission after the ``DO_LAND_START`` and
   land
-  If ``RTL_AUTOLAND=2`` then the plane will bypass the RTL completely
   and go straight to the landing sequence.

You can optionally include more than one ``DO_LAND_START`` mission item
in your mission. If that is done then the latitude/longitude of the
``DO_LAND_START`` mission items is used to choose which landing sequence
to use. The ``DO_LAND_START`` closest to the current location is used.
This can be useful if you have multiple landing sequences for different
wind conditions or different areas.

How to abort an auto-landing
============================
A landing-abort mechanism is provided to allow you to abort a landing sequence in a safe, controlled, and expected way. Custom abort behaviour can be pre-programmed as part of the mission or you can use the default abort mechanism. To enable this feature set param LAND_ABORT_THR=1.
 
There are three steps to this feature:

1. :ref:`Trigger an abort <trigger_an_abort>`
#. :ref:`The behavior during the abort <behavior_during_the_abort>`
#. :ref:`The mission state after the abort completes <mission_state_after_an_aborted_landing_completes>`

.. note::

   This section describes the abort behavior introduced in Plane
   3.4.

.. _trigger_an_abort:

Step 1) Abort land triggers
---------------------------
The are three ways to trigger an auto-landing abort. All of them will only work while in AUTO mode and currently executing a ``LAND`` waypoint mission item:

-  *Send the ``MAV_CMD_DO_GO_AROUND`` command using a GCS.* Mission Planner has a button labeled "Abort Landing" on the FlightData Actions tab.
-  *RC input Throttle > 90%*. This will trigger an abort while staying in AUTO mode. The throttle only needs to be high briefly to trigger it. Don't forget to lower it!
-  *Mode change*. For human piloted landing abort you can switch out of AUTO mode into, for example MANUAL/STABILIZE/FBWA, and navigate the aircraft safely however you'd like. Using this method will skip abort behavior step 2 because it is being done manually. When switching back to AUTO the mission will resume as described in step 3 below.

.. _behavior_during_the_abort:

Step 2) Abort land flight behavior
----------------------------------
The abort behaviour has a default configuration and does not require a pre-planned mission. The default abort behavior is to simulate an auto-takeoff: pitch up at least 10 degrees and set throttle to TKOFF_THR_MAX and hold the heading until it reaches a target altitude of 30m. It is possible to override the pitch and altitude to allow for a customized behavior.

- Pitch minimum. If there was a NAV_TAKEOFF ever executed on this mission then the same pitch will be re-used here.
- Target altitude. If NAV_LAND param1 is >0 then it is used as a target altitude in meters. Else If a NAV_TAKEOFF was ever executed on this mission then the same altitude will be re-used here.
  
This step is skipped if the abort trigger is via mode change because it is assumed the pilot manually took over and flew the aircraft to a safe altitude at the pitch and throttle of their choosing.

.. _mission_state_after_an_aborted_landing_completes:

Step 3) Mission state after an aborted landing completes
--------------------------------------------------------
Once an abort land has completed, by either reaching the target altitude or switching back to AUTO, the mission index will have changed and you will no longer be executing a NAV_LAND command. The mission index will change to be one of these three options and checked for in this order:

- If the NAV_LAND mission item is followed by mission item :ref:`CONTINUE_AND_CHANGE_ALT <mav_cmd_nav_continue_and_change_alt>` with param1 = 0 or 1 then the mission index will increment once to that command and execute it like normal. This can be followed by further post-abort mission planning for any custom planned mission behavior.
- Else If there is a :ref:`DO_LAND_START <mav_cmd_do_land_start>` in the mission then it jumps to that index.
- Else the mission index decrements once to be the index before the NAV_LAND. This will ensure the same landing approach is repeated.


.. _reverse-thrust:

Reverse-Thrust Landing
======================

Some ESC's allow for reverse direction. When using reverse on the propeller it will generate a negative thrust which can be used to reduce your airspeed. 
During a steep landing approach this method can be used to maintain a stable and low airspeed allowing you to land much more softly and precisely. 
To use this feature it is highly recommend to use an airspeed sensor and a rangefinder (see above) for an accurate altitude.

.. note::

   Reverse-thrust landings are available starting from Plane
   v3.5.1.


The below video is an example of a Skywalker X8 performing an auto-landing with a 15 degree slope. The target is the hat on the ground showing it is possible to get repeatable high precision landings where the final position error was dictated by the GPS position error. This particular aircraft has been landed at 20deg and 25deg slopes too. YMMV depending on weight of aircraft and available thrust from motor/propeller. Typically a Skywalker X8 would need a shallow slope such at 6 to 10deg.  

..  youtube:: kdw8vjbttNo
    :width: 100%


Anahtar Parametreler
--------------

The key parameters that control reverse thrust landing in addition to the ones :ref:`listed in section 1.1 <automatic-landing_key_parameters>` are:

-  :ref:`LAND_PF_ALT <LAND_PF_ALT>`
-  :ref:`LAND_PF_SEC <LAND_PF_SEC>`
-  :ref:`LAND_PF_ARSPD <LAND_PF_ARSPD>`
-  :ref:`USE_REV_THRUST <USE_REV_THRUST>`
-  :ref:`TECS_APPR_SMAX <TECS_APPR_SMAX>`
-  :ref:`RC3_TRIM <RC3_TRIM>`
-  :ref:`THR_MIN <THR_MIN>`



ESC (Electronic Speed Controller)
---------------------------------

Hardware selection and programming
++++++++++++++++++++++++++++++++++

Most ESCs can operate in forwards and reverse, however that is usually not a stock feature and may need to be reprogrammed to do it. 
Any SimonK and BLHeli compatible ESC can be flashed to support reverse thrust. 

`Here's info about BLHeli compatible ones <https://blhelisuite.wordpress.com/>`__.


Hardware configuration
++++++++++++++++++++++

.. note::

   Remove propeller while configuring ESCs and thrust parameters

Configure your ESC for reverse thrust by changing it's neutral point.
Many ESC require custom firmware to accomplish this. Search Google or your ESC's mfgr for instructions on how to configure your particular ESC.

Set these:

#. Minimum PWM to 1000, mid to 1500, and maximum to 2000.
#. ``THR_MIN`` to a negative value such -100. Next set ``RC3_TRIM`` (or whatever ``RCx`` is mapped to throttle via ``RCMAP_THROTTLE``) to your ESC's mid value.

Determining your max glide slope angle
--------------------------------------

For a steep landing approach, the limitation is how well you can maintain your desired airspeed. 
This is determined by your aircraft's ability to create reverse thrust (motor+prop thrust ability) and its resistance to slowing down (aircraft mass). 
In many cases extreme steepness is unnecessary, but possible. 
With an over-sized motor and lightweight aircraft you can come in as steep as 60 degrees.

To determine your steepest approach angle, set :ref:`TECS_APPR_SMAX <TECS_APPR_SMAX>` very high as to not limit you (e.g. 99). 
Next, plan a mission with a steeper than normal approach (try 15 degrees and go up from there).
Watch your airspeed on the approach - the aircraft should be able to maintain :ref:`TECS_LAND_ARSPD <TECS_LAND_ARSPD>` without exceeding 75% of the available reverse throttle range. 
If not, you're coming in too steep for the negative-thrust-to-mass ratio of your aircraft.

.. tip::

   Keep in mind that whatever value you determine as your maximum may
   not be acceptable in all wind conditions. It is best to be a little
   conservative to maintain repeatability.

Setting up the Pre-Flare
------------------------

With a rangefinder and airspeed sensors installed, at the pre-flare point we will have an accurate airspeed and altitude reading. 
This gives us a good idea of our momentum and stable "initial conditions" to the final flare. 
Set ``LAND_PF_ALT`` (or ``LAND_PF_SEC``) to a fairly high point (for example 10m) and adjust from there. 
Next set ``LAND_PF_ARSPD`` to a value just above your stall speed.

When LAND_PF_ALT is reached the airspeed demand will instantly go from :ref:`TECS_LAND_ARSPD <TECS_LAND_ARSPD>` to LAND_PF_ARSPD.
This will cause it to slam on the brakes via increased reverse thrust so that the airspeed reduces to the desired airspeed.

The trick is to set ``LAND_PF_ALT`` to an altitude where it
achieves ``LAND_PF_ARSPD`` before killing the throttle at
``LAND_FLARE_ALT`` (which occurs at a somewhat low altitude - around 1
or 2m).

Example, ``TECS_LAND_ARSPD = 15``, ``LAND_PF_ARSPD = 12``, ``LAND_PF_ALT=12``, ``LAND_FLARE_ALT=2``.
Depending on your slope, mass of aircraft and motor+propeller thrust
ability, you're expecting the aircraft to decelerate from 15m/s to 12m/s
airspeed while dropping 10m to 2m. These are the critical params to adjust to
ensure a smooth and slow flare below 2m altitude.

Flare
-----

Now that you are starting the flare with a stable and predictable airspeed, it's much easier to :ref:`control the flare <automatic-landing_controlling_the_flare>`. 
If you've already tuned your flare for an auto-land without reverse thrust you'll want to retune it. 
You'll notice you're coming in much slower ad tuning will be easier. 
The tweaks and compromises you had to do before are much easier to deal with.


Determining actual stall speed of your aircraft
+++++++++++++++++++++++++++++++++++++++++++++++

Unless you really know what you're doing, stall speed can be hard to estimate. 
Traditionally, to determine this true value you would need to slowly decrease your airspeed until you stall but that comes with the pesky problem that now you have a stalled aircraft falling out of the sky.

With ``LAND_PF_ALT`` and ``LAND_PF_ARSPD`` you can check your stall speed much lower to the ground. 
To know the airspeed at the exact moment it stalls, check your dataflash logs (``*.bin`` on SD card) for the airspeed (ARSP.Airspeed) when your wing loses lift and drops by comparing actual roll (CTUN.Roll) and desired roll (CTUN.NavPitch) diverge.
