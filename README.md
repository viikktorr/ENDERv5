
Esto hace que los bloques de código se vean de otro color en Visual Studio Code gracias a la sintaxis resaltada (como `C`, `Python`, etc.). Pero esto no afecta el texto estándar.

---

### Opción 2: **Usar HTML dentro del Markdown (funciona en GitHub y otras plataformas)**

Puedes usar etiquetas HTML directamente en el Markdown para cambiar el color:

```markdown
# ⚙️ Configuración de Marlin

### 🔹 <span style="color:yellow;">[71]</span> - La placa base es **v4.2.7**  
`#define MOTHERBOARD BOARD_CREALITY_V427`

### 🔹 <span style="color:cyan;">[134]</span> - Nombre de la máquina cambiado  
`#define CUSTOM_MACHINE_NAME "Ender 5 - v4.2.7"`
