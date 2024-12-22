## 📜 **Configuration File for Creality Ender 5 (with BL Touch)** 🖨️

### 🔧 **(Modified values in ["Configuration.h"](./Config%20Files/Configuration.h))** 🔧

🔹 **[71]** - The motherboard is **v4.2.7**
```c
#define MOTHERBOARD BOARD_CREALITY_V427 
```

🔹 [134] - **(Optional)** Change name
```c
#define CUSTOM_MACHINE_NAME "Ender 5 - v4.2.7"
```

🔹 [157,158,159,171] - In my case, I used TMC2209_STANDALONE, but TMC2208_STANDALONE would also work
```c
#define X_DRIVER_TYPE  TMC2209_STANDALONE
#define Y_DRIVER_TYPE  TMC2209_STANDALONE
#define Z_DRIVER_TYPE  TMC2209_STANDALONE
#define E0_DRIVER_TYPE TMC2209_STANDALONE
```

🔹 [1641] - My values are these
```c
#define NOZZLE_TO_PROBE_OFFSET { -44, -5, -0.4 }
```

🔹 [2106] - By default, 2106 is uncommented; you need to comment it and uncomment 2107, so it should look like this:
```c
//#define AUTO_BED_LEVELING_3POINT
//#define AUTO_BED_LEVELING_LINEAR
#define AUTO_BED_LEVELING_BILINEAR
//#define AUTO_BED_LEVELING_UBL
//#define MESH_BED_LEVELING
```

🔹 [2130-2131] - **(OPTIONAL)** - Enable preheating both the NOZZLE and the BED before leveling:
```c
#define PREHEAT_BEFORE_LEVELING
#if ENABLED(PREHEAT_BEFORE_LEVELING)
    #define LEVELING_NOZZLE_TEMP 120   // (°C) Only applies to E0 at this time
    #define LEVELING_BED_TEMP     60
#endif
```

🔹 [2190] - **(OPTIONAL)** but RECOMMENDED, as by default it will only do 3x3, 9 points in total. As shown, it will do 25 points.
```c
#define GRID_MAX_POINTS_X 5
```

### 🔧 (Modified values in ["Configuration_adv.h"](./Config%20Files/Configuration_adv.h)) 🔧

🔹 [2311] - Uncomment this line, which is useful for adjusting the extruder (nozzle) while printing
```c
#define BABYSTEP_ZPROBE_OFFSET
```