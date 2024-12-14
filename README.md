## 📜 **Archivo de Configuración de Creality Ender 5 (con BL Touch)** 🖨️

### 🔧 **(Valores modificados en "Configuration.h")** 🔧

🔹 **[71]** - La placa base es **v4.2.7**
```c
    #define MOTHERBOARD BOARD_CREALITY_V427 
```

🔹 **[134]** - **(Opcional)** Cambiar nombre
```c
    #define CUSTOM_MACHINE_NAME "Ender 5 - v4.2.7"
```

🔹 **[157,158,159,171]** - En mi caso puse **TMC2209_STANDALONE**, pero **TMC2208_STANDALONE**, tambien iria bien
```c
    #define X_DRIVER_TYPE  TMC2209_STANDALONE
    #define Y_DRIVER_TYPE  TMC2209_STANDALONE
    #define Z_DRIVER_TYPE  TMC2209_STANDALONE
    #define E0_DRIVER_TYPE TMC2209_STANDALONE
```

🔹 **[1641]** - Creo que asi como esta, es por defecto
```c
    #define NOZZLE_TO_PROBE_OFFSET { -44, -5, 0 }
```

🔹 **[2106]** - Por defecto la **2106**, viene descomentada, hay que comentarla y descomentar la **2107**, asi debe quedar:
```c
    //#define AUTO_BED_LEVELING_3POINT
    //#define AUTO_BED_LEVELING_LINEAR
    #define AUTO_BED_LEVELING_BILINEAR
    //#define AUTO_BED_LEVELING_UBL
    //#define MESH_BED_LEVELING
```

🔹 **[2130-2131]** - **OPCIONAL** - Habilitar que al calibrar la cama se tenga que calentar, tanto **NOZZLE** como **BED**:
```c
    #define PREHEAT_BEFORE_LEVELING
    #if ENABLED(PREHEAT_BEFORE_LEVELING)
        #define LEVELING_NOZZLE_TEMP 120   // (°C) Only applies to E0 at this time
        #define LEVELING_BED_TEMP     60
    #endif
```

🔹 **[2190]** - **OPCIONAL** pero **RECOMENDABLE**, ya que por defecto solo hara 3X3, 9 puntos en total, asi como se ve hará 25 puntos
```c
    #define GRID_MAX_POINTS_X 5
```

### 🔧 **(Valores modificados en "Configuration_adv.h")** 🔧

🔹 **[2311]** - Descomentar esta linea, esto sirve para ajustar el extrusor (boquilla), mientras se esta imprimendo algo
```c
    #define BABYSTEP_ZPROBE_OFFSET
```