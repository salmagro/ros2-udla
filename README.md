# Introducción a ROS 2 Jazzy (Ubuntu 24.04)

Este repositorio contiene el código fuente y los ejemplos prácticos utilizados durante el curso de introducción a **ROS 2 Jazzy**.

Está organizado en secciones que acompañan cada módulo del curso, cubriendo desde los conceptos básicos hasta el uso avanzado de herramientas como URDF, TF y Xacro.

---

## 📁 Estructura del repositorio

El contenido se organiza por carpetas llamadas `Seccion X`, donde **X** representa el número correspondiente a una unidad del curso. A medida que el curso progresa, algunos paquetes se **modifican o amplían** manteniendo el mismo nombre, lo cual puede generar **conflictos al compilar**.

---

## ⚠️ Importante: Conflictos al compilar

Si intentas compilar el workspace completo (`colcon build`) con múltiples versiones de un **mismo paquete** (por ejemplo, extendido entre la Sección 5 y Sección 6), **`colcon` fallará** debido a la colisión de nombres.

### ✅ Solución: Usa `AMENT_IGNORE`

Para compilar solo una versión de un paquete a la vez, debes **ignorar temporalmente** las demás versiones. Hazlo creando un archivo vacío llamado `AMENT_IGNORE` dentro de las carpetas de los paquetes que **no deseas compilar**:

```bash
touch Seccion5/AMENT_IGNORE
```

Esto le indica a colcon que omita ese paquete/directorio durante la compilación.

### 🛠️ Compilación y ejecución
```
colcon build --symlink-install
source install/setup.bash
ros2 run <nombre_paquete> <nombre_nodo>
```
Recuerda: activa solo los paquetes necesarios eliminando el archivo AMENT_IGNORE antes de compilar.

### 📦 Secciones incluidas

El repositorio actualmente incluye el código fuente correspondiente a las siguientes secciones del curso:

* Sección 3: Primeros programas ROS 2 (Python y C++)

* Sección 5: Topics – Comunicación entre nodos

* Sección 6: Services – Cliente / Servidor

* Sección 7: Parámetros en nodos

* Sección 8: Archivos Launch (XML y Python)

* Sección 10: URDF – Descripción de robots

* Sección 11: TF – Publicación de transformaciones

* Sección 12: Xacro – Optimización del URDF