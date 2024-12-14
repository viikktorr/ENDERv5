## 📜 **Archivo de Configuración de Creality Ender 5 (con BL Touch)** 🖨️

#### 🔧 **(Valores modificados en "Configuration.h")** 🔧

- 🔹 [71] - La placa base es v4.2.7 ➡ **MOTHERBOARD BOARD_CREALITY_V427**
- 🔹 [134] - (Opcional) Nombre de máquina cambiado ➡ **CUSTOM_MACHINE_NAME "Ender 5 - v4.2.7"**
- 🔹 [157,158,159,171] - Por defecto está asi ➡ **TMC2208_STANDALONE**, pero el mío es **TMC2209_STANDALONE**
- 🔹 [1641] - Por defecto está asi ➡ **NOZZLE_TO_PROBE_OFFSET { -44, -5, 0 }**, así mismo lo tengo yo
- 🔹 [2106] - Por defecto esta asi ➡ **#define AUTO_BED_LEVELING_LINEAR**, hay que comentarlo con // delante
- 🔹 [2107] - Y descomentamos esta, que quede asi ➡ **#define AUTO_BED_LEVELING_BILINEAR**
- 🔹 [2130 / 2131] - Por defecto esta en **120ºC y 50ºC**, se puede cambiar, es para calentar cuando se nivela la cama. Desde la 2128 a 2132 asegurarse que estan descomentadas.
- 🔹 [2190] - He cambiado el valor que viene por defecto en **#define GRID_MAX_POINTS_X 3**, el 3 por un 5, ya que asi ara un total de 25 puntos y no 9 como hace por defecto, con eso conseguimos que el nivel de calibración sea con mayor precisión.

#### 🔧 **(Valores modificados en "Configuration_adv.h")** 🔧

- 🔹 [2311] - En el default esta asi ➡ **//#define BABYSTEP_ZPROBE_OFFSET**,  hay que descomentarlo, quitando //