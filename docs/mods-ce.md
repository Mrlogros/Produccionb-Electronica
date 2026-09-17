# Preparación de Archivos con Mods CE

!!! abstract "Objetivo de esta fase"
    Una vez generados los archivos de las capas de nuestra placa en KiCad, es necesario "traducirlos" a un formato (G-Code/Toolpaths) que la fresadora CNC **Roland Monofab (SRM-20)** pueda interpretar para realizar el corte físico.

Para realizar esta conversión utilizaremos **Mods CE** (Community Edition), una plataforma basada en navegador ideal para la generación de trayectorias de fresado de PCBs.

---

## 1. Archivos Base (SVG)

El proceso comienza exportando las capas necesarias desde el editor de KiCad en formato vectorial (`.svg`). Debemos tener listos los archivos correspondientes a las **pistas**, **perforaciones**, **bordes** y **etiquetas** (opcional).

![Archivos SVG exportados](img/Imagen 54.png)

---

## 2. Acceso y Configuración del Entorno Mods CE

Para configurar nuestro espacio de trabajo, seguimos esta ruta de inicialización:

1. Ingresamos a la página oficial de [Mods CE](https://modsproject.org).
2. En la interfaz principal (identificable por el logo de la carita feliz en la pestaña), hacemos clic derecho o buscamos el menú de opciones en la esquina para abrir los **Programs**.
3. Navegamos hacia la sección de máquinas, buscamos **Roland SRM-20** y seleccionamos la opción **mill 2D PCB**.

<div style="display: flex; gap: 10px; justify-content: center; margin-top: 15px;">
  <img src="../img/Imagen 55.png" width="30%">
  <img src="../img/Imagen 56.png" width="30%">
  <img src="../img/Imagen 57.png" width="30%">
</div>

Al cargar el programa, se desplegará una red de nodos interconectados (diagrama de flujo de datos) que procesarán nuestro archivo desde el SVG hasta el archivo de corte de la máquina.

![Entorno de nodos de Mods CE](img/Imagen 58.png)

---

## 3. Configuración de Pistas (Traces)

Comenzaremos procesando el archivo de las pistas (`Pistas.svg`). En el nodo de entrada, cargamos nuestro archivo SVG. A continuación, configuramos los parámetros de la herramienta:

!!! tip "Parámetros de la Broca"
    Para el fresado de las pistas utilizaremos una broca plana estándar. En el nodo de configuración (*set PCB defaults*), seleccionamos **0.40mm flat** (lo que equivale aproximadamente a 1/64 de pulgada).

![Configuración de herramienta](img/Imagen 59.png)

### Ajuste de Pasadas (Offsets)
En el nodo **mill raster 2D**, definiremos cuánto material queremos remover alrededor de cada pista:

* **Offset number:** Lo configuramos en `4`. Esto indica que el taladro realizará cuatro pasadas concéntricas alrededor de las pistas para asegurar un buen aislamiento de cobre.
* Una vez configurado, hacemos clic en el botón **Calculate**.

![Cálculo de trayectorias](img/Imagen 60.png)

---

## 4. Visualización y Renderizado

Al presionar *Calculate*, Mods CE generará el plano de trayectorias de la herramienta (toolpath). 

![Plano de trayectorias 2D](img/Imagen 61.png)

Podemos hacer clic en el botón **View** para obtener un renderizado 3D de cómo quedará la placa físicamente. 

!!! warning "Interpretación del Renderizado"
    En el renderizado 3D, **el área oscura representa el cobre que será removido** por la fresadora, mientras que el área clara e intacta representa nuestras pistas y pads eléctricos. 

![Renderizado 3D de la placa](img/Imagen 62.png)

---

## 5. Origen y Velocidad (Nodo SRM-20)

El último paso antes de exportar el archivo es configurar los parámetros físicos de la máquina en el nodo final **Roland SRM-20 milling machine**:

* **Speed (Velocidad):** Ajustamos la velocidad de fresado a `4 mm/s` para evitar rupturas en la broca y asegurar cortes limpios.
* **Origin (Origen de coordenadas):**
    * Se configura en **X: 0, Y: 0, Z: 0** para la fabricación de una placa individual principal. 
    * *Nota:* Si se requiere producir múltiples placas (panelización) en el mismo bloque de cobre, este origen en los ejes X o Y deberá desfasarse correspondientemente.

![Configuración final de máquina](img/Imagen 63.png)

Una vez verificados estos datos, el archivo estará listo para ser guardado y enviado al software de control de la Monofab (VPanel).
