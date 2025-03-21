## 📜 **Configuration File for Creality Ender 5 (with BL Touch)** 🖨️

### 🔧 **(Modified values in ["Configuration.h"](./Config%20Files/Configuration.h))** 🔧

🔹 **[93]** - The motherboard is **v4.2.7**
```c
#define MOTHERBOARD BOARD_CREALITY_V427 
```

🔹 [143] - **(Optional)** Change name
```c
#define CUSTOM_MACHINE_NAME "Ender 5 - v4.2.7"
```

🔹 [166,167,168,180] - In my case, I used TMC2209_STANDALONE, but TMC2208_STANDALONE would also work
```c
#define X_DRIVER_TYPE  TMC2209_STANDALONE
#define Y_DRIVER_TYPE  TMC2209_STANDALONE
#define Z_DRIVER_TYPE  TMC2209_STANDALONE
#define E0_DRIVER_TYPE TMC2209_STANDALONE
```

🔹 [1340] - This value should be like this
```c
//#define PROBE_MANUALLY
```

🔹 [1517] - My values are these
```c
#define NOZZLE_TO_PROBE_OFFSET { -44, -5, -0.4 }
```

🔹 [1911] - By default, 2106 is uncommented; you need to comment it and uncomment 2107, so it should look like this:
```c
//#define AUTO_BED_LEVELING_3POINT
//#define AUTO_BED_LEVELING_LINEAR
#define AUTO_BED_LEVELING_BILINEAR
//#define AUTO_BED_LEVELING_UBL
//#define MESH_BED_LEVELING
```

🔹 [1932-1936] - **(OPTIONAL)** - Enable preheating both the NOZZLE and the BED before leveling:
```c
#define PREHEAT_BEFORE_LEVELING
#if ENABLED(PREHEAT_BEFORE_LEVELING)
    #define LEVELING_NOZZLE_TEMP 120   // (°C) Only applies to E0 at this time
    #define LEVELING_BED_TEMP     60
#endif
```

🔹 [1997] - **(OPTIONAL)** but RECOMMENDED, as by default it will only do 3x3, 9 points in total. As shown, it will do 25 points.
```c
#define GRID_MAX_POINTS_X 5
```

### 🔧 (Modified values in ["Configuration_adv.h"](./Config%20Files/Configuration_adv.h)) 🔧

🔹 [2092] - Uncomment this line, which is useful for adjusting the extruder (nozzle) while printing
```c
#define BABYSTEP_ZPROBE_OFFSET
```

## [CURRENT CONFIG]

```c
>>> m503
SENDING:M503
echo:; Linear Units:
echo:  G21 ; (mm)
echo:; Temperature Units:
echo:  M149 C ; Units in Celsius
echo:; Filament settings (Disabled):
echo:  M200 S0 D1.75
echo:; Steps per unit:
echo:  M92 X80.00 Y80.00 Z400.00 E93.00
echo:; Max feedrates (units/s):
echo:  M203 X500.00 Y500.00 Z5.00 E25.00
echo:; Max Acceleration (units/s2):
echo:  M201 X500.00 Y500.00 Z100.00 E5000.00
echo:; Acceleration (units/s2) (P<print-accel> R<retract-accel> T<travel-accel>):
echo:  M204 P500.00 R500.00 T500.00
echo:; Advanced (B<min_segment_time_us> S<min_feedrate> T<min_travel_feedrate> J<junc_dev>):
echo:  M205 B20000.00 S0.00 T0.00 J0.08
echo:; Home offset:
echo:  M206 X0.00 Y0.00 Z0.00
echo:; Auto Bed Leveling:
echo:  M420 S0 Z10.00 ; Leveling OFF
echo:; Material heatup parameters:
echo:  M145 S0 H185.00 B45.00 F255
echo:  M145 S1 H240.00 B70.00 F255
echo:; Hotend PID:
echo:  M301 P21.73 I1.54 D76.55
echo:; Z-Probe Offset:
echo:  M851 X-44.00 Y-5.00 Z-0.40 ; (mm)
```
