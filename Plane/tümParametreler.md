# ArduPlane Parameters

FORMAT_VERSION: Eeprom format version number  
SYSID_THISMAV: MAVLink system ID of this vehicle  
SYSID_MYGCS: Ground station MAVLink system ID  
AUTOTUNE_LEVEL: Autotune level  
TELEM_DELAY: Telemetry startup delay  
GCS_PID_MASK: GCS PID tuning mask  
KFF_RDDRMIX: Rudder Mix  
KFF_THR2PTCH: Throttle to Pitch Mix  
STAB_PITCH_DOWN: Low throttle pitch down trim  
GLIDE_SLOPE_MIN: Glide slope minimum  
GLIDE_SLOPE_THR: Glide slope threshold  
STICK_MIXING: Stick Mixing  
AUTO_FBW_STEER: Use FBWA steering in AUTO  
TKOFF_THR_MINSPD: Takeoff throttle min speed  
TKOFF_THR_MINACC: Takeoff throttle min acceleration  
TKOFF_THR_DELAY: Takeoff throttle delay  
TKOFF_TDRAG_ELEV: Takeoff tail dragger elevator  
TKOFF_TDRAG_SPD1: Takeoff tail dragger speed1  
TKOFF_ROTATE_SPD: Takeoff rotate speed  
TKOFF_THR_SLEW: Takeoff throttle slew rate  
TKOFF_PLIM_SEC: Takeoff pitch limit reduction  
TKOFF_FLAP_PCNT: Takeoff flap percentage  
FBWA_TDRAG_CHAN: FBWA taildragger channel  
LEVEL_ROLL_LIMIT: Level flight roll limit  
USE_REV_THRUST: Bitmask for when to allow negative reverse thrust  
NAV_CONTROLLER: Navigation controller selection  
ALT_CTRL_ALG: Altitude control algorithm  
ALT_OFFSET: Altitude offset  
WP_RADIUS: Waypoint Radius  
WP_MAX_RADIUS: Waypoint Maximum Radius  
WP_LOITER_RAD: Waypoint Loiter Radius  
RTL_RADIUS: RTL loiter radius  
FENCE_ACTION: Action on geofence breach  
FENCE_TOTAL: Fence Total  
FENCE_CHANNEL: Fence Channel  
FENCE_MINALT: Fence Minimum Altitude  
FENCE_MAXALT: Fence Maximum Altitude  
FENCE_RETALT: Fence Return Altitude  
FENCE_AUTOENABLE: Fence automatic enable  
FENCE_RET_RALLY: Fence Return to Rally  
STALL_PREVENTION: Enable stall prevention  
ARSPD_FBW_MIN: Minimum Airspeed  
ARSPD_FBW_MAX: Maximum Airspeed  
FBWB_ELEV_REV: Fly By Wire elevator reverse  
TERRAIN_FOLLOW: Use terrain following  
TERRAIN_LOOKAHD: Terrain lookahead  
FBWB_CLIMB_RATE: Fly By Wire B altitude change rate  
THR_MIN: Minimum Throttle  
THR_MAX: Maximum Throttle  
TKOFF_THR_MAX: Maximum Throttle for takeoff  
THR_SLEWRATE: Throttle slew rate  
FLAP_SLEWRATE: Flap slew rate  
THR_SUPP_MAN: Throttle suppress manual passthru  
THR_PASS_STAB: Throttle passthru in stabilize  
THR_FAILSAFE: Throttle and RC Failsafe Enable  
THR_FS_VALUE: Throttle Failsafe Value  
TRIM_THROTTLE: Throttle cruise percentage  
THROTTLE_NUDGE: Throttle nudge enable  
FS_SHORT_ACTN: Short failsafe action  
FS_SHORT_TIMEOUT: Short failsafe timeout  
FS_LONG_ACTN: Long failsafe action  
FS_LONG_TIMEOUT: Long failsafe timeout  
FS_GCS_ENABL: GCS failsafe enable  
FLTMODE_CH: Flightmode channel  
FLTMODE1: FlightMode1  
FLTMODE2: FlightMode2  
FLTMODE3: FlightMode3  
FLTMODE4: FlightMode4  
FLTMODE5: FlightMode5  
FLTMODE6: FlightMode6  
INITIAL_MODE: Initial flight mode  
LIM_ROLL_CD: Maximum Bank Angle  
LIM_PITCH_MAX: Maximum Pitch Angle  
LIM_PITCH_MIN: Minimum Pitch Angle  
ACRO_ROLL_RATE: ACRO mode roll rate  
ACRO_PITCH_RATE: ACRO mode pitch rate  
ACRO_LOCKING: ACRO mode attitude locking  
GROUND_STEER_ALT: Ground steer altitude  
GROUND_STEER_DPS: Ground steer rate  
TRIM_AUTO: Automatic trim adjustment  
MIXING_GAIN: Mixing Gain  
RUDDER_ONLY: Rudder only aircraft  
MIXING_OFFSET: Mixing Offset  
DSPOILR_RUD_RATE: Differential spoilers rudder rate  
SYS_NUM_RESETS: Num Resets  
LOG_BITMASK: Log bitmask  
RST_SWITCH_CH: Reset Switch Channel  
RST_MISSION_CH: Reset Mission Channel  
TRIM_ARSPD_CM: Target airspeed  
SCALING_SPEED: speed used for speed scaling calculations  
MIN_GNDSPD_CM: Minimum ground speed  
TRIM_PITCH_CD: Pitch angle offset  
ALT_HOLD_RTL: RTL altitude  
ALT_HOLD_FBWCM: Minimum altitude for FBWB mode  
FLAP_IN_CHANNEL: Flap input channel  
FLAP_1_PERCNT: Flap 1 percentage  
FLAP_1_SPEED: Flap 1 speed  
FLAP_2_PERCNT: Flap 2 percentage  
FLAP_2_SPEED: Flap 2 speed  
OVERRIDE_CHAN: IO override channel  
OVERRIDE_SAFETY: IO override safety switch  
HIL_MODE: HIL mode enable  
HIL_SERVOS: HIL Servos enable  
HIL_ERR_LIMIT: Limit of error in HIL attitude before reset  
RTL_AUTOLAND: RTL auto land  
CRASH_ACC_THRESH: Crash Deceleration Threshold  
CRASH_DETECT: Crash Detection  
CHUTE_CHAN: Parachute release channel  
RNGFND_LANDING: Enable rangefinder for landing  
SYSID_ENFORCE: GCS sysid enforcement  
RUDD_DT_GAIN: rudder differential thrust gain  
MANUAL_RCMASK: Manual R/C pass-through mask  
HOME_RESET_ALT: Home reset altitude threshold  
FLIGHT_OPTIONS: Flight mode options  
TKOFF_ACCEL_CNT: Takeoff throttle acceleration count  
DSPOILER_CROW_W1: Differential spoiler crow flaps outer weight  
DSPOILER_CROW_W2: Differential spoiler crow flaps inner weight  
TKOFF_TIMEOUT: Takeoff timeout  
DSPOILER_OPTS: Differential spoiler and crow flaps options  
DSPOILER_AILMTCH: Differential spoiler aileron matching  


# ADSB_ Parameters

ADSB_ENABLE: Enable ADSB  
ADSB_LIST_MAX: ADSB vehicle list size  
ADSB_LIST_RADIUS: ADSB vehicle list radius filter  
ADSB_ICAO_ID: ICAO_ID vehicle identification number  
ADSB_EMIT_TYPE: Emitter type  
ADSB_LEN_WIDTH: Aircraft length and width  
ADSB_OFFSET_LAT: GPS antenna lateral offset  
ADSB_OFFSET_LON: GPS antenna longitudinal offset  
ADSB_RF_SELECT: Transceiver RF selection  
ADSB_SQUAWK: Squawk code  
ADSB_RF_CAPABLE: RF capabilities  
ADSB_LIST_ALT: ADSB vehicle list altitude filter  
ADSB_ICAO_SPECL: ICAO_ID of special vehicle  
ADSB_LOG: ADS-B logging  
 
 
# AFS_ Parameters

AFS_ENABLE: Enable Advanced Failsafe  
AFS_MAN_PIN: Manual Pin  
AFS_HB_PIN: Heartbeat Pin  
AFS_WP_COMMS: Comms Waypoint  
AFS_GPS_LOSS: GPS Loss Waypoint  
AFS_TERMINATE: Force Terminate  
AFS_TERM_ACTION: Terminate action  
AFS_TERM_PIN: Terminate Pin  
AFS_AMSL_LIMIT: AMSL limit  
AFS_AMSL_ERR_GPS: Error margin for GPS based AMSL limit  
AFS_QNH_PRESSURE: QNH pressure  
AFS_MAX_GPS_LOSS: Maximum number of GPS loss events  
AFS_MAX_COM_LOSS: Maximum number of comms loss events  
AFS_GEOFENCE: Enable geofence Advanced Failsafe  
AFS_RC: Enable RC Advanced Failsafe  
AFS_RC_MAN_ONLY: Enable RC Termination only in manual control modes  
AFS_DUAL_LOSS: Enable dual loss terminate due to failure of both GCS and GPS simultaneously  
AFS_RC_FAIL_TIME: RC failure time  


# AHRS_ Parameters

AHRS_GPS_GAIN: AHRS GPS gain  
AHRS_GPS_USE: AHRS use GPS for navigation  
AHRS_YAW_P: Yaw P  
AHRS_RP_P: AHRS RP_P  
AHRS_WIND_MAX: Maximum wind  
AHRS_TRIM_X: AHRS Trim Roll  
AHRS_TRIM_Y: AHRS Trim Pitch  
AHRS_TRIM_Z: AHRS Trim Yaw  
AHRS_ORIENTATION: Board Orientation  
AHRS_COMP_BETA: AHRS Velocity Complementary Filter Beta Coefficient  
AHRS_GPS_MINSATS: AHRS GPS Minimum satellites  
AHRS_EKF_TYPE: Use NavEKF Kalman filter for attitude and position estimation  
AHRS_CUSTOM_ROLL: Board orientation roll offset  
AHRS_CUSTOM_PIT: Board orientation pitch offset  
AHRS_CUSTOM_YAW: Board orientation yaw offset  


# ARMING_ Parameters

ARMING_REQUIRE: Require Arming Motors  
ARMING_ACCTHRESH: Accelerometer error threshold  
ARMING_RUDDER: Arming with Rudder enable/disable  
ARMING_MIS_ITEMS: Required mission items  
ARMING_CHECK: Arm Checks to Peform (bitmask)  


# ARSPD Parameters

ARSPD_TYPE: Airspeed type  
ARSPD_USE: Airspeed use  
ARSPD_OFFSET: Airspeed offset  
ARSPD_RATIO: Airspeed ratio  
ARSPD_PIN: Airspeed pin  
ARSPD_AUTOCAL: Automatic airspeed ratio calibration  
ARSPD_TUBE_ORDER: Control pitot tube order  
ARSPD_SKIP_CAL: Skip airspeed calibration on startup  
ARSPD_PSI_RANGE: The PSI range of the device  
ARSPD_BUS: Airspeed I2C bus  
ARSPD_PRIMARY: Primary airspeed sensor  
ARSPD_OPTIONS: Airspeed options bitmask  
ARSPD2_TYPE: Second Airspeed type  
ARSPD2_USE: Enable use of 2nd airspeed sensor  
ARSPD2_OFFSET: Airspeed offset for 2nd airspeed sensor  
ARSPD2_RATIO: Airspeed ratio for 2nd airspeed sensor  
ARSPD2_PIN: Airspeed pin for 2nd airspeed sensor  
ARSPD2_AUTOCAL: Automatic airspeed ratio calibration for 2nd airspeed sensor  
ARSPD2_TUBE_ORDR: Control pitot tube order of 2nd airspeed sensor  
ARSPD2_SKIP_CAL: Skip airspeed calibration on startup for 2nd sensor  
ARSPD2_PSI_RANGE: The PSI range of the device for 2nd sensor  
ARSPD2_BUS: Airspeed I2C bus for 2nd sensor  
 

# AVD_ Parameters

AVD_ENABLE: Enable Avoidance using ADSB  
AVD_F_RCVRY: Recovery behaviour after a fail event  
AVD_OBS_MAX: Maximum number of obstacles to track  
AVD_W_TIME: Time Horizon Warn  
AVD_F_TIME: Time Horizon Fail  
AVD_W_DIST_XY: Distance Warn XY  
AVD_F_DIST_XY: Distance Fail XY  
AVD_W_DIST_Z: Distance Warn Z  
AVD_F_DIST_Z: Distance Fail Z  
AVD_F_ALT_MIN: ADS-B avoidance minimum altitude  


# BATT2_ Parameters

BATT2_MONITOR: Battery monitoring  
BATT2_VOLT_PIN: Battery Voltage sensing pin  
BATT2_CURR_PIN: Battery Current sensing pin  
BATT2_VOLT_MULT: Voltage Multiplier  
BATT2_AMP_PERVLT: Amps per volt  
BATT2_AMP_OFFSET: AMP offset  
BATT2_CAPACITY: Battery capacity  
BATT2_WATT_MAX: Maximum allowed power (Watts)  
BATT2_SERIAL_NUM: Battery serial number  
BATT2_LOW_TIMER: Low voltage timeout  
BATT2_FS_VOLTSRC: Failsafe voltage source  
BATT2_LOW_VOLT: Low battery voltage  
BATT2_LOW_MAH: Low battery capacity  
BATT2_CRT_VOLT: Critical battery voltage  
BATT2_CRT_MAH: Battery critical capacity  
BATT2_FS_LOW_ACT: Low battery failsafe action  
BATT2_FS_CRT_ACT: Critical battery failsafe action  
BATT2_ARM_VOLT: Required arming voltage  
BATT2_ARM_MAH: Required arming remaining capacity  


# BATT3_ Parameters

BATT3_MONITOR: Battery monitoring  
BATT3_VOLT_PIN: Battery Voltage sensing pin  
BATT3_CURR_PIN: Battery Current sensing pin  
BATT3_VOLT_MULT: Voltage Multiplier  
BATT3_AMP_PERVLT: Amps per volt  
BATT3_AMP_OFFSET: AMP offset  
BATT3_CAPACITY: Battery capacity  
BATT3_WATT_MAX: Maximum allowed power (Watts)  
BATT3_SERIAL_NUM: Battery serial number  
BATT3_LOW_TIMER: Low voltage timeout  
BATT3_FS_VOLTSRC: Failsafe voltage source  
BATT3_LOW_VOLT: Low battery voltage  
BATT3_LOW_MAH: Low battery capacity  
BATT3_CRT_VOLT: Critical battery voltage  
BATT3_CRT_MAH: Battery critical capacity  
BATT3_FS_LOW_ACT: Low battery failsafe action  
BATT3_FS_CRT_ACT: Critical battery failsafe action  
BATT3_ARM_VOLT: Required arming voltage  
BATT3_ARM_MAH: Required arming remaining capacity  


# BATT4_ Parameters

BATT4_MONITOR: Battery monitoring  
BATT4_VOLT_PIN: Battery Voltage sensing pin  
BATT4_CURR_PIN: Battery Current sensing pin  
BATT4_VOLT_MULT: Voltage Multiplier  
BATT4_AMP_PERVLT: Amps per volt  
BATT4_AMP_OFFSET: AMP offset  
BATT4_CAPACITY: Battery capacity  
BATT4_WATT_MAX: Maximum allowed power (Watts)  
BATT4_SERIAL_NUM: Battery serial number  
BATT4_LOW_TIMER: Low voltage timeout  
BATT4_FS_VOLTSRC: Failsafe voltage source  
BATT4_LOW_VOLT: Low battery voltage  
BATT4_LOW_MAH: Low battery capacity  
BATT4_CRT_VOLT: Critical battery voltage  
BATT4_CRT_MAH: Battery critical capacity  
BATT4_FS_LOW_ACT: Low battery failsafe action  
BATT4_FS_CRT_ACT: Critical battery failsafe action  
BATT4_ARM_VOLT: Required arming voltage  
BATT4_ARM_MAH: Required arming remaining capacity  


# BATT5_ Parameters

BATT5_MONITOR: Battery monitoring  
BATT5_VOLT_PIN: Battery Voltage sensing pin  
BATT5_CURR_PIN: Battery Current sensing pin  
BATT5_VOLT_MULT: Voltage Multiplier  
BATT5_AMP_PERVLT: Amps per volt  
BATT5_AMP_OFFSET: AMP offset  
BATT5_CAPACITY: Battery capacity  
BATT5_WATT_MAX: Maximum allowed power (Watts)  
BATT5_SERIAL_NUM: Battery serial number  
BATT5_LOW_TIMER: Low voltage timeout  
BATT5_FS_VOLTSRC: Failsafe voltage source  
BATT5_LOW_VOLT: Low battery voltage  
BATT5_LOW_MAH: Low battery capacity  
BATT5_CRT_VOLT: Critical battery voltage  
BATT5_CRT_MAH: Battery critical capacity  
BATT5_FS_LOW_ACT: Low battery failsafe action  
BATT5_FS_CRT_ACT: Critical battery failsafe action  
BATT5_ARM_VOLT: Required arming voltage  
BATT5_ARM_MAH: Required arming remaining capacity  


# BATT6_ Parameters

BATT6_MONITOR: Battery monitoring  
BATT6_VOLT_PIN: Battery Voltage sensing pin  
BATT6_CURR_PIN: Battery Current sensing pin  
BATT6_VOLT_MULT: Voltage Multiplier  
BATT6_AMP_PERVLT: Amps per volt  
BATT6_AMP_OFFSET: AMP offset  
BATT6_CAPACITY: Battery capacity  
BATT6_WATT_MAX: Maximum allowed power (Watts)  
BATT6_SERIAL_NUM: Battery serial number  
BATT6_LOW_TIMER: Low voltage timeout  
BATT6_FS_VOLTSRC: Failsafe voltage source  
BATT6_LOW_VOLT: Low battery voltage  
BATT6_LOW_MAH: Low battery capacity  
BATT6_CRT_VOLT: Critical battery voltage  
BATT6_CRT_MAH: Battery critical capacity  
BATT6_FS_LOW_ACT: Low battery failsafe action  
BATT6_FS_CRT_ACT: Critical battery failsafe action  
BATT6_ARM_VOLT: Required arming voltage  
BATT6_ARM_MAH: Required arming remaining capacity  


# BATT7_ Parameters

BATT7_MONITOR: Battery monitoring  
BATT7_VOLT_PIN: Battery Voltage sensing pin  
BATT7_CURR_PIN: Battery Current sensing pin  
BATT7_VOLT_MULT: Voltage Multiplier  
BATT7_AMP_PERVLT: Amps per volt  
BATT7_AMP_OFFSET: AMP offset  
BATT7_CAPACITY: Battery capacity  
BATT7_WATT_MAX: Maximum allowed power (Watts)  
BATT7_SERIAL_NUM: Battery serial number  
BATT7_LOW_TIMER: Low voltage timeout  
BATT7_FS_VOLTSRC: Failsafe voltage source  
BATT7_LOW_VOLT: Low battery voltage  
BATT7_LOW_MAH: Low battery capacity  
BATT7_CRT_VOLT: Critical battery voltage  
BATT7_CRT_MAH: Battery critical capacity  
BATT7_FS_LOW_ACT: Low battery failsafe action  
BATT7_FS_CRT_ACT: Critical battery failsafe action  
BATT7_ARM_VOLT: Required arming voltage  
BATT7_ARM_MAH: Required arming remaining capacity  


# BATT8_ Parameters

BATT8_MONITOR: Battery monitoring  
BATT8_VOLT_PIN: Battery Voltage sensing pin  
BATT8_CURR_PIN: Battery Current sensing pin  
BATT8_VOLT_MULT: Voltage Multiplier  
BATT8_AMP_PERVLT: Amps per volt  
BATT8_AMP_OFFSET: AMP offset  
BATT8_CAPACITY: Battery capacity  
BATT8_WATT_MAX: Maximum allowed power (Watts)  
BATT8_SERIAL_NUM: Battery serial number  
BATT8_LOW_TIMER: Low voltage timeout  
BATT8_FS_VOLTSRC: Failsafe voltage source  
BATT8_LOW_VOLT: Low battery voltage  
BATT8_LOW_MAH: Low battery capacity  
BATT8_CRT_VOLT: Critical battery voltage  
BATT8_CRT_MAH: Battery critical capacity  
BATT8_FS_LOW_ACT: Low battery failsafe action  
BATT8_FS_CRT_ACT: Critical battery failsafe action  
BATT8_ARM_VOLT: Required arming voltage  
BATT8_ARM_MAH: Required arming remaining capacity  


# BATT9_ Parameters

BATT9_MONITOR: Battery monitoring  
BATT9_VOLT_PIN: Battery Voltage sensing pin  
BATT9_CURR_PIN: Battery Current sensing pin  
BATT9_VOLT_MULT: Voltage Multiplier  
BATT9_AMP_PERVLT: Amps per volt  
BATT9_AMP_OFFSET: AMP offset  
BATT9_CAPACITY: Battery capacity  
BATT9_WATT_MAX: Maximum allowed power (Watts)  
BATT9_SERIAL_NUM: Battery serial number  
BATT9_LOW_TIMER: Low voltage timeout  
BATT9_FS_VOLTSRC: Failsafe voltage source  
BATT9_LOW_VOLT: Low battery voltage  
BATT9_LOW_MAH: Low battery capacity  
BATT9_CRT_VOLT: Critical battery voltage  
BATT9_CRT_MAH: Battery critical capacity  
BATT9_FS_LOW_ACT: Low battery failsafe action  
BATT9_FS_CRT_ACT: Critical battery failsafe action  
BATT9_ARM_VOLT: Required arming voltage  
BATT9_ARM_MAH: Required arming remaining capacity  


# BATT_ Parameters

BATT_MONITOR: Battery monitoring  
BATT_VOLT_PIN: Battery Voltage sensing pin  
BATT_CURR_PIN: Battery Current sensing pin  
BATT_VOLT_MULT: Voltage Multiplier  
BATT_AMP_PERVLT: Amps per volt  
BATT_AMP_OFFSET: AMP offset  
BATT_CAPACITY: Battery capacity  
BATT_WATT_MAX: Maximum allowed power (Watts)  
BATT_SERIAL_NUM: Battery serial number  
BATT_LOW_TIMER: Low voltage timeout  
BATT_FS_VOLTSRC: Failsafe voltage source  
BATT_LOW_VOLT: Low battery voltage  
BATT_LOW_MAH: Low battery capacity  
BATT_CRT_VOLT: Critical battery voltage  
BATT_CRT_MAH: Battery critical capacity  
BATT_FS_LOW_ACT: Low battery failsafe action  
BATT_FS_CRT_ACT: Critical battery failsafe action  
BATT_ARM_VOLT: Required arming voltage  
BATT_ARM_MAH: Required arming remaining capacity  


# BRD_ Parameters

BRD_PWM_COUNT: Auxiliary pin config  
BRD_SER1_RTSCTS: Serial 1 flow control  
BRD_SER2_RTSCTS: Serial 2 flow control  
BRD_SAFETYENABLE: Enable use of safety arming switch  
BRD_SBUS_OUT: SBUS output rate  
BRD_SERIAL_NUM: User-defined serial number  
BRD_SAFETY_MASK: Channels which ignore the safety switch state  
BRD_IMU_TARGTEMP: Target IMU temperature  
BRD_TYPE: Board type  
BRD_IO_ENABLE: Enable IO co-processor  
BRD_SAFETYOPTION: Options for safety button behavior  
BRD_VBUS_MIN: Autopilot board voltage requirement  
BRD_VSERVO_MIN: Servo voltage requirement  
BRD_SD_SLOWDOWN: microSD slowdown  
BRD_PWM_VOLT_SEL: Set PWM Out Voltage  
BRD_OPTIONS: Board options  
BRD_BOOT_DELAY: Boot delay  


# BRD_RADIO Parameters

BRD_RADIO_TYPE: Set type of direct attached radio  
BRD_RADIO_PROT: protocol  
BRD_RADIO_DEBUG: debug level  
BRD_RADIO_DISCRC: disable receive CRC  
BRD_RADIO_SIGCH: RSSI signal strength  
BRD_RADIO_PPSCH: Packet rate channel  
BRD_RADIO_TELEM: Enable telemetry  
BRD_RADIO_TXPOW: Telemetry Transmit power  
BRD_RADIO_FCCTST: Put radio into FCC test mode  
BRD_RADIO_STKMD: Stick input mode  
BRD_RADIO_TESTCH: Set radio to factory test channel  
BRD_RADIO_TSIGCH: RSSI value channel for telemetry data on transmitter  
BRD_RADIO_TPPSCH: Telemetry PPS channel  
BRD_RADIO_TXMAX: Transmitter transmit power  
BRD_RADIO_BZOFS: Transmitter buzzer adjustment  
BRD_RADIO_ABTIME: Auto-bind time  
BRD_RADIO_ABLVL: Auto-bind level  


# BRD_RTC Parameters

BRD_RTC_TYPES: Allowed sources of RTC time  


# BTN_ Parameters

BTN_ENABLE: Enable button reporting  
BTN_PIN1: First button Pin  
BTN_PIN2: Second button Pin  
BTN_PIN3: Third button Pin  
BTN_PIN4: Fourth button Pin  
BTN_REPORT_SEND: Report send time  


# CAM_ Parameters

CAM_TRIGG_TYPE: Camera shutter (trigger) type  
CAM_DURATION: Duration that shutter is held open  
CAM_SERVO_ON: Servo ON PWM value  
CAM_SERVO_OFF: Servo OFF PWM value  
CAM_TRIGG_DIST: Camera trigger distance  
CAM_RELAY_ON: Relay ON value  
CAM_MIN_INTERVAL: Minimum time between photos  
CAM_MAX_ROLL: Maximum photo roll angle.  
CAM_FEEDBACK_PIN: Camera feedback pin  
CAM_FEEDBACK_POL: Camera feedback pin polarity  
CAM_AUTO_ONLY: Distance-trigging in AUTO mode only  
CAM_TYPE: Type of camera (0: None, 1: BMMCC)  


# CAN_D1_ Parameters

CAN_D1_PROTOCOL: Enable use of specific protocol over virtual driver  


# CAN_D1_KDE_ Parameters

CAN_D1_KDE_NPOLE: Number of motor poles  


# CAN_D1_UC_ Parameters

CAN_D1_UC_NODE: UAVCAN node that is used for this network  
CAN_D1_UC_SRV_BM: RC Out channels to be transmitted as servo over UAVCAN  
CAN_D1_UC_ESC_BM: RC Out channels to be transmitted as ESC over UAVCAN  
CAN_D1_UC_SRV_RT: Servo output rate  


# CAN_D2_ Parameters

CAN_D2_PROTOCOL: Enable use of specific protocol over virtual driver  


# CAN_D2_KDE_ Parameters

CAN_D2_KDE_NPOLE: Number of motor poles  



# CAN_D2_UC_ Parameters

CAN_D2_UC_NODE: UAVCAN node that is used for this network  
CAN_D2_UC_SRV_BM: RC Out channels to be transmitted as servo over UAVCAN  
CAN_D2_UC_ESC_BM: RC Out channels to be transmitted as ESC over UAVCAN  
CAN_D2_UC_SRV_RT: Servo output rate  

# CAN_D3_ Parameters

CAN_D3_PROTOCOL: Enable use of specific protocol over virtual driver  

# CAN_D3_KDE_ Parameters

CAN_D3_KDE_NPOLE: Number of motor poles  

# CAN_D3_UC_ Parameters

CAN_D3_UC_NODE: UAVCAN node that is used for this network  
CAN_D3_UC_SRV_BM: RC Out channels to be transmitted as servo over UAVCAN  
CAN_D3_UC_ESC_BM: RC Out channels to be transmitted as ESC over UAVCAN  
CAN_D3_UC_SRV_RT: Servo output rate  

# CAN_P1_ Parameters

CAN_P1_DRIVER: Index of virtual driver to be used with physical CAN interface  
CAN_P1_BITRATE: Bitrate of CAN interface  
CAN_P1_DEBUG: Level of debug for CAN devices  

# CAN_P2_ Parameters

CAN_P2_DRIVER: Index of virtual driver to be used with physical CAN interface  
CAN_P2_BITRATE: Bitrate of CAN interface  
CAN_P2_DEBUG: Level of debug for CAN devices  


# CAN_P3_ Parameters

CAN_P3_DRIVER: Index of virtual driver to be used with physical CAN interface  
CAN_P3_BITRATE: Bitrate of CAN interface  
CAN_P3_DEBUG: Level of debug for CAN devices  

# CAN_SLCAN_ Parameters

CAN_SLCAN_CPORT: SLCAN Route  
CAN_SLCAN_SERNUM: SLCAN Serial Port  
CAN_SLCAN_TIMOUT: SLCAN Timeout  

# CHUTE_ Parameters

CHUTE_ENABLED: Parachute release enabled or disabled  
CHUTE_TYPE: Parachute release mechanism type (relay or servo)  
CHUTE_SERVO_ON: Parachute Servo ON PWM value  
CHUTE_SERVO_OFF: Servo OFF PWM value  
CHUTE_ALT_MIN: Parachute min altitude in meters above home  
CHUTE_DELAY_MS: Parachute release delay  
CHUTE_CRT_SINK: Critical sink speed rate in m/s to trigger emergency parachute  


# COMPASS_ Parameters

COMPASS_OFS_X: Compass offsets in milligauss on the X axis  
COMPASS_OFS_Y: Compass offsets in milligauss on the Y axis  
COMPASS_OFS_Z: Compass offsets in milligauss on the Z axis  
COMPASS_DEC: Compass declination  
COMPASS_LEARN: Learn compass offsets automatically  
COMPASS_USE: Use compass for yaw  
COMPASS_AUTODEC: Auto Declination  
COMPASS_MOTCT: Motor interference compensation type  
COMPASS_MOT_X: Motor interference compensation for body frame X axis  
COMPASS_MOT_Y: Motor interference compensation for body frame Y axis  
COMPASS_MOT_Z: Motor interference compensation for body frame Z axis  
COMPASS_ORIENT: Compass orientation  
COMPASS_EXTERNAL: Compass is attached via an external cable  
COMPASS_OFS2_X: Compass2 offsets in milligauss on the X axis  
COMPASS_OFS2_Y: Compass2 offsets in milligauss on the Y axis  
COMPASS_OFS2_Z: Compass2 offsets in milligauss on the Z axis  
COMPASS_MOT2_X: Motor interference compensation to compass2 for body frame X axis  
COMPASS_MOT2_Y: Motor interference compensation to compass2 for body frame Y axis  
COMPASS_MOT2_Z: Motor interference compensation to compass2 for body frame Z axis  
COMPASS_PRIMARY: Choose primary compass  
COMPASS_OFS3_X: Compass3 offsets in milligauss on the X axis  
COMPASS_OFS3_Y: Compass3 offsets in milligauss on the Y axis  
COMPASS_OFS3_Z: Compass3 offsets in milligauss on the Z axis  
COMPASS_MOT3_X: Motor interference compensation to compass3 for body frame X axis  
COMPASS_MOT3_Y: Motor interference compensation to compass3 for body frame Y axis  
COMPASS_MOT3_Z: Motor interference compensation to compass3 for body frame Z axis  
COMPASS_DEV_ID: Compass device id  
COMPASS_DEV_ID2: Compass2 device id  
COMPASS_DEV_ID3: Compass3 device id  
COMPASS_USE2: Compass2 used for yaw  
COMPASS_ORIENT2: Compass2 orientation  
COMPASS_EXTERN2: Compass2 is attached via an external cable  
COMPASS_USE3: Compass3 used for yaw  
COMPASS_ORIENT3: Compass3 orientation  
COMPASS_DIA_X: Compass soft-iron diagonal X component  
COMPASS_DIA_Y: Compass soft-iron diagonal Y component  
COMPASS_DIA_Z: Compass soft-iron diagonal Z component  
COMPASS_ODI_X: Compass soft-iron off-diagonal X component  
COMPASS_ODI_Y: Compass soft-iron off-diagonal Y component  
COMPASS_ODI_Z: Compass soft-iron off-diagonal Z component  
COMPASS_DIA2_X: Compass2 soft-iron diagonal X component  
COMPASS_DIA2_Y: Compass2 soft-iron diagonal Y component  
COMPASS_DIA2_Z: Compass2 soft-iron diagonal Z component  
COMPASS_ODI2_X: Compass2 soft-iron off-diagonal X component  
COMPASS_ODI2_Y: Compass2 soft-iron off-diagonal Y component  
COMPASS_ODI2_Z: Compass2 soft-iron off-diagonal Z component  
COMPASS_DIA3_X: Compass3 soft-iron diagonal X component  
COMPASS_DIA3_Y: Compass3 soft-iron diagonal Y component  
COMPASS_DIA3_Z: Compass3 soft-iron diagonal Z component  
COMPASS_ODI3_X: Compass3 soft-iron off-diagonal X component  
COMPASS_ODI3_Y: Compass3 soft-iron off-diagonal Y component  
COMPASS_ODI3_Z: Compass3 soft-iron off-diagonal Z component  
COMPASS_CAL_FIT: Compass calibration fitness  
COMPASS_OFFS_MAX: Compass maximum offset  
COMPASS_TYPEMASK: Compass disable driver type mask  
COMPASS_FLTR_RNG: Range in which sample is accepted  
COMPASS_AUTO_ROT: Automatically check orientation  
COMPASS_EXP_DID: Compass device id expected  
COMPASS_EXP_DID2: Compass2 device id expected  
COMPASS_EXP_DID3: Compass3 device id expected  
COMPASS_ENABLE: Enable Compass  


# COMPASS_PMOT Parameters

COMPASS_PMOT_EN: per-motor compass correction enable  
COMPASS_PMOT_EXP: per-motor exponential correction  
COMPASS_PMOT1_X: Compass per-motor1 X  
COMPASS_PMOT1_Y: Compass per-motor1 Y  
COMPASS_PMOT1_Z: Compass per-motor1 Z  
COMPASS_PMOT2_X: Compass per-motor2 X  
COMPASS_PMOT2_Y: Compass per-motor2 Y  
COMPASS_PMOT2_Z: Compass per-motor2 Z  
COMPASS_PMOT3_X: Compass per-motor3 X  
COMPASS_PMOT3_Y: Compass per-motor3 Y  
COMPASS_PMOT3_Z: Compass per-motor3 Z  
COMPASS_PMOT4_X: Compass per-motor4 X  
COMPASS_PMOT4_Y: Compass per-motor4 Y  
COMPASS_PMOT4_Z: Compass per-motor4 Z  


# EK2_ Parameters
EK2_ENABLE: Enable EKF2  
EK2_GPS_TYPE: GPS mode control  
EK2_VELNE_M_NSE: GPS horizontal velocity measurement noise (m/s)  
EK2_VELD_M_NSE: GPS vertical velocity measurement noise (m/s)  
EK2_VEL_I_GATE: GPS velocity innovation gate size  
EK2_POSNE_M_NSE: GPS horizontal position measurement noise (m)  
EK2_POS_I_GATE: GPS position measurement gate size  
EK2_GLITCH_RAD: GPS glitch radius gate size (m)  
EK2_ALT_SOURCE: Primary altitude sensor source  
EK2_ALT_M_NSE: Altitude measurement noise (m)  
EK2_HGT_I_GATE: Height measurement gate size  
EK2_HGT_DELAY: Height measurement delay (msec)  
EK2_MAG_M_NSE: Magnetometer measurement noise (Gauss)  
EK2_MAG_CAL: Magnetometer default fusion mode  
EK2_MAG_I_GATE: Magnetometer measurement gate size  
EK2_EAS_M_NSE: Equivalent airspeed measurement noise (m/s)  
EK2_EAS_I_GATE: Airspeed measurement gate size  
EK2_RNG_M_NSE: Range finder measurement noise (m)  
EK2_RNG_I_GATE: Range finder measurement gate size  
EK2_MAX_FLOW: Maximum valid optical flow rate  
EK2_FLOW_M_NSE: Optical flow measurement noise (rad/s)  
EK2_FLOW_I_GATE: Optical Flow measurement gate size  
EK2_FLOW_DELAY: Optical Flow measurement delay (msec)  
EK2_GYRO_P_NSE: Rate gyro noise (rad/s)  
EK2_ACC_P_NSE: Accelerometer noise (m/s^2)  
EK2_GBIAS_P_NSE: Rate gyro bias stability (rad/s/s)  
EK2_GSCL_P_NSE: Rate gyro scale factor stability (1/s)  
EK2_ABIAS_P_NSE: Accelerometer bias stability (m/s^3)  
EK2_WIND_P_NSE: Wind velocity process noise (m/s^2)  
EK2_WIND_PSCALE: Height rate to wind process noise scaler  
EK2_GPS_CHECK: GPS preflight check  
EK2_IMU_MASK: Bitmask of active IMUs  
EK2_CHECK_SCALE: GPS accuracy check scaler (%)  
EK2_NOAID_M_NSE: Non-GPS operation position uncertainty (m)  
EK2_LOG_MASK: EKF sensor logging IMU mask  
EK2_YAW_M_NSE: Yaw measurement noise (rad)  
EK2_YAW_I_GATE: Yaw measurement gate size  
EK2_TAU_OUTPUT: Output complementary filter time constant (centi-sec)  
EK2_MAGE_P_NSE: Earth magnetic field process noise (gauss/s)  
EK2_MAGB_P_NSE: Body magnetic field process noise (gauss/s)  
EK2_RNG_USE_HGT: Range finder switch height percentage  
EK2_TERR_GRAD: Maximum terrain gradient  
EK2_BCN_M_NSE: Range beacon measurement noise (m)  
EK2_BCN_I_GTE: Range beacon measurement gate size  
EK2_BCN_DELAY: Range beacon measurement delay (msec)  
EK2_RNG_USE_SPD: Range finder max ground speed  
EK2_MAG_MASK: Bitmask of active EKF cores that will always use heading fusion  
EK2_OGN_HGT_MASK: Bitmask control of EKF reference height correction  
EK2_EXTNAV_DELAY: external navigation system measurement delay (msec)  
EK2_FLOW_USE: Optical flow use bitmask  
EK2_MAG_EF_LIM: EarthField error limit  



# EK3_ Parameters

EK3_ENABLE: Enable EKF3  
EK3_GPS_TYPE: GPS mode control  
EK3_VELNE_M_NSE: GPS horizontal velocity measurement noise (m/s)  
EK3_VELD_M_NSE: GPS vertical velocity measurement noise (m/s)  
EK3_VEL_I_GATE: GPS velocity innovation gate size  
EK3_POSNE_M_NSE: GPS horizontal position measurement noise (m)  
EK3_POS_I_GATE: GPS position measurement gate size  
EK3_GLITCH_RAD: GPS glitch radius gate size (m)  
EK3_ALT_SOURCE: Primary altitude sensor source  
EK3_ALT_M_NSE: Altitude measurement noise (m)  
EK3_HGT_I_GATE: Height measurement gate size  
EK3_HGT_DELAY: Height measurement delay (msec)  
EK3_MAG_M_NSE: Magnetometer measurement noise (Gauss)  
EK3_MAG_CAL: Magnetometer default fusion mode  
EK3_MAG_I_GATE: Magnetometer measurement gate size  
EK3_EAS_M_NSE: Equivalent airspeed measurement noise (m/s)  
EK3_EAS_I_GATE: Airspeed measurement gate size  
EK3_RNG_M_NSE: Range finder measurement noise (m)  
EK3_RNG_I_GATE: Range finder measurement gate size  
EK3_MAX_FLOW: Maximum valid optical flow rate  
EK3_FLOW_M_NSE: Optical flow measurement noise (rad/s)  
EK3_FLOW_I_GATE: Optical Flow measurement gate size  
EK3_FLOW_DELAY: Optical Flow measurement delay (msec)  
EK3_GYRO_P_NSE: Rate gyro noise (rad/s)  
EK3_ACC_P_NSE: Accelerometer noise (m/s^2)  
EK3_GBIAS_P_NSE: Rate gyro bias stability (rad/s/s)  
EK3_ABIAS_P_NSE: Accelerometer bias stability (m/s^3)  
EK3_WIND_P_NSE: Wind velocity process noise (m/s^2)  
EK3_WIND_PSCALE: Height rate to wind process noise scaler  
EK3_GPS_CHECK: GPS preflight check  
EK3_IMU_MASK: Bitmask of active IMUs  
EK3_CHECK_SCALE: GPS accuracy check scaler (%)  
EK3_NOAID_M_NSE: Non-GPS operation position uncertainty (m)  
EK3_LOG_MASK: EKF sensor logging IMU mask  
EK3_YAW_M_NSE: Yaw measurement noise (rad)  
EK3_YAW_I_GATE: Yaw measurement gate size  
EK3_TAU_OUTPUT: Output complementary filter time constant (centi-sec)  
EK3_MAGE_P_NSE: Earth magnetic field process noise (gauss/s)  
EK3_MAGB_P_NSE: Body magnetic field process noise (gauss/s)  
EK3_RNG_USE_HGT: Range finder switch height percentage  
EK3_TERR_GRAD: Maximum terrain gradient  
EK3_BCN_M_NSE: Range beacon measurement noise (m)  
EK3_BCN_I_GTE: Range beacon measurement gate size  
EK3_BCN_DELAY: Range beacon measurement delay (msec)  
EK3_RNG_USE_SPD: Range finder max ground speed  
EK3_ACC_BIAS_LIM: Accelerometer bias limit  
EK3_MAG_MASK: Bitmask of active EKF cores that will always use heading fusion  
EK3_OGN_HGT_MASK: Bitmask control of EKF reference height correction  
EK3_VIS_VERR_MIN: Visual odometry minimum velocity error  
EK3_VIS_VERR_MAX: Visual odometry maximum velocity error  
EK3_WENC_VERR: Wheel odometry velocity error  
EK3_FLOW_USE: Optical flow use bitmask  

# FLOW Parameters

FLOW_TYPE: Optical flow sensor type  
FLOW_FXSCALER: X axis optical flow scale factor correction  
FLOW_FYSCALER: Y axis optical flow scale factor correction  
FLOW_ORIENT_YAW: Flow sensor yaw alignment  
FLOW_POS_X:  X position offset  
FLOW_POS_Y: Y position offset  
FLOW_POS_Z: Z position offset  
FLOW_ADDR: Address on the bus  
FLOW_ENABLE: Optical flow enable/disable  

# GND_ Parameters

GND_ABS_PRESS: Absolute Pressure  
GND_TEMP: ground temperature  
GND_ALT_OFFSET: altitude offset  
GND_PRIMARY: Primary barometer  
GND_EXT_BUS: External baro bus  
GND_SPEC_GRAV: Specific Gravity (For water depth measurement)  
GND_ABS_PRESS2: Absolute Pressure  
GND_ABS_PRESS3: Absolute Pressure  
GND_FLTR_RNG: Range in which sample is accepted  
GND_PROBE_EXT: External barometers to probe  

# GPS_ Parameters

GPS_TYPE: GPS type  
GPS_TYPE2: 2nd GPS type  
GPS_NAVFILTER: Navigation filter setting  
GPS_AUTO_SWITCH: Automatic Switchover Setting  
GPS_MIN_DGPS: Minimum Lock Type Accepted for DGPS  
GPS_SBAS_MODE: SBAS Mode  
GPS_MIN_ELEV: Minimum elevation  
GPS_INJECT_TO: Destination for GPS_INJECT_DATA MAVLink packets  
GPS_SBP_LOGMASK: Swift Binary Protocol Logging Mask  
GPS_RAW_DATA: Raw data logging  
GPS_GNSS_MODE: GNSS system configuration  
GPS_SAVE_CFG: Save GPS configuration  
GPS_GNSS_MODE2: GNSS system configuration  
GPS_AUTO_CONFIG: Automatic GPS configuration  
GPS_RATE_MS: GPS update rate in milliseconds  
GPS_RATE_MS2: GPS 2 update rate in milliseconds  
GPS_POS1_X: Antenna X position offset  
GPS_POS1_Y: Antenna Y position offset  
GPS_POS1_Z: Antenna Z position offset  
GPS_POS2_X: Antenna X position offset  
GPS_POS2_Y: Antenna Y position offset  
GPS_POS2_Z: Antenna Z position offset  
GPS_DELAY_MS: GPS delay in milliseconds  
GPS_DELAY_MS2: GPS 2 delay in milliseconds  
GPS_BLEND_MASK: Multi GPS Blending Mask  
GPS_BLEND_TC: Blending time constant  

# GRIP_ Parameters

GRIP_ENABLE: Gripper Enable/Disable  
GRIP_TYPE: Gripper Type  
GRIP_GRAB: Gripper Grab PWM  
GRIP_RELEASE: Gripper Release PWM  
GRIP_NEUTRAL: Neutral PWM  
GRIP_REGRAB: Gripper Regrab interval  
GRIP_UAVCAN_ID: EPM UAVCAN Hardpoint ID  

# ICE_ Parameters

ICE_ENABLE: Enable ICEngine control  
ICE_START_CHAN: Input channel for engine start  
ICE_STARTER_TIME: Time to run starter  
ICE_START_DELAY: Time to wait between starts  
ICE_RPM_THRESH: RPM threshold  
ICE_PWM_IGN_ON: PWM value for ignition on  
ICE_PWM_IGN_OFF: PWM value for ignition off  
ICE_PWM_STRT_ON: PWM value for starter on  
ICE_PWM_STRT_OFF: PWM value for starter off  
ICE_RPM_CHAN: RPM instance channel to use  
ICE_START_PCT: Throttle percentage for engine start  
ICE_IDLE_PCT: Throttle percentage for engine idle  

# INS_ Parameters

INS_GYROFFS_X: Gyro offsets of X axis  
INS_GYROFFS_Y: Gyro offsets of Y axis  
INS_GYROFFS_Z: Gyro offsets of Z axis  
INS_GYR2OFFS_X: Gyro2 offsets of X axis  
INS_GYR2OFFS_Y: Gyro2 offsets of Y axis  
INS_GYR2OFFS_Z: Gyro2 offsets of Z axis  
INS_GYR3OFFS_X: Gyro3 offsets of X axis  
INS_GYR3OFFS_Y: Gyro3 offsets of Y axis  
INS_GYR3OFFS_Z: Gyro3 offsets of Z axis  
INS_ACCSCAL_X: Accelerometer scaling of X axis  
INS_ACCSCAL_Y: Accelerometer scaling of Y axis  
INS_ACCSCAL_Z: Accelerometer scaling of Z axis  
INS_ACCOFFS_X: Accelerometer offsets of X axis  
INS_ACCOFFS_Y: Accelerometer offsets of Y axis  
INS_ACCOFFS_Z: Accelerometer offsets of Z axis  
INS_ACC2SCAL_X: Accelerometer2 scaling of X axis  
INS_ACC2SCAL_Y: Accelerometer2 scaling of Y axis  
INS_ACC2SCAL_Z: Accelerometer2 scaling of Z axis  
INS_ACC2OFFS_X: Accelerometer2 offsets of X axis  
INS_ACC2OFFS_Y: Accelerometer2 offsets of Y axis  
INS_ACC2OFFS_Z: Accelerometer2 offsets of Z axis  
INS_ACC3SCAL_X: Accelerometer3 scaling of X axis  
INS_ACC3SCAL_Y: Accelerometer3 scaling of Y axis  
INS_ACC3SCAL_Z: Accelerometer3 scaling of Z axis  
INS_ACC3OFFS_X: Accelerometer3 offsets of X axis  
INS_ACC3OFFS_Y: Accelerometer3 offsets of Y axis  
INS_ACC3OFFS_Z: Accelerometer3 offsets of Z axis  
INS_GYRO_FILTER: Gyro filter cutoff frequency  
INS_ACCEL_FILTER: Accel filter cutoff frequency  
INS_USE: Use first IMU for attitude, velocity and position estimates  
INS_USE2: Use second IMU for attitude, velocity and position estimates  
INS_USE3: Use third IMU for attitude, velocity and position estimates  
INS_STILL_THRESH: Stillness threshold for detecting if we are moving  
INS_GYR_CAL: Gyro Calibration scheme  
INS_TRIM_OPTION: Accel cal trim option  
INS_ACC_BODYFIX: Body-fixed accelerometer  
INS_POS1_X: IMU accelerometer X position  
INS_POS1_Y: IMU accelerometer Y position  
INS_POS1_Z: IMU accelerometer Z position  
INS_POS2_X: IMU accelerometer X position  
INS_POS2_Y: IMU accelerometer Y position  
INS_POS2_Z: IMU accelerometer Z position  
INS_POS3_X: IMU accelerometer X position  
INS_POS3_Y: IMU accelerometer Y position  
INS_POS3_Z: IMU accelerometer Z position  
INS_GYR_ID: Gyro ID  
INS_GYR2_ID: Gyro2 ID  
INS_GYR3_ID: Gyro3 ID  
INS_ACC_ID: Accelerometer ID  
INS_ACC2_ID: Accelerometer2 ID  
INS_ACC3_ID: Accelerometer3 ID  
INS_FAST_SAMPLE: Fast sampling mask  
INS_ENABLE_MASK: IMU enable mask  

# INS_LOG_ Parameters

INS_LOG_BAT_CNT: sample count per batch  
INS_LOG_BAT_MASK: Sensor Bitmask  
INS_LOG_BAT_OPT: Batch Logging Options Mask  
INS_LOG_BAT_LGIN: logging interval  
INS_LOG_BAT_LGCT: logging count  

# INS_NOTCH_ Parameters

INS_NOTCH_ENABLE: Enable  
INS_NOTCH_FREQ: Frequency  
INS_NOTCH_BW: Bandwidth  
INS_NOTCH_ATT: Attenuation  

# LAND_ Parameters

LAND_SLOPE_RCALC: Landing slope re-calc threshold  
LAND_ABORT_DEG: Landing auto-abort slope threshold  
LAND_PITCH_CD: Landing Pitch  
LAND_FLARE_ALT: Landing flare altitude  
LAND_FLARE_SEC: Landing flare time  
LAND_PF_ALT: Landing pre-flare altitude  
LAND_PF_SEC: Landing pre-flare time  
LAND_PF_ARSPD: Landing pre-flare airspeed  
LAND_THR_SLEW: Landing throttle slew rate  
LAND_DISARMDELAY: Landing disarm delay  
LAND_THEN_NEUTRL: Set servos to neutral after landing  
LAND_ABORT_THR: Landing abort using throttle  
LAND_FLAP_PERCNT: Landing flap percentage  
LAND_TYPE: Auto-landing type  

# LAND_DS_ Parameters

LAND_DS_V_FWD: Deepstall forward velocity  
LAND_DS_SLOPE_A: Deepstall slope a  
LAND_DS_SLOPE_B: Deepstall slope b  
LAND_DS_APP_EXT: Deepstall approach extension  
LAND_DS_V_DWN: Deepstall velocity down  
LAND_DS_SLEW_SPD: Deepstall slew speed  
LAND_DS_ELEV_PWM: Deepstall elevator PWM  
LAND_DS_ARSP_MAX: Deepstall enabled airspeed  
LAND_DS_ARSP_MIN: Deepstall minimum derating airspeed  
LAND_DS_L1: Deepstall L1 period  
LAND_DS_L1_I: Deepstall L1 I gain  
LAND_DS_AIL_SCL: Aileron landing gain scalaing  

# LAND_DS_DS_ Parameters

LAND_DS_DS_P: PID Proportional Gain  
LAND_DS_DS_I: PID Integral Gain  
LAND_DS_DS_D: PID Derivative Gain  
LAND_DS_DS_IMAX: PID Integral Maximum  


# LGR_ Parameters

LGR_STARTUP: Landing Gear Startup position  
LGR_DEPLOY_PIN: Chassis deployment feedback pin  
LGR_DEPLOY_POL: Chassis deployment feedback pin polarity  
LGR_WOW_PIN: Weight on wheels feedback pin  
LGR_WOW_POL: Weight on wheels feedback pin polarity  
LGR_DEPLOY_ALT: Landing gear deployment altitude  
LGR_RETRACT_ALT: Landing gear retract altitude  


# LOG Parameters

LOG_BACKEND_TYPE: AP_Logger Backend Storage type  
LOG_FILE_BUFSIZE: Maximum AP_Logger File Backend buffer size (in kilobytes)  
LOG_DISARMED: Enable logging while disarmed  
LOG_REPLAY: Enable logging of information needed for Replay  
LOG_FILE_DSRMROT: Stop logging to current file on disarm  
LOG_MAV_BUFSIZE: Maximum AP_Logger MAVLink Backend buffer size  


# MIS_ Parameters

MIS_TOTAL: Total mission commands  
MIS_RESTART: Mission Restart when entering Auto mode  
MIS_OPTIONS: Mission options bitmask  


# MNT Parameters

MNT_DEFLT_MODE: Mount default operating mode  
MNT_RETRACT_X: Mount roll angle when in retracted position  
MNT_RETRACT_Y: Mount tilt/pitch angle when in retracted position  
MNT_RETRACT_Z: Mount yaw/pan angle when in retracted position  
MNT_NEUTRAL_X: Mount roll angle when in neutral position  
MNT_NEUTRAL_Y: Mount tilt/pitch angle when in neutral position  
MNT_NEUTRAL_Z: Mount pan/yaw angle when in neutral position  
MNT_STAB_ROLL: Stabilize mount’s roll angle  
MNT_STAB_TILT: Stabilize mount’s pitch/tilt angle  
MNT_STAB_PAN: Stabilize mount pan/yaw angle  
MNT_RC_IN_ROLL: roll RC input channel  
MNT_ANGMIN_ROL: Minimum roll angle  
MNT_ANGMAX_ROL: Maximum roll angle  
MNT_RC_IN_TILT: tilt (pitch) RC input channel  
MNT_ANGMIN_TIL: Minimum tilt angle  
MNT_ANGMAX_TIL: Maximum tilt angle  
MNT_RC_IN_PAN: pan (yaw) RC input channel  
MNT_ANGMIN_PAN: Minimum pan angle  
MNT_ANGMAX_PAN: Maximum pan angle  
MNT_JSTICK_SPD: mount joystick speed  
MNT_LEAD_RLL: Roll stabilization lead time  
MNT_LEAD_PTCH: Pitch stabilization lead time  
MNT_TYPE: Mount Type  
MNT2_DEFLT_MODE: Mount default operating mode  
MNT2_RETRACT_X: Mount2 roll angle when in retracted position  
MNT2_RETRACT_Y: Mount2 tilt/pitch angle when in retracted position  
MNT2_RETRACT_Z: Mount2 yaw/pan angle when in retracted position  
MNT2_NEUTRAL_X: Mount2 roll angle when in neutral position  
MNT2_NEUTRAL_Y: Mount2 tilt/pitch angle when in neutral position  
MNT2_NEUTRAL_Z: Mount2 pan/yaw angle when in neutral position  
MNT2_STAB_ROLL: Stabilize Mount2’s roll angle  
MNT2_STAB_TILT: Stabilize Mount2’s pitch/tilt angle  
MNT2_STAB_PAN: Stabilize mount2 pan/yaw angle  
MNT2_RC_IN_ROLL: Mount2’s roll RC input channel  
MNT2_ANGMIN_ROL: Mount2’s minimum roll angle  
MNT2_ANGMAX_ROL: Mount2’s maximum roll angle  
MNT2_RC_IN_TILT: Mount2’s tilt (pitch) RC input channel  
MNT2_ANGMIN_TIL: Mount2’s minimum tilt angle  
MNT2_ANGMAX_TIL: Mount2’s maximum tilt angle  
MNT2_RC_IN_PAN: Mount2’s pan (yaw) RC input channel  
MNT2_ANGMIN_PAN: Mount2’s minimum pan angle  
MNT2_ANGMAX_PAN: Mount2’s maximum pan angle  
MNT2_LEAD_RLL: Mount2’s Roll stabilization lead time  
MNT2_LEAD_PTCH: Mount2’s Pitch stabilization lead time  
MNT2_TYPE: Mount2 Type  


# NAVL1_ Parameters

NAVL1_PERIOD: L1 control period  
NAVL1_DAMPING: L1 control damping ratio  
NAVL1_XTRACK_I: L1 control crosstrack integrator gain  
NAVL1_LIM_BANK: Loiter Radius Bank Angle Limit  


# NTF_ Parameters

NTF_LED_BRIGHT: LED Brightness  
NTF_BUZZ_ENABLE: Buzzer enable  
NTF_LED_OVERRIDE: Specifies colour source for the RGBLed  
NTF_DISPLAY_TYPE: Type of on-board I2C display  
NTF_OREO_THEME: OreoLED Theme  
NTF_BUZZ_PIN: Buzzer pin  
NTF_LED_TYPES: LED Driver Types  
NTF_BUZZ_ON_LVL: Buzzer-on pin logic level  


# OSD Parameters

OSD_TYPE: OSD type  
OSD_CHAN: Screen switch transmitter channel  
OSD_OPTIONS: OSD Options  
OSD_FONT: OSD Font  
OSD_V_OFFSET: OSD vertical offset  
OSD_H_OFFSET: OSD horizontal offset  
OSD_W_RSSI: RSSI warn level (in %)  
OSD_W_NSAT: NSAT warn level  
OSD_W_BATVOLT: BAT_VOLT warn level  
OSD_UNITS: Display Units  
OSD_MSG_TIME: Message display duration in seconds  
OSD_ARM_SCR: Arm screen  
OSD_DSARM_SCR: Disarm screen  
OSD_FS_SCR: Failsafe screen  


# OSD1_ Parameters

OSD1_ENABLE: Enable screen  
OSD1_CHAN_MIN: Transmitter switch screen minimum pwm  
OSD1_CHAN_MAX: Transmitter switch screen maximum pwm  
OSD1_ALTITUDE_EN: ALTITUDE_EN  
OSD1_ALTITUDE_X: ALTITUDE_X  
OSD1_ALTITUDE_Y: ALTITUDE_Y  
OSD1_BATVOLT_EN: BATVOLT_EN  
OSD1_BATVOLT_X: BATVOLT_X  
OSD1_BATVOLT_Y: BATVOLT_Y  
OSD1_RSSI_EN: RSSI_EN  
OSD1_RSSI_X: RSSI_X  
OSD1_RSSI_Y: RSSI_Y  
OSD1_CURRENT_EN: CURRENT_EN  
OSD1_CURRENT_X: CURRENT_X  
OSD1_CURRENT_Y: CURRENT_Y  
OSD1_BATUSED_EN: BATUSED_EN  
OSD1_BATUSED_X: BATUSED_X  
OSD1_BATUSED_Y: BATUSED_Y  
OSD1_SATS_EN: SATS_EN  
OSD1_SATS_X: SATS_X  
OSD1_SATS_Y: SATS_Y  
OSD1_FLTMODE_EN: FLTMODE_EN  
OSD1_FLTMODE_X: FLTMODE_X  
OSD1_FLTMODE_Y: FLTMODE_Y  
OSD1_MESSAGE_EN: MESSAGE_EN  
OSD1_MESSAGE_X: MESSAGE_X  
OSD1_MESSAGE_Y: MESSAGE_Y  
OSD1_GSPEED_EN: GSPEED_EN  
OSD1_GSPEED_X: GSPEED_X  
OSD1_GSPEED_Y: GSPEED_Y  
OSD1_HORIZON_EN: HORIZON_EN  
OSD1_HORIZON_X: HORIZON_X  
OSD1_HORIZON_Y: HORIZON_Y  
OSD1_HOME_EN: HOME_EN  
OSD1_HOME_X: HOME_X  
OSD1_HOME_Y: HOME_Y  
OSD1_HEADING_EN: HEADING_EN  
OSD1_HEADING_X: HEADING_X  
OSD1_HEADING_Y: HEADING_Y  
OSD1_THROTTLE_EN: THROTTLE_EN  
OSD1_THROTTLE_X: THROTTLE_X  
OSD1_THROTTLE_Y: THROTTLE_Y  
OSD1_COMPASS_EN: COMPASS_EN  
OSD1_COMPASS_X: COMPASS_X  
OSD1_COMPASS_Y: COMPASS_Y  
OSD1_WIND_EN: WIND_EN  
OSD1_WIND_X: WIND_X  
OSD1_WIND_Y: WIND_Y  
OSD1_ASPEED_EN: ASPEED_EN  
OSD1_ASPEED_X: ASPEED_X  
OSD1_ASPEED_Y: ASPEED_Y  
OSD1_VSPEED_EN: VSPEED_EN  
OSD1_VSPEED_X: VSPEED_X  
OSD1_VSPEED_Y: VSPEED_Y  
OSD1_BLHTEMP_EN: BLHTEMP_EN  
OSD1_BLHTEMP_X: BLHTEMP_X  
OSD1_BLHTEMP_Y: BLHTEMP_Y  
OSD1_BLHRPM_EN: BLHRPM_EN  
OSD1_BLHRPM_X: BLHRPM_X  
OSD1_BLHRPM_Y: BLHRPM_Y  
OSD1_BLHAMPS_EN: BLHAMPS_EN  
OSD1_BLHAMPS_X: BLHAMPS_X  
OSD1_BLHAMPS_Y: BLHAMPS_Y  
OSD1_GPSLAT_EN: GPSLAT_EN  
OSD1_GPSLAT_X: GPSLAT_X  
OSD1_GPSLAT_Y: GPSLAT_Y  
OSD1_GPSLONG_EN: GPSLONG_EN  
OSD1_GPSLONG_X: GPSLONG_X  
OSD1_GPSLONG_Y: GPSLONG_Y  
OSD1_ROLL_EN: ROLL_EN  
OSD1_ROLL_X: ROLL_X  
OSD1_ROLL_Y: ROLL_Y  
OSD1_PITCH_EN: PITCH_EN  
OSD1_PITCH_X: PITCH_X  
OSD1_PITCH_Y: PITCH_Y  
OSD1_TEMP_EN: TEMP_EN  
OSD1_TEMP_X: TEMP_X  
OSD1_TEMP_Y: TEMP_Y  
OSD1_HDOP_EN: HDOP_EN  
OSD1_HDOP_X: HDOP_X  
OSD1_HDOP_Y: HDOP_Y  
OSD1_WAYPOINT_EN: WAYPOINT_EN  
OSD1_WAYPOINT_X: WAYPOINT_X  
OSD1_WAYPOINT_Y: WAYPOINT_Y  
OSD1_XTRACK_EN: XTRACK_EN  
OSD1_XTRACK_X: XTRACK_X  
OSD1_XTRACK_Y: XTRACK_Y  
OSD1_DIST_EN: DIST_EN  
OSD1_DIST_X: DIST_X  
OSD1_DIST_Y: DIST_Y  
OSD1_STATS_EN: STATS_EN  
OSD1_STATS_X: STATS_X  
OSD1_STATS_Y: STATS_Y  
OSD1_FLTIME_EN: FLTIME_EN  
OSD1_FLTIME_X: FLTIME_X  
OSD1_FLTIME_Y: FLTIME_Y  
OSD1_CLIMBEFF_EN: CLIMBEFF_EN  
OSD1_CLIMBEFF_X: CLIMBEFF_X  
OSD1_CLIMBEFF_Y: CLIMBEFF_Y  
OSD1_EFF_EN: EFF_EN  
OSD1_EFF_X: EFF_X  
OSD1_EFF_Y: EFF_Y  
OSD1_BTEMP_EN: BTEMP_EN  
OSD1_BTEMP_X: BTEMP_X  
OSD1_BTEMP_Y: BTEMP_Y  
OSD1_ATEMP_EN: ATEMP_EN  
OSD1_ATEMP_X: ATEMP_X  
OSD1_ATEMP_Y: ATEMP_Y  
OSD1_BAT2VLT_EN: BAT2VLT_EN  
OSD1_BAT2VLT_X: BAT2VLT_X  
OSD1_BAT2VLT_Y: BAT2VLT_Y  
OSD1_BAT2USED_EN: BAT2USED_EN  
OSD1_BAT2USED_X: BAT2USED_X  
OSD1_BAT2USED_Y: BAT2USED_Y  
OSD1_ASPD2_EN: ASPD2_EN  
OSD1_ASPD2_X: ASPD2_X  
OSD1_ASPD2_Y: ASPD2_Y  
OSD1_ASPD1_Y: ASPD1_Y  


# OSD2_ Parameters

OSD2_ENABLE: Enable screen  
OSD2_CHAN_MIN: Transmitter switch screen minimum pwm  
OSD2_CHAN_MAX: Transmitter switch screen maximum pwm  
OSD2_ALTITUDE_EN: ALTITUDE_EN  
OSD2_ALTITUDE_X: ALTITUDE_X  
OSD2_ALTITUDE_Y: ALTITUDE_Y  
OSD2_BATVOLT_EN: BATVOLT_EN  
OSD2_BATVOLT_X: BATVOLT_X  
OSD2_BATVOLT_Y: BATVOLT_Y  
OSD2_RSSI_EN: RSSI_EN  
OSD2_RSSI_X: RSSI_X  
OSD2_RSSI_Y: RSSI_Y  
OSD2_CURRENT_EN: CURRENT_EN  
OSD2_CURRENT_X: CURRENT_X  
OSD2_CURRENT_Y: CURRENT_Y  
OSD2_BATUSED_EN: BATUSED_EN  
OSD2_BATUSED_X: BATUSED_X  
OSD2_BATUSED_Y: BATUSED_Y  
OSD2_SATS_EN: SATS_EN  
OSD2_SATS_X: SATS_X  
OSD2_SATS_Y: SATS_Y  
OSD2_FLTMODE_EN: FLTMODE_EN  
OSD2_FLTMODE_X: FLTMODE_X  
OSD2_FLTMODE_Y: FLTMODE_Y  
OSD2_MESSAGE_EN: MESSAGE_EN  
OSD2_MESSAGE_X: MESSAGE_X  
OSD2_MESSAGE_Y: MESSAGE_Y  
OSD2_GSPEED_EN: GSPEED_EN  
OSD2_GSPEED_X: GSPEED_X  
OSD2_GSPEED_Y: GSPEED_Y  
OSD2_HORIZON_EN: HORIZON_EN  
OSD2_HORIZON_X: HORIZON_X  
OSD2_HORIZON_Y: HORIZON_Y  
OSD2_HOME_EN: HOME_EN  
OSD2_HOME_X: HOME_X  
OSD2_HOME_Y: HOME_Y  
OSD2_HEADING_EN: HEADING_EN  
OSD2_HEADING_X: HEADING_X  
OSD2_HEADING_Y: HEADING_Y  
OSD2_THROTTLE_EN: THROTTLE_EN  
OSD2_THROTTLE_X: THROTTLE_X  
OSD2_THROTTLE_Y: THROTTLE_Y  
OSD2_COMPASS_EN: COMPASS_EN  
OSD2_COMPASS_X: COMPASS_X  
OSD2_COMPASS_Y: COMPASS_Y  
OSD2_WIND_EN: WIND_EN  
OSD2_WIND_X: WIND_X  
OSD2_WIND_Y: WIND_Y  
OSD2_ASPEED_EN: ASPEED_EN  
OSD2_ASPEED_X: ASPEED_X  
OSD2_ASPEED_Y: ASPEED_Y  
OSD2_VSPEED_EN: VSPEED_EN  
OSD2_VSPEED_X: VSPEED_X  
OSD2_VSPEED_Y: VSPEED_Y  
OSD2_BLHTEMP_EN: BLHTEMP_EN  
OSD2_BLHTEMP_X: BLHTEMP_X  
OSD2_BLHTEMP_Y: BLHTEMP_Y  
OSD2_BLHRPM_EN: BLHRPM_EN  
OSD2_BLHRPM_X: BLHRPM_X  
OSD2_BLHRPM_Y: BLHRPM_Y  
OSD2_BLHAMPS_EN: BLHAMPS_EN  
OSD2_BLHAMPS_X: BLHAMPS_X  
OSD2_BLHAMPS_Y: BLHAMPS_Y  
OSD2_GPSLAT_EN: GPSLAT_EN  
OSD2_GPSLAT_X: GPSLAT_X  
OSD2_GPSLAT_Y: GPSLAT_Y  
OSD2_GPSLONG_EN: GPSLONG_EN  
OSD2_GPSLONG_X: GPSLONG_X  
OSD2_GPSLONG_Y: GPSLONG_Y  
OSD2_ROLL_EN: ROLL_EN  
OSD2_ROLL_X: ROLL_X  
OSD2_ROLL_Y: ROLL_Y  
OSD2_PITCH_EN: PITCH_EN  
OSD2_PITCH_X: PITCH_X  
OSD2_PITCH_Y: PITCH_Y  
OSD2_TEMP_EN: TEMP_EN  
OSD2_TEMP_X: TEMP_X  
OSD2_TEMP_Y: TEMP_Y  
OSD2_HDOP_EN: HDOP_EN  
OSD2_HDOP_X: HDOP_X  
OSD2_HDOP_Y: HDOP_Y  
OSD2_WAYPOINT_EN: WAYPOINT_EN  
OSD2_WAYPOINT_X: WAYPOINT_X  
OSD2_WAYPOINT_Y: WAYPOINT_Y  
OSD2_XTRACK_EN: XTRACK_EN  
OSD2_XTRACK_X: XTRACK_X  
OSD2_XTRACK_Y: XTRACK_Y  
OSD2_DIST_EN: DIST_EN  
OSD2_DIST_X: DIST_X  
OSD2_DIST_Y: DIST_Y  
OSD2_STATS_EN: STATS_EN  
OSD2_STATS_X: STATS_X  
OSD2_STATS_Y: STATS_Y  
OSD2_FLTIME_EN: FLTIME_EN  
OSD2_FLTIME_X: FLTIME_X  
OSD2_FLTIME_Y: FLTIME_Y  
OSD2_CLIMBEFF_EN: CLIMBEFF_EN  
OSD2_CLIMBEFF_X: CLIMBEFF_X  
OSD2_CLIMBEFF_Y: CLIMBEFF_Y  
OSD2_EFF_EN: EFF_EN  
OSD2_EFF_X: EFF_X  
OSD2_EFF_Y: EFF_Y  
OSD2_BTEMP_EN: BTEMP_EN  
OSD2_BTEMP_X: BTEMP_X  
OSD2_BTEMP_Y: BTEMP_Y  
OSD2_ATEMP_EN: ATEMP_EN  
OSD2_ATEMP_X: ATEMP_X  
OSD2_ATEMP_Y: ATEMP_Y  
OSD2_BAT2VLT_EN: BAT2VLT_EN  
OSD2_BAT2VLT_X: BAT2VLT_X  
OSD2_BAT2VLT_Y: BAT2VLT_Y  
OSD2_BAT2USED_EN: BAT2USED_EN  
OSD2_BAT2USED_X: BAT2USED_X  
OSD2_BAT2USED_Y: BAT2USED_Y  
OSD2_ASPD2_EN: ASPD2_EN  
OSD2_ASPD2_X: ASPD2_X  
OSD2_ASPD2_Y: ASPD2_Y  
OSD2_ASPD1_Y: ASPD1_Y  


# OSD3_ Parameters

OSD3_ENABLE: Enable screen  
OSD3_CHAN_MIN: Transmitter switch screen minimum pwm  
OSD3_CHAN_MAX: Transmitter switch screen maximum pwm  
OSD3_ALTITUDE_EN: ALTITUDE_EN  
OSD3_ALTITUDE_X: ALTITUDE_X  
OSD3_ALTITUDE_Y: ALTITUDE_Y  
OSD3_BATVOLT_EN: BATVOLT_EN  
OSD3_BATVOLT_X: BATVOLT_X  
OSD3_BATVOLT_Y: BATVOLT_Y  
OSD3_RSSI_EN: RSSI_EN  
OSD3_RSSI_X: RSSI_X  
OSD3_RSSI_Y: RSSI_Y  
OSD3_CURRENT_EN: CURRENT_EN  
OSD3_CURRENT_X: CURRENT_X  
OSD3_CURRENT_Y: CURRENT_Y  
OSD3_BATUSED_EN: BATUSED_EN  
OSD3_BATUSED_X: BATUSED_X  
OSD3_BATUSED_Y: BATUSED_Y  
OSD3_SATS_EN: SATS_EN  
OSD3_SATS_X: SATS_X  
OSD3_SATS_Y: SATS_Y  
OSD3_FLTMODE_EN: FLTMODE_EN  
OSD3_FLTMODE_X: FLTMODE_X  
OSD3_FLTMODE_Y: FLTMODE_Y  
OSD3_MESSAGE_EN: MESSAGE_EN  
OSD3_MESSAGE_X: MESSAGE_X  
OSD3_MESSAGE_Y: MESSAGE_Y  
OSD3_GSPEED_EN: GSPEED_EN  
OSD3_GSPEED_X: GSPEED_X  
OSD3_GSPEED_Y: GSPEED_Y  
OSD3_HORIZON_EN: HORIZON_EN  
OSD3_HORIZON_X: HORIZON_X  
OSD3_HORIZON_Y: HORIZON_Y  
OSD3_HOME_EN: HOME_EN  
OSD3_HOME_X: HOME_X  
OSD3_HOME_Y: HOME_Y  
OSD3_HEADING_EN: HEADING_EN  
OSD3_HEADING_X: HEADING_X  
OSD3_HEADING_Y: HEADING_Y  
OSD3_THROTTLE_EN: THROTTLE_EN  
OSD3_THROTTLE_X: THROTTLE_X  
OSD3_THROTTLE_Y: THROTTLE_Y  
OSD3_COMPASS_EN: COMPASS_EN  
OSD3_COMPASS_X: COMPASS_X  
OSD3_COMPASS_Y: COMPASS_Y  
OSD3_WIND_EN: WIND_EN  
OSD3_WIND_X: WIND_X  
OSD3_WIND_Y: WIND_Y  
OSD3_ASPEED_EN: ASPEED_EN  
OSD3_ASPEED_X: ASPEED_X  
OSD3_ASPEED_Y: ASPEED_Y  
OSD3_VSPEED_EN: VSPEED_EN  
OSD3_VSPEED_X: VSPEED_X  
OSD3_VSPEED_Y: VSPEED_Y  
OSD3_BLHTEMP_EN: BLHTEMP_EN  
OSD3_BLHTEMP_X: BLHTEMP_X  
OSD3_BLHTEMP_Y: BLHTEMP_Y  
OSD3_BLHRPM_EN: BLHRPM_EN  
OSD3_BLHRPM_X: BLHRPM_X  
OSD3_BLHRPM_Y: BLHRPM_Y  
OSD3_BLHAMPS_EN: BLHAMPS_EN  
OSD3_BLHAMPS_X: BLHAMPS_X  
OSD3_BLHAMPS_Y: BLHAMPS_Y  
OSD3_GPSLAT_EN: GPSLAT_EN  
OSD3_GPSLAT_X: GPSLAT_X  
OSD3_GPSLAT_Y: GPSLAT_Y  
OSD3_GPSLONG_EN: GPSLONG_EN  
OSD3_GPSLONG_X: GPSLONG_X  
OSD3_GPSLONG_Y: GPSLONG_Y  
OSD3_ROLL_EN: ROLL_EN  
OSD3_ROLL_X: ROLL_X  
OSD3_ROLL_Y: ROLL_Y  
OSD3_PITCH_EN: PITCH_EN  
OSD3_PITCH_X: PITCH_X  
OSD3_PITCH_Y: PITCH_Y  
OSD3_TEMP_EN: TEMP_EN  
OSD3_TEMP_X: TEMP_X  
OSD3_TEMP_Y: TEMP_Y  
OSD3_HDOP_EN: HDOP_EN  
OSD3_HDOP_X: HDOP_X  
OSD3_HDOP_Y: HDOP_Y  
OSD3_WAYPOINT_EN: WAYPOINT_EN  
OSD3_WAYPOINT_X: WAYPOINT_X  
OSD3_WAYPOINT_Y: WAYPOINT_Y  
OSD3_XTRACK_EN: XTRACK_EN  
OSD3_XTRACK_X: XTRACK_X  
OSD3_XTRACK_Y: XTRACK_Y  
OSD3_DIST_EN: DIST_EN  
OSD3_DIST_X: DIST_X  
OSD3_DIST_Y: DIST_Y  
OSD3_STATS_EN: STATS_EN  
OSD3_STATS_X: STATS_X  
OSD3_STATS_Y: STATS_Y  
OSD3_FLTIME_EN: FLTIME_EN  
OSD3_FLTIME_X: FLTIME_X  
OSD3_FLTIME_Y: FLTIME_Y  
OSD3_CLIMBEFF_EN: CLIMBEFF_EN  
OSD3_CLIMBEFF_X: CLIMBEFF_X  
OSD3_CLIMBEFF_Y: CLIMBEFF_Y  
OSD3_EFF_EN: EFF_EN  
OSD3_EFF_X: EFF_X  
OSD3_EFF_Y: EFF_Y  
OSD3_BTEMP_EN: BTEMP_EN  
OSD3_BTEMP_X: BTEMP_X  
OSD3_BTEMP_Y: BTEMP_Y  
OSD3_ATEMP_EN: ATEMP_EN  
OSD3_ATEMP_X: ATEMP_X  
OSD3_ATEMP_Y: ATEMP_Y  
OSD3_BAT2VLT_EN: BAT2VLT_EN  
OSD3_BAT2VLT_X: BAT2VLT_X  
OSD3_BAT2VLT_Y: BAT2VLT_Y  
OSD3_BAT2USED_EN: BAT2USED_EN  
OSD3_BAT2USED_X: BAT2USED_X  
OSD3_BAT2USED_Y: BAT2USED_Y  
OSD3_ASPD2_EN: ASPD2_EN  
OSD3_ASPD2_X: ASPD2_X  
OSD3_ASPD2_Y: ASPD2_Y  
OSD3_ASPD1_Y: ASPD1_Y  


# OSD4_ Parameters

OSD4_ENABLE: Enable screen  
OSD4_CHAN_MIN: Transmitter switch screen minimum pwm  
OSD4_CHAN_MAX: Transmitter switch screen maximum pwm  
OSD4_ALTITUDE_EN: ALTITUDE_EN  
OSD4_ALTITUDE_X: ALTITUDE_X  
OSD4_ALTITUDE_Y: ALTITUDE_Y  
OSD4_BATVOLT_EN: BATVOLT_EN  
OSD4_BATVOLT_X: BATVOLT_X  
OSD4_BATVOLT_Y: BATVOLT_Y  
OSD4_RSSI_EN: RSSI_EN  
OSD4_RSSI_X: RSSI_X  
OSD4_RSSI_Y: RSSI_Y  
OSD4_CURRENT_EN: CURRENT_EN  
OSD4_CURRENT_X: CURRENT_X  
OSD4_CURRENT_Y: CURRENT_Y  
OSD4_BATUSED_EN: BATUSED_EN  
OSD4_BATUSED_X: BATUSED_X  
OSD4_BATUSED_Y: BATUSED_Y  
OSD4_SATS_EN: SATS_EN  
OSD4_SATS_X: SATS_X  
OSD4_SATS_Y: SATS_Y  
OSD4_FLTMODE_EN: FLTMODE_EN  
OSD4_FLTMODE_X: FLTMODE_X  
OSD4_FLTMODE_Y: FLTMODE_Y  
OSD4_MESSAGE_EN: MESSAGE_EN  
OSD4_MESSAGE_X: MESSAGE_X  
OSD4_MESSAGE_Y: MESSAGE_Y  
OSD4_GSPEED_EN: GSPEED_EN  
OSD4_GSPEED_X: GSPEED_X  
OSD4_GSPEED_Y: GSPEED_Y  
OSD4_HORIZON_EN: HORIZON_EN  
OSD4_HORIZON_X: HORIZON_X  
OSD4_HORIZON_Y: HORIZON_Y  
OSD4_HOME_EN: HOME_EN  
OSD4_HOME_X: HOME_X  
OSD4_HOME_Y: HOME_Y  
OSD4_HEADING_EN: HEADING_EN  
OSD4_HEADING_X: HEADING_X  
OSD4_HEADING_Y: HEADING_Y  
OSD4_THROTTLE_EN: THROTTLE_EN  
OSD4_THROTTLE_X: THROTTLE_X  
OSD4_THROTTLE_Y: THROTTLE_Y  
OSD4_COMPASS_EN: COMPASS_EN  
OSD4_COMPASS_X: COMPASS_X  
OSD4_COMPASS_Y: COMPASS_Y  
OSD4_WIND_EN: WIND_EN  
OSD4_WIND_X: WIND_X  
OSD4_WIND_Y: WIND_Y  
OSD4_ASPEED_EN: ASPEED_EN  
OSD4_ASPEED_X: ASPEED_X  
OSD4_ASPEED_Y: ASPEED_Y  
OSD4_VSPEED_EN: VSPEED_EN  
OSD4_VSPEED_X: VSPEED_X  
OSD4_VSPEED_Y: VSPEED_Y  
OSD4_BLHTEMP_EN: BLHTEMP_EN  
OSD4_BLHTEMP_X: BLHTEMP_X  
OSD4_BLHTEMP_Y: BLHTEMP_Y  
OSD4_BLHRPM_EN: BLHRPM_EN  
OSD4_BLHRPM_X: BLHRPM_X  
OSD4_BLHRPM_Y: BLHRPM_Y  
OSD4_BLHAMPS_EN: BLHAMPS_EN  
OSD4_BLHAMPS_X: BLHAMPS_X  
OSD4_BLHAMPS_Y: BLHAMPS_Y  
OSD4_GPSLAT_EN: GPSLAT_EN  
OSD4_GPSLAT_X: GPSLAT_X  
OSD4_GPSLAT_Y: GPSLAT_Y  
OSD4_GPSLONG_EN: GPSLONG_EN  
OSD4_GPSLONG_X: GPSLONG_X  
OSD4_GPSLONG_Y: GPSLONG_Y  
OSD4_ROLL_EN: ROLL_EN  
OSD4_ROLL_X: ROLL_X  
OSD4_ROLL_Y: ROLL_Y  
OSD4_PITCH_EN: PITCH_EN  
OSD4_PITCH_X: PITCH_X  
OSD4_PITCH_Y: PITCH_Y  
OSD4_TEMP_EN: TEMP_EN  
OSD4_TEMP_X: TEMP_X  
OSD4_TEMP_Y: TEMP_Y  
OSD4_HDOP_EN: HDOP_EN  
OSD4_HDOP_X: HDOP_X  
OSD4_HDOP_Y: HDOP_Y  
OSD4_WAYPOINT_EN: WAYPOINT_EN  
OSD4_WAYPOINT_X: WAYPOINT_X  
OSD4_WAYPOINT_Y: WAYPOINT_Y  
OSD4_XTRACK_EN: XTRACK_EN  
OSD4_XTRACK_X: XTRACK_X  
OSD4_XTRACK_Y: XTRACK_Y  
OSD4_DIST_EN: DIST_EN  
OSD4_DIST_X: DIST_X  
OSD4_DIST_Y: DIST_Y  
OSD4_STATS_EN: STATS_EN  
OSD4_STATS_X: STATS_X  
OSD4_STATS_Y: STATS_Y  
OSD4_FLTIME_EN: FLTIME_EN  
OSD4_FLTIME_X: FLTIME_X  
OSD4_FLTIME_Y: FLTIME_Y  
OSD4_CLIMBEFF_EN: CLIMBEFF_EN  
OSD4_CLIMBEFF_X: CLIMBEFF_X  
OSD4_CLIMBEFF_Y: CLIMBEFF_Y  
OSD4_EFF_EN: EFF_EN  
OSD4_EFF_X: EFF_X  
OSD4_EFF_Y: EFF_Y  
OSD4_BTEMP_EN: BTEMP_EN  
OSD4_BTEMP_X: BTEMP_X  
OSD4_BTEMP_Y: BTEMP_Y  
OSD4_ATEMP_EN: ATEMP_EN  
OSD4_ATEMP_X: ATEMP_X  
OSD4_ATEMP_Y: ATEMP_Y  
OSD4_BAT2VLT_EN: BAT2VLT_EN  
OSD4_BAT2VLT_X: BAT2VLT_X  
OSD4_BAT2VLT_Y: BAT2VLT_Y  
OSD4_BAT2USED_EN: BAT2USED_EN  
OSD4_BAT2USED_X: BAT2USED_X  
OSD4_BAT2USED_Y: BAT2USED_Y  
OSD4_ASPD2_EN: ASPD2_EN  
OSD4_ASPD2_X: ASPD2_X  
OSD4_ASPD2_Y: ASPD2_Y  
OSD4_ASPD1_Y: ASPD1_Y  


# PTCH2SRV_ Parameters

PTCH2SRV_TCONST: Pitch Time Constant  
PTCH2SRV_P: Proportional Gain  
PTCH2SRV_D: Damping Gain  
PTCH2SRV_I: Integrator Gain  
PTCH2SRV_RMAX_UP: Pitch up max rate  
PTCH2SRV_RMAX_DN: Pitch down max rate  
PTCH2SRV_RLL: Roll compensation  
PTCH2SRV_IMAX: Integrator limit  
PTCH2SRV_FF: Feed forward Gain  


# Q_ Parameters

Q_ENABLE: Enable QuadPlane  
Q_ANGLE_MAX: Angle Max  
Q_TRANSITION_MS: Transition time  
Q_VELZ_MAX: Pilot maximum vertical speed  
Q_ACCEL_Z: Pilot vertical acceleration  
Q_RC_SPEED: RC output speed in Hz  
Q_THR_MIN_PWM: Minimum PWM output  
Q_THR_MAX_PWM: Maximum PWM output  
Q_ASSIST_SPEED: Quadplane assistance speed  
Q_YAW_RATE_MAX: Maximum yaw rate  
Q_LAND_SPEED: Land speed  
Q_LAND_FINAL_ALT: Land final altitude  
Q_TRAN_PIT_MAX: Transition max pitch  
Q_FRAME_CLASS: Frame Class  
Q_FRAME_TYPE: Frame Type (+, X or V)  
Q_VFWD_GAIN: Forward velocity hold gain  
Q_WVANE_GAIN: Weathervaning gain  
Q_WVANE_MINROLL: Weathervaning min roll  
Q_RTL_ALT: QRTL return altitude  
Q_RTL_MODE: VTOL RTL mode  
Q_TILT_MASK: Tiltrotor mask  
Q_TILT_RATE_UP: Tiltrotor upwards tilt rate  
Q_TILT_MAX: Tiltrotor maximum VTOL angle  
Q_GUIDED_MODE: Enable VTOL in GUIDED mode  
Q_ESC_CAL: ESC Calibration  
Q_VFWD_ALT: Forward velocity alt cutoff  
Q_LAND_ICE_CUT: Cut IC engine on landing  
Q_ASSIST_ANGLE: Quadplane assistance angle  
Q_TILT_TYPE: Tiltrotor type  
Q_TAILSIT_ANGLE: Tailsitter transition angle  
Q_TILT_RATE_DN: Tiltrotor downwards tilt rate  
Q_TAILSIT_INPUT: Tailsitter input type  
Q_TAILSIT_MASK: Tailsitter input mask  
Q_TAILSIT_MASKCH: Tailsitter input mask channel  
Q_TAILSIT_VFGAIN: Tailsitter vector thrust gain in forward flight  
Q_TAILSIT_VHGAIN: Tailsitter vector thrust gain in hover  
Q_TILT_YAW_ANGLE: Tilt minimum angle for vectored yaw  
Q_TAILSIT_VHPOW: Tailsitter vector thrust gain power  
Q_MAV_TYPE: MAVLink type identifier  
Q_OPTIONS: quadplane options  
Q_TRANS_DECEL: Transition deceleration  
Q_TAILSIT_THSCMX: Maximum control throttle scaling value  
Q_TRIM_PITCH: Quadplane AHRS trim pitch  
Q_TAILSIT_RLL_MX: Maximum Roll angle  
Q_FW_LND_APR_RAD: Quadplane fixed wing landing approach radius  
Q_TRANS_FAIL: Quadplane transition failure time  
Q_TAILSIT_MOTMX: Tailsiter mask  
Q_THROTTLE_EXPO: Throttle expo strength  
Q_ACRO_RLL_RATE: QACRO mode roll rate  
Q_ACRO_PIT_RATE: QACRO mode pitch rate  
Q_ACRO_YAW_RATE: QACRO mode yaw rate  


# Q_A_ Parameters

Q_A_SLEW_YAW: Yaw target slew rate  
Q_A_ACCEL_Y_MAX: Acceleration Max for Yaw  
Q_A_RATE_FF_ENAB: Rate Feedforward Enable  
Q_A_ACCEL_R_MAX: Acceleration Max for Roll  
Q_A_ACCEL_P_MAX: Acceleration Max for Pitch  
Q_A_ANGLE_BOOST: Angle Boost  
Q_A_ANG_RLL_P: Roll axis angle controller P gain  
Q_A_ANG_PIT_P: Pitch axis angle controller P gain  
Q_A_ANG_YAW_P: Yaw axis angle controller P gain  
Q_A_ANG_LIM_TC: Angle Limit (to maintain altitude) Time Constant  
Q_A_RATE_R_MAX: Angular Velocity Max for Roll  
Q_A_RATE_P_MAX: Angular Velocity Max for Pitch  
Q_A_RATE_Y_MAX: Angular Velocity Max for Yaw  
Q_A_INPUT_TC: Attitude control input time constant  
Q_A_RAT_RLL_P: Roll axis rate controller P gain  
Q_A_RAT_RLL_I: Roll axis rate controller I gain  
Q_A_RAT_RLL_IMAX: Roll axis rate controller I gain maximum  
Q_A_RAT_RLL_D: Roll axis rate controller D gain  
Q_A_RAT_RLL_FF: Roll axis rate controller feed forward  
Q_A_RAT_RLL_FLTT: Roll axis rate controller target frequency in Hz  
Q_A_RAT_RLL_FLTE: Roll axis rate controller error frequency in Hz  
Q_A_RAT_RLL_FLTD: Roll axis rate controller derivative frequency in Hz  
Q_A_RAT_PIT_P: Pitch axis rate controller P gain  
Q_A_RAT_PIT_I: Pitch axis rate controller I gain  
Q_A_RAT_PIT_IMAX: Pitch axis rate controller I gain maximum  
Q_A_RAT_PIT_D: Pitch axis rate controller D gain  
Q_A_RAT_PIT_FF: Pitch axis rate controller feed forward  
Q_A_RAT_PIT_FLTT: Pitch axis rate controller target frequency in Hz  
Q_A_RAT_PIT_FLTE: Pitch axis rate controller error frequency in Hz  
Q_A_RAT_PIT_FLTD: Pitch axis rate controller derivative frequency in Hz  
Q_A_RAT_YAW_P: Yaw axis rate controller P gain  
Q_A_RAT_YAW_I: Yaw axis rate controller I gain  
Q_A_RAT_YAW_IMAX: Yaw axis rate controller I gain maximum  
Q_A_RAT_YAW_D: Yaw axis rate controller D gain  
Q_A_RAT_YAW_FF: Yaw axis rate controller feed forward  
Q_A_RAT_YAW_FLTT: Yaw axis rate controller target frequency in Hz  
Q_A_RAT_YAW_FLTE: Yaw axis rate controller error frequency in Hz  
Q_A_RAT_YAW_FLTD: Yaw axis rate controller derivative frequency in Hz  
Q_A_THR_MIX_MIN: Throttle Mix Minimum  
Q_A_THR_MIX_MAX: Throttle Mix Maximum  
Q_A_THR_MIX_MAN: Throttle Mix Manual  
Q_A_RAT_RLL_FILT: Roll axis rate controller input frequency in Hz  
Q_A_RAT_PIT_FILT: Pitch axis rate controller input frequency in Hz  
Q_A_RAT_YAW_FILT: Yaw axis rate controller input frequency in Hz  


# Q_LOIT_ Parameters

Q_LOIT_ANG_MAX: Loiter Angle Max  
Q_LOIT_SPEED: Loiter Horizontal Maximum Speed  
Q_LOIT_ACC_MAX: Loiter maximum correction acceleration  
Q_LOIT_BRK_ACCEL: Loiter braking acceleration  
Q_LOIT_BRK_JERK: Loiter braking jerk  
Q_LOIT_BRK_DELAY: Loiter brake start delay (in seconds)  


# Q_M_ Parameters

Q_M_YAW_HEADROOM: Matrix Yaw Min  
Q_M_THST_EXPO: Thrust Curve Expo  
Q_M_SPIN_MAX: Motor Spin maximum  
Q_M_BAT_VOLT_MAX: Battery voltage compensation maximum voltage  
Q_M_BAT_VOLT_MIN: Battery voltage compensation minimum voltage  
Q_M_BAT_CURR_MAX: Motor Current Max  
Q_M_PWM_TYPE: Output PWM type  
Q_M_PWM_MIN: PWM output miniumum  
Q_M_PWM_MAX: PWM output maximum  
Q_M_SPIN_MIN: Motor Spin minimum  
Q_M_SPIN_ARM: Motor Spin armed  
Q_M_BAT_CURR_TC: Motor Current Max Time Constant  
Q_M_THST_HOVER: Thrust Hover Value  
Q_M_HOVER_LEARN: Hover Value Learning  
Q_M_SAFE_DISARM: Motor PWM output disabled when disarmed  
Q_M_YAW_SV_ANGLE: Yaw Servo Max Lean Angle  
Q_M_SPOOL_TIME: Spool up time  
Q_M_BOOST_SCALE: Motor boost scale  
Q_M_BAT_IDX: Battery compensation index  
Q_M_SLEW_UP_TIME: Output slew time for increasing throttle  
Q_M_SLEW_DN_TIME: Output slew time for decreasing throttle  


# Q_P Parameters

Q_P_ACC_XY_FILT: XY Acceleration filter cutoff frequency  
Q_P_POSZ_P: Position (vertical) controller P gain  
Q_P_VELZ_P: Velocity (vertical) controller P gain  
Q_P_ACCZ_P: Acceleration (vertical) controller P gain  
Q_P_ACCZ_I: Acceleration (vertical) controller I gain  
Q_P_ACCZ_IMAX: Acceleration (vertical) controller I gain maximum  
Q_P_ACCZ_D: Acceleration (vertical) controller D gain  
Q_P_ACCZ_FILT: Acceleration (vertical) controller filter  
Q_P_POSXY_P: Position (horizonal) controller P gain  
Q_P_VELXY_P: Velocity (horizontal) P gain  
Q_P_VELXY_I: Velocity (horizontal) I gain  
Q_P_VELXY_D: Velocity (horizontal) D gain  
Q_P_VELXY_IMAX: Velocity (horizontal) integrator maximum  
Q_P_VELXY_FILT: Velocity (horizontal) input filter  
Q_P_VELXY_D_FILT: Velocity (horizontal) input filter  
Q_P_ANGLE_MAX: Position Control Angle Max  


# Q_WP_ Parameters

Q_WP_SPEED: Waypoint Horizontal Speed Target  
Q_WP_RADIUS: Waypoint Radius  
Q_WP_SPEED_UP: Waypoint Climb Speed Target  
Q_WP_SPEED_DN: Waypoint Descent Speed Target  
Q_WP_ACCEL: Waypoint Acceleration  
Q_WP_ACCEL_Z: Waypoint Vertical Acceleration  
Q_WP_RFND_USE: Waypoint missions use rangefinder for terrain following  


# RALLY_ Parameters

RALLY_TOTAL: Rally Total  
RALLY_LIMIT_KM: Rally Limit  
RALLY_INCL_HOME: Rally Include Home  


# RC Parameters

RC_OVERRIDE_TIME: RC override timeout  
RC_OPTIONS: RC options  


# RC10_ Parameters

RC10_MIN: RC min PWM  
RC10_TRIM: RC trim PWM  
RC10_MAX: RC max PWM  
RC10_REVERSED: RC reversed  
RC10_DZ: RC dead-zone  
RC10_OPTION: RC input option  


# RC11_ Parameters

RC11_MIN: RC min PWM  
RC11_TRIM: RC trim PWM  
RC11_MAX: RC max PWM  
RC11_REVERSED: RC reversed  
RC11_DZ: RC dead-zone  
RC11_OPTION: RC input option  


# RC12_ Parameters

RC12_MIN: RC min PWM  
RC12_TRIM: RC trim PWM  
RC12_MAX: RC max PWM  
RC12_REVERSED: RC reversed  
RC12_DZ: RC dead-zone  
RC12_OPTION: RC input option  


# RC13_ Parameters

RC13_MIN: RC min PWM  
RC13_TRIM: RC trim PWM  
RC13_MAX: RC max PWM  
RC13_REVERSED: RC reversed  
RC13_DZ: RC dead-zone  
RC13_OPTION: RC input option  


# RC14_ Parameters

RC14_MIN: RC min PWM  
RC14_TRIM: RC trim PWM  
RC14_MAX: RC max PWM  
RC14_REVERSED: RC reversed  
RC14_DZ: RC dead-zone  
RC14_OPTION: RC input option  


# RC15_ Parameters

RC15_MIN: RC min PWM  
RC15_TRIM: RC trim PWM  
RC15_MAX: RC max PWM  
RC15_REVERSED: RC reversed  
RC15_DZ: RC dead-zone  
RC15_OPTION: RC input option  


# RC16_ Parameters

RC16_MIN: RC min PWM  
RC16_TRIM: RC trim PWM  
RC16_MAX: RC max PWM  
RC16_REVERSED: RC reversed  
RC16_DZ: RC dead-zone  
RC16_OPTION: RC input option  


# RC1_ Parameters

RC1_MIN: RC min PWM  
RC1_TRIM: RC trim PWM  
RC1_MAX: RC max PWM  
RC1_REVERSED: RC reversed  
RC1_DZ: RC dead-zone  
RC1_OPTION: RC input option  


# RC2_ Parameters

RC2_MIN: RC min PWM  
RC2_TRIM: RC trim PWM  
RC2_MAX: RC max PWM  
RC2_REVERSED: RC reversed  
RC2_DZ: RC dead-zone  
RC2_OPTION: RC input option  


# RC3_ Parameters

RC3_MIN: RC min PWM  
RC3_TRIM: RC trim PWM  
RC3_MAX: RC max PWM  
RC3_REVERSED: RC reversed  
RC3_DZ: RC dead-zone  
RC3_OPTION: RC input option  


# RC4_ Parameters

RC4_MIN: RC min PWM  
RC4_TRIM: RC trim PWM  
RC4_MAX: RC max PWM  
RC4_REVERSED: RC reversed  
RC4_DZ: RC dead-zone  
RC4_OPTION: RC input option  


# RC5_ Parameters

RC5_MIN: RC min PWM  
RC5_TRIM: RC trim PWM  
RC5_MAX: RC max PWM  
RC5_REVERSED: RC reversed  
RC5_DZ: RC dead-zone  
RC5_OPTION: RC input option  


# RC6_ Parameters

RC6_MIN: RC min PWM  
RC6_TRIM: RC trim PWM  
RC6_MAX: RC max PWM  
RC6_REVERSED: RC reversed  
RC6_DZ: RC dead-zone  
RC6_OPTION: RC input option  


# RC7_ Parameters

RC7_MIN: RC min PWM  
RC7_TRIM: RC trim PWM  
RC7_MAX: RC max PWM  
RC7_REVERSED: RC reversed  
RC7_DZ: RC dead-zone  
RC7_OPTION: RC input option  


# RC8_ Parameters

RC8_MIN: RC min PWM  
RC8_TRIM: RC trim PWM  
RC8_MAX: RC max PWM  
RC8_REVERSED: RC reversed  
RC8_DZ: RC dead-zone  
RC8_OPTION: RC input option  


# RC9_ Parameters

RC9_MIN: RC min PWM  
RC9_TRIM: RC trim PWM  
RC9_MAX: RC max PWM  
RC9_REVERSED: RC reversed  
RC9_DZ: RC dead-zone  
RC9_OPTION: RC input option  


# RCMAP_ Parameters

RCMAP_ROLL: Roll channel  
RCMAP_PITCH: Pitch channel  
RCMAP_THROTTLE: Throttle channel  
RCMAP_YAW: Yaw channel  
RCMAP_FORWARD: Forward channel  
RCMAP_LATERAL: Lateral channel  


# RELAY_ Parameters

RELAY_PIN: First Relay Pin  
RELAY_PIN2: Second Relay Pin  
RELAY_PIN3: Third Relay Pin  
RELAY_PIN4: Fourth Relay Pin  
RELAY_DEFAULT: Default relay state  
RELAY_PIN5: Fifth Relay Pin  
RELAY_PIN6: Sixth Relay Pin  


# RLL2SRV_ Parameters

RLL2SRV_TCONST: Roll Time Constant  
RLL2SRV_P: Proportional Gain  
RLL2SRV_D: Damping Gain  
RLL2SRV_I: Integrator Gain  
RLL2SRV_RMAX: Maximum Roll Rate  
RLL2SRV_IMAX: Integrator limit  
RLL2SRV_FF: Feed forward Gain  


# RNGFND1_ Parameters

RNGFND1_TYPE: Rangefinder type  
RNGFND1_PIN: Rangefinder pin  
RNGFND1_SCALING: Rangefinder scaling  
RNGFND1_OFFSET: rangefinder offset  
RNGFND1_FUNCTION: Rangefinder function  
RNGFND1_MIN_CM: Rangefinder minimum distance  
RNGFND1_MAX_CM: Rangefinder maximum distance  
RNGFND1_STOP_PIN: Rangefinder stop pin  
RNGFND1_SETTLE: Rangefinder settle time  
RNGFND1_RMETRIC: Ratiometric  
RNGFND1_PWRRNG: Powersave range  
RNGFND1_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND1_ADDR: Bus address of sensor  
RNGFND1_POS_X:  X position offset  
RNGFND1_POS_Y: Y position offset  
RNGFND1_POS_Z: Z position offset  
RNGFND1_ORIENT: Rangefinder orientation  


# RNGFND1_ Parameters

RNGFND1_WSP_MAVG: Moving Average Range  
RNGFND1_WSP_MEDF: Moving Median Filter  
RNGFND1_WSP_FRQ: Frequency  
RNGFND1_WSP_AVG: Multi-pulse averages  
RNGFND1_WSP_THR: Sensitivity threshold  
RNGFND1_WSP_BAUD: Baud rate  


# RNGFND2_ Parameters

RNGFND2_TYPE: Rangefinder type  
RNGFND2_PIN: Rangefinder pin  
RNGFND2_SCALING: Rangefinder scaling  
RNGFND2_OFFSET: rangefinder offset  
RNGFND2_FUNCTION: Rangefinder function  
RNGFND2_MIN_CM: Rangefinder minimum distance  
RNGFND2_MAX_CM: Rangefinder maximum distance  
RNGFND2_STOP_PIN: Rangefinder stop pin  
RNGFND2_SETTLE: Rangefinder settle time  
RNGFND2_RMETRIC: Ratiometric  
RNGFND2_PWRRNG: Powersave range  
RNGFND2_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND2_ADDR: Bus address of sensor  
RNGFND2_POS_X:  X position offset  
RNGFND2_POS_Y: Y position offset  
RNGFND2_POS_Z: Z position offset  
RNGFND2_ORIENT: Rangefinder orientation  


# RNGFND2_ Parameters

RNGFND2_WSP_MAVG: Moving Average Range  
RNGFND2_WSP_MEDF: Moving Median Filter  
RNGFND2_WSP_FRQ: Frequency  
RNGFND2_WSP_AVG: Multi-pulse averages  
RNGFND2_WSP_THR: Sensitivity threshold  
RNGFND2_WSP_BAUD: Baud rate  


# RNGFND3_ Parameters

RNGFND3_TYPE: Rangefinder type  
RNGFND3_PIN: Rangefinder pin  
RNGFND3_SCALING: Rangefinder scaling  
RNGFND3_OFFSET: rangefinder offset  
RNGFND3_FUNCTION: Rangefinder function  
RNGFND3_MIN_CM: Rangefinder minimum distance  
RNGFND3_MAX_CM: Rangefinder maximum distance  
RNGFND3_STOP_PIN: Rangefinder stop pin  
RNGFND3_SETTLE: Rangefinder settle time  
RNGFND3_RMETRIC: Ratiometric  
RNGFND3_PWRRNG: Powersave range  
RNGFND3_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND3_ADDR: Bus address of sensor  
RNGFND3_POS_X:  X position offset  
RNGFND3_POS_Y: Y position offset  
RNGFND3_POS_Z: Z position offset  
RNGFND3_ORIENT: Rangefinder orientation  


# RNGFND3_ Parameters

RNGFND3_WSP_MAVG: Moving Average Range  
RNGFND3_WSP_MEDF: Moving Median Filter  
RNGFND3_WSP_FRQ: Frequency  
RNGFND3_WSP_AVG: Multi-pulse averages  
RNGFND3_WSP_THR: Sensitivity threshold  
RNGFND3_WSP_BAUD: Baud rate  


# RNGFND4_ Parameters

RNGFND4_TYPE: Rangefinder type  
RNGFND4_PIN: Rangefinder pin  
RNGFND4_SCALING: Rangefinder scaling  
RNGFND4_OFFSET: rangefinder offset  
RNGFND4_FUNCTION: Rangefinder function  
RNGFND4_MIN_CM: Rangefinder minimum distance  
RNGFND4_MAX_CM: Rangefinder maximum distance  
RNGFND4_STOP_PIN: Rangefinder stop pin  
RNGFND4_SETTLE: Rangefinder settle time  
RNGFND4_RMETRIC: Ratiometric  
RNGFND4_PWRRNG: Powersave range  
RNGFND4_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND4_ADDR: Bus address of sensor  
RNGFND4_POS_X:  X position offset  
RNGFND4_POS_Y: Y position offset  
RNGFND4_POS_Z: Z position offset  
RNGFND4_ORIENT: Rangefinder orientation  


# RNGFND4_ Parameters

RNGFND4_WSP_MAVG: Moving Average Range  
RNGFND4_WSP_MEDF: Moving Median Filter  
RNGFND4_WSP_FRQ: Frequency  
RNGFND4_WSP_AVG: Multi-pulse averages  
RNGFND4_WSP_THR: Sensitivity threshold  
RNGFND4_WSP_BAUD: Baud rate  


# RNGFND5_ Parameters

RNGFND5_TYPE: Rangefinder type  
RNGFND5_PIN: Rangefinder pin  
RNGFND5_SCALING: Rangefinder scaling  
RNGFND5_OFFSET: rangefinder offset  
RNGFND5_FUNCTION: Rangefinder function  
RNGFND5_MIN_CM: Rangefinder minimum distance  
RNGFND5_MAX_CM: Rangefinder maximum distance  
RNGFND5_STOP_PIN: Rangefinder stop pin  
RNGFND5_SETTLE: Rangefinder settle time  
RNGFND5_RMETRIC: Ratiometric  
RNGFND5_PWRRNG: Powersave range  
RNGFND5_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND5_ADDR: Bus address of sensor  
RNGFND5_POS_X:  X position offset  
RNGFND5_POS_Y: Y position offset  
RNGFND5_POS_Z: Z position offset  
RNGFND5_ORIENT: Rangefinder orientation  


# RNGFND5_ Parameters

RNGFND5_WSP_MAVG: Moving Average Range  
RNGFND5_WSP_MEDF: Moving Median Filter  
RNGFND5_WSP_FRQ: Frequency  
RNGFND5_WSP_AVG: Multi-pulse averages  
RNGFND5_WSP_THR: Sensitivity threshold  
RNGFND5_WSP_BAUD: Baud rate  


# RNGFND6_ Parameters

RNGFND6_TYPE: Rangefinder type  
RNGFND6_PIN: Rangefinder pin  
RNGFND6_SCALING: Rangefinder scaling  
RNGFND6_OFFSET: rangefinder offset  
RNGFND6_FUNCTION: Rangefinder function  
RNGFND6_MIN_CM: Rangefinder minimum distance  
RNGFND6_MAX_CM: Rangefinder maximum distance  
RNGFND6_STOP_PIN: Rangefinder stop pin  
RNGFND6_SETTLE: Rangefinder settle time  
RNGFND6_RMETRIC: Ratiometric  
RNGFND6_PWRRNG: Powersave range  
RNGFND6_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND6_ADDR: Bus address of sensor  
RNGFND6_POS_X:  X position offset  
RNGFND6_POS_Y: Y position offset  
RNGFND6_POS_Z: Z position offset  
RNGFND6_ORIENT: Rangefinder orientation  


# RNGFND6_ Parameters

RNGFND6_WSP_MAVG: Moving Average Range  
RNGFND6_WSP_MEDF: Moving Median Filter  
RNGFND6_WSP_FRQ: Frequency  
RNGFND6_WSP_AVG: Multi-pulse averages  
RNGFND6_WSP_THR: Sensitivity threshold  
RNGFND6_WSP_BAUD: Baud rate  


# RNGFND7_ Parameters

RNGFND7_TYPE: Rangefinder type  
RNGFND7_PIN: Rangefinder pin  
RNGFND7_SCALING: Rangefinder scaling  
RNGFND7_OFFSET: rangefinder offset  
RNGFND7_FUNCTION: Rangefinder function  
RNGFND7_MIN_CM: Rangefinder minimum distance  
RNGFND7_MAX_CM: Rangefinder maximum distance  
RNGFND7_STOP_PIN: Rangefinder stop pin  
RNGFND7_SETTLE: Rangefinder settle time  
RNGFND7_RMETRIC: Ratiometric  
RNGFND7_PWRRNG: Powersave range  
RNGFND7_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND7_ADDR: Bus address of sensor  
RNGFND7_POS_X:  X position offset  
RNGFND7_POS_Y: Y position offset  
RNGFND7_POS_Z: Z position offset  
RNGFND7_ORIENT: Rangefinder orientation  


# RNGFND7_ Parameters

RNGFND7_WSP_MAVG: Moving Average Range  
RNGFND7_WSP_MEDF: Moving Median Filter  
RNGFND7_WSP_FRQ: Frequency  
RNGFND7_WSP_AVG: Multi-pulse averages  
RNGFND7_WSP_THR: Sensitivity threshold  
RNGFND7_WSP_BAUD: Baud rate  


# RNGFND8_ Parameters

RNGFND8_TYPE: Rangefinder type  
RNGFND8_PIN: Rangefinder pin  
RNGFND8_SCALING: Rangefinder scaling  
RNGFND8_OFFSET: rangefinder offset  
RNGFND8_FUNCTION: Rangefinder function  
RNGFND8_MIN_CM: Rangefinder minimum distance  
RNGFND8_MAX_CM: Rangefinder maximum distance  
RNGFND8_STOP_PIN: Rangefinder stop pin  
RNGFND8_SETTLE: Rangefinder settle time  
RNGFND8_RMETRIC: Ratiometric  
RNGFND8_PWRRNG: Powersave range  
RNGFND8_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND8_ADDR: Bus address of sensor  
RNGFND8_POS_X:  X position offset  
RNGFND8_POS_Y: Y position offset  
RNGFND8_POS_Z: Z position offset  
RNGFND8_ORIENT: Rangefinder orientation  


# RNGFND8_ Parameters

RNGFND8_WSP_MAVG: Moving Average Range  
RNGFND8_WSP_MEDF: Moving Median Filter  
RNGFND8_WSP_FRQ: Frequency  
RNGFND8_WSP_AVG: Multi-pulse averages  
RNGFND8_WSP_THR: Sensitivity threshold  
RNGFND8_WSP_BAUD: Baud rate  


# RNGFND9_ Parameters

RNGFND9_TYPE: Rangefinder type  
RNGFND9_PIN: Rangefinder pin  
RNGFND9_SCALING: Rangefinder scaling  
RNGFND9_OFFSET: rangefinder offset  
RNGFND9_FUNCTION: Rangefinder function  
RNGFND9_MIN_CM: Rangefinder minimum distance  
RNGFND9_MAX_CM: Rangefinder maximum distance  
RNGFND9_STOP_PIN: Rangefinder stop pin  
RNGFND9_SETTLE: Rangefinder settle time  
RNGFND9_RMETRIC: Ratiometric  
RNGFND9_PWRRNG: Powersave range  
RNGFND9_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFND9_ADDR: Bus address of sensor  
RNGFND9_POS_X:  X position offset  
RNGFND9_POS_Y: Y position offset  
RNGFND9_POS_Z: Z position offset  
RNGFND9_ORIENT: Rangefinder orientation  


# RNGFND9_ Parameters

RNGFND9_WSP_MAVG: Moving Average Range  
RNGFND9_WSP_MEDF: Moving Median Filter  
RNGFND9_WSP_FRQ: Frequency  
RNGFND9_WSP_AVG: Multi-pulse averages  
RNGFND9_WSP_THR: Sensitivity threshold  
RNGFND9_WSP_BAUD: Baud rate  


# RNGFNDA_ Parameters

RNGFNDA_TYPE: Rangefinder type  
RNGFNDA_PIN: Rangefinder pin  
RNGFNDA_SCALING: Rangefinder scaling  
RNGFNDA_OFFSET: rangefinder offset  
RNGFNDA_FUNCTION: Rangefinder function  
RNGFNDA_MIN_CM: Rangefinder minimum distance  
RNGFNDA_MAX_CM: Rangefinder maximum distance  
RNGFNDA_STOP_PIN: Rangefinder stop pin  
RNGFNDA_SETTLE: Rangefinder settle time  
RNGFNDA_RMETRIC: Ratiometric  
RNGFNDA_PWRRNG: Powersave range  
RNGFNDA_GNDCLEAR: Distance (in cm) from the range finder to the ground  
RNGFNDA_ADDR: Bus address of sensor  
RNGFNDA_POS_X:  X position offset  
RNGFNDA_POS_Y: Y position offset  
RNGFNDA_POS_Z: Z position offset  
RNGFNDA_ORIENT: Rangefinder orientation  


# RNGFNDA_ Parameters

RNGFNDA_WSP_MAVG: Moving Average Range  
RNGFNDA_WSP_MEDF: Moving Median Filter  
RNGFNDA_WSP_FRQ: Frequency  
RNGFNDA_WSP_AVG: Multi-pulse averages  
RNGFNDA_WSP_THR: Sensitivity threshold  
RNGFNDA_WSP_BAUD: Baud rate  


# RPM Parameters

RPM_TYPE: RPM type  
RPM_SCALING: RPM scaling  
RPM_MAX: Maximum RPM  
RPM_MIN: Minimum RPM  
RPM_MIN_QUAL: Minimum Quality  
RPM_PIN: Input pin number  
RPM2_TYPE: Second RPM type  
RPM2_SCALING: RPM scaling  
RPM2_PIN: RPM2 input pin number  


# RSSI_ Parameters

RSSI_TYPE: RSSI Type  
RSSI_ANA_PIN: Receiver RSSI sensing pin  
RSSI_PIN_LOW: RSSI pin’s lowest voltage  
RSSI_PIN_HIGH: RSSI pin’s highest voltage  
RSSI_CHANNEL: Receiver RSSI channel number  
RSSI_CHAN_LOW: RSSI PWM low value  
RSSI_CHAN_HIGH: Receiver RSSI PWM high value  


# SCHED_ Parameters

SCHED_DEBUG: Scheduler debug level  
SCHED_LOOP_RATE: Scheduling main loop rate  


# SCR_ Parameters

SCR_ENABLE: Enable Scripting  
SCR_VM_I_COUNT: Scripting Virtual Machine Instruction Count  
SCR_HEAP_SIZE: Scripting Heap Size  


# SERIAL Parameters

SERIAL0_BAUD: Serial0 baud rate  
SERIAL0_PROTOCOL: Console protocol selection  
SERIAL1_PROTOCOL: Telem1 protocol selection  
SERIAL1_BAUD: Telem1 Baud Rate  
SERIAL2_PROTOCOL: Telemetry 2 protocol selection  
SERIAL2_BAUD: Telemetry 2 Baud Rate  
SERIAL3_PROTOCOL: Serial 3 (GPS) protocol selection  
SERIAL3_BAUD: Serial 3 (GPS) Baud Rate  
SERIAL4_PROTOCOL: Serial4 protocol selection  
SERIAL4_BAUD: Serial 4 Baud Rate  
SERIAL5_PROTOCOL: Serial5 protocol selection  
SERIAL5_BAUD: Serial 5 Baud Rate  
SERIAL6_PROTOCOL: Serial6 protocol selection  
SERIAL6_BAUD: Serial 6 Baud Rate  
SERIAL1_OPTIONS: Telem1 options  
SERIAL2_OPTIONS: Telem2 options  
SERIAL3_OPTIONS: Serial3 options  
SERIAL4_OPTIONS: Serial4 options  
SERIAL5_OPTIONS: Serial5 options  
SERIAL6_OPTIONS: Serial6 options  
SERIAL_PASS1: Serial passthru first port  
SERIAL_PASS2: Serial passthru second port  
SERIAL_PASSTIMO: Serial passthru timeout  
SERIAL7_PROTOCOL: Serial7 protocol selection  
SERIAL7_BAUD: Serial 7 Baud Rate  
SERIAL7_OPTIONS: Serial7 options  


# SERVO Parameters

SERVO_AUTO_TRIM: Automatic servo trim  
SERVO_RATE: Servo default output rate  


# SERVO10_ Parameters

SERVO10_MIN: Minimum PWM  
SERVO10_MAX: Maximum PWM  
SERVO10_TRIM: Trim PWM  
SERVO10_REVERSED: Servo reverse  
SERVO10_FUNCTION: Servo output function  


# SERVO11_ Parameters

SERVO11_MIN: Minimum PWM  
SERVO11_MAX: Maximum PWM  
SERVO11_TRIM: Trim PWM  
SERVO11_REVERSED: Servo reverse  
SERVO11_FUNCTION: Servo output function  


# SERVO12_ Parameters

SERVO12_MIN: Minimum PWM  
SERVO12_MAX: Maximum PWM  
SERVO12_TRIM: Trim PWM  
SERVO12_REVERSED: Servo reverse  
SERVO12_FUNCTION: Servo output function  


# SERVO13_ Parameters

SERVO13_MIN: Minimum PWM  
SERVO13_MAX: Maximum PWM  
SERVO13_TRIM: Trim PWM  
SERVO13_REVERSED: Servo reverse  
SERVO13_FUNCTION: Servo output function  


# SERVO14_ Parameters

SERVO14_MIN: Minimum PWM  
SERVO14_MAX: Maximum PWM  
SERVO14_TRIM: Trim PWM  
SERVO14_REVERSED: Servo reverse  
SERVO14_FUNCTION: Servo output function  


# SERVO15_ Parameters

SERVO15_MIN: Minimum PWM  
SERVO15_MAX: Maximum PWM  
SERVO15_TRIM: Trim PWM  
SERVO15_REVERSED: Servo reverse  
SERVO15_FUNCTION: Servo output function  


# SERVO16_ Parameters

SERVO16_MIN: Minimum PWM  
SERVO16_MAX: Maximum PWM  
SERVO16_TRIM: Trim PWM  
SERVO16_REVERSED: Servo reverse  
SERVO16_FUNCTION: Servo output function  


# SERVO1_ Parameters

SERVO1_MIN: Minimum PWM  
SERVO1_MAX: Maximum PWM  
SERVO1_TRIM: Trim PWM  
SERVO1_REVERSED: Servo reverse  
SERVO1_FUNCTION: Servo output function  


# SERVO2_ Parameters

SERVO2_MIN: Minimum PWM  
SERVO2_MAX: Maximum PWM  
SERVO2_TRIM: Trim PWM  
SERVO2_REVERSED: Servo reverse  
SERVO2_FUNCTION: Servo output function  


# SERVO3_ Parameters

SERVO3_MIN: Minimum PWM  
SERVO3_MAX: Maximum PWM  
SERVO3_TRIM: Trim PWM  
SERVO3_REVERSED: Servo reverse  
SERVO3_FUNCTION: Servo output function  


# SERVO4_ Parameters

SERVO4_MIN: Minimum PWM  
SERVO4_MAX: Maximum PWM  
SERVO4_TRIM: Trim PWM  
SERVO4_REVERSED: Servo reverse  
SERVO4_FUNCTION: Servo output function  


# SERVO5_ Parameters

SERVO5_MIN: Minimum PWM  
SERVO5_MAX: Maximum PWM  
SERVO5_TRIM: Trim PWM  
SERVO5_REVERSED: Servo reverse  
SERVO5_FUNCTION: Servo output function  


# SERVO6_ Parameters

SERVO6_MIN: Minimum PWM  
SERVO6_MAX: Maximum PWM  
SERVO6_TRIM: Trim PWM  
SERVO6_REVERSED: Servo reverse  
SERVO6_FUNCTION: Servo output function  


# SERVO7_ Parameters

SERVO7_MIN: Minimum PWM  
SERVO7_MAX: Maximum PWM  
SERVO7_TRIM: Trim PWM  
SERVO7_REVERSED: Servo reverse  
SERVO7_FUNCTION: Servo output function  


# SERVO8_ Parameters

SERVO8_MIN: Minimum PWM  
SERVO8_MAX: Maximum PWM  
SERVO8_TRIM: Trim PWM  
SERVO8_REVERSED: Servo reverse  
SERVO8_FUNCTION: Servo output function  


# SERVO9_ Parameters

SERVO9_MIN: Minimum PWM  
SERVO9_MAX: Maximum PWM  
SERVO9_TRIM: Trim PWM  
SERVO9_REVERSED: Servo reverse  
SERVO9_FUNCTION: Servo output function  


# SERVO_BLH_ Parameters

SERVO_BLH_MASK: BLHeli Channel Bitmask  
SERVO_BLH_AUTO: BLHeli auto-enable for multicopter motors  
SERVO_BLH_TEST: BLHeli internal interface test  
SERVO_BLH_TMOUT: BLHeli protocol timeout  
SERVO_BLH_TRATE: BLHeli telemetry rate  
SERVO_BLH_DEBUG: BLHeli debug level  
SERVO_BLH_OTYPE: BLHeli output type override  
SERVO_BLH_PORT: Control port  
SERVO_BLH_POLES: BLHeli Motor Poles  
SERVO_BLH_REMASK: BLHeli bitmask of reversible channels  


# SERVO_ROB_ Parameters

SERVO_ROB_POSMIN: Robotis servo position min  
SERVO_ROB_POSMAX: Robotis servo position max  


# SERVO_SBUS_ Parameters

SERVO_SBUS_RATE: SBUS default output rate  


# SERVO_VOLZ_ Parameters

SERVO_VOLZ_MASK: Channel Bitmask  


# SIM_GRPE_ Parameters

SIM_GRPE_ENABLE: Gripper servo Sim enable/disable  
SIM_GRPE_PIN: Gripper emp pin  


# SIM_GRPS_ Parameters

SIM_GRPS_ENABLE: Gripper servo Sim enable/disable  
SIM_GRPS_PIN: Gripper servo pin  
SIM_GRPS_GRAB: Gripper Grab PWM  
SIM_GRPS_RELEASE: Gripper Release PWM  
SIM_GRPS_REVERSE: Gripper close direction  


# SIM_PLD_ Parameters

SIM_PLD_ENABLE: Preland device Sim enable/disable  
SIM_PLD_LAT: Precland device origin’s latitude  
SIM_PLD_LON: Precland device origin’s longitude  
SIM_PLD_HEIGHT: Precland device origin’s height above sealevel  
SIM_PLD_YAW: Precland device systems rotation from north  
SIM_PLD_RATE: Precland device update rate  
SIM_PLD_TYPE: Precland device radiance type  
SIM_PLD_ALT_LIMIT: Precland device alt range  
SIM_PLD_DIST_LIMIT: Precland device lateral range  


# SIM_SPR_ Parameters

SIM_SPR_ENABLE: Gripper servo Sim enable/disable  
SIM_SPR_PUMP: Sprayer pump pin  
SIM_SPR_SPIN: Sprayer spinner servo pin  


# SOAR_ Parameters

SOAR_ENABLE: Is the soaring mode enabled or not  
SOAR_VSPEED: Vertical v-speed  
SOAR_DIST_AHEAD: Distance to thermal center  
SOAR_MIN_THML_S: Minimum thermalling time  
SOAR_MIN_CRSE_S: Minimum cruising time  
SOAR_POLAR_K: Cl factor  
SOAR_ALT_MAX: Maximum soaring altitude, relative to the home location  
SOAR_ALT_MIN: Minimum soaring altitude, relative to the home location  
SOAR_ALT_CUTOFF: Maximum power altitude, relative to the home location  
SOAR_ENABLE_CH: (Optional) RC channel that toggles the soaring controller on and off  


# SR0_ Parameters

SR0_RAW_SENS: Raw sensor stream rate  
SR0_EXT_STAT: Extended status stream rate to ground station  
SR0_RC_CHAN: RC Channel stream rate to ground station  
SR0_RAW_CTRL: Raw Control stream rate to ground station  
SR0_POSITION: Position stream rate to ground station  
SR0_EXTRA1: Extra data type 1 stream rate to ground station  
SR0_EXTRA2: Extra data type 2 stream rate to ground station  
SR0_EXTRA3: Extra data type 3 stream rate to ground station  
SR0_PARAMS: Parameter stream rate to ground station  
SR0_ADSB: ADSB stream rate to ground station  


# SR1_ Parameters

SR1_RAW_SENS: Raw sensor stream rate  
SR1_EXT_STAT: Extended status stream rate to ground station  
SR1_RC_CHAN: RC Channel stream rate to ground station  
SR1_RAW_CTRL: Raw Control stream rate to ground station  
SR1_POSITION: Position stream rate to ground station  
SR1_EXTRA1: Extra data type 1 stream rate to ground station  
SR1_EXTRA2: Extra data type 2 stream rate to ground station  
SR1_EXTRA3: Extra data type 3 stream rate to ground station  
SR1_PARAMS: Parameter stream rate to ground station  
SR1_ADSB: ADSB stream rate to ground station  


# SR2_ Parameters

SR2_RAW_SENS: Raw sensor stream rate  
SR2_EXT_STAT: Extended status stream rate to ground station  
SR2_RC_CHAN: RC Channel stream rate to ground station  
SR2_RAW_CTRL: Raw Control stream rate to ground station  
SR2_POSITION: Position stream rate to ground station  
SR2_EXTRA1: Extra data type 1 stream rate to ground station  
SR2_EXTRA2: Extra data type 2 stream rate to ground station  
SR2_EXTRA3: Extra data type 3 stream rate to ground station  
SR2_PARAMS: Parameter stream rate to ground station  
SR2_ADSB: ADSB stream rate to ground station  


# SR3_ Parameters

SR3_RAW_SENS: Raw sensor stream rate  
SR3_EXT_STAT: Extended status stream rate to ground station  
SR3_RC_CHAN: RC Channel stream rate to ground station  
SR3_RAW_CTRL: Raw Control stream rate to ground station  
SR3_POSITION: Position stream rate to ground station  
SR3_EXTRA1: Extra data type 1 stream rate to ground station  
SR3_EXTRA2: Extra data type 2 stream rate to ground station  
SR3_EXTRA3: Extra data type 3 stream rate to ground station  
SR3_PARAMS: Parameter stream rate to ground station  
SR3_ADSB: ADSB stream rate to ground station  


# STAT Parameters

STAT_BOOTCNT: Boot Count  
STAT_FLTTIME: Total FlightTime  
STAT_RUNTIME: Total RunTime  
STAT_RESET: Statistics Reset Time  


# STEER2SRV_ Parameters

STEER2SRV_TCONST: Steering Time Constant  
STEER2SRV_P: Steering turning gain  
STEER2SRV_I: Integrator Gain  
STEER2SRV_D: Damping Gain  
STEER2SRV_IMAX: Integrator limit  
STEER2SRV_MINSPD: Minimum speed  
STEER2SRV_FF: Steering feed forward  
STEER2SRV_DRTSPD: Derating speed  
STEER2SRV_DRTFCT: Derating factor  
STEER2SRV_DRTMIN: Minimum angle of wheel  


# TECS_ Parameters

TECS_CLMB_MAX: Maximum Climb Rate (metres/sec)  
TECS_SINK_MIN: Minimum Sink Rate (metres/sec)  
TECS_TIME_CONST: Controller time constant (sec)  
TECS_THR_DAMP: Controller throttle damping  
TECS_INTEG_GAIN: Controller integrator  
TECS_VERT_ACC: Vertical Acceleration Limit (metres/sec^2)  
TECS_HGT_OMEGA: Height complementary filter frequency (radians/sec)  
TECS_SPD_OMEGA: Speed complementary filter frequency (radians/sec)  
TECS_RLL2THR: Bank angle compensation gain  
TECS_SPDWEIGHT: Weighting applied to speed control  
TECS_PTCH_DAMP: Controller pitch damping  
TECS_SINK_MAX: Maximum Descent Rate (metres/sec)  
TECS_LAND_ARSPD: Airspeed during landing approach (m/s)  
TECS_LAND_THR: Cruise throttle during landing approach (percentage)  
TECS_LAND_SPDWGT: Weighting applied to speed control during landing.  
TECS_PITCH_MAX: Maximum pitch in auto flight  
TECS_PITCH_MIN: Minimum pitch in auto flight  
TECS_LAND_SINK: Sink rate for final landing stage  
TECS_LAND_TCONST: Land controller time constant (sec)  
TECS_LAND_DAMP: Controller sink rate to pitch gain during flare  
TECS_LAND_PMAX: Maximum pitch during final stage of landing  
TECS_APPR_SMAX: Sink rate max for landing approach stage  
TECS_LAND_SRC: Land sink rate change  
TECS_LAND_TDAMP: Controller throttle damping when landing  
TECS_LAND_IGAIN: Controller integrator during landing  
TECS_TKOFF_IGAIN: Controller integrator during takeoff  
TECS_LAND_PDAMP: Pitch damping gain when landing  
TECS_SYNAIRSPEED: Enable the use of synthetic airspeed  
TECS_OPTIONS: Extra TECS options  


# TERRAIN_ Parameters

TERRAIN_ENABLE: Terrain data enable  
TERRAIN_SPACING: Terrain grid spacing  


# TUNE_ Parameters

TUNE_PARAM: Transmitter tuning parameter or set of parameters  
TUNE_CHAN: Transmitter tuning channel  
TUNE_CHAN_MIN: Transmitter tuning channel minimum pwm  
TUNE_CHAN_MAX: Transmitter tuning channel maximum pwm  
TUNE_SELECTOR: Transmitter tuning selector channel  
TUNE_RANGE: Transmitter tuning range  
TUNE_MODE_REVERT: Revert on mode change  
TUNE_ERR_THRESH: Controller error threshold  


# YAW2SRV_ Parameters

YAW2SRV_SLIP: Sideslip control gain  
YAW2SRV_INT: Sideslip control integrator  
YAW2SRV_DAMP: Yaw damping  
YAW2SRV_RLL: Yaw coordination gain  
YAW2SRV_IMAX: Integrator limit  

