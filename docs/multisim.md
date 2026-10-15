# 5. Simulación de Circuitos en NI Multisim

Antes de la implementación física de cualquier circuito, es una práctica estándar en la ingeniería electrónica validar el comportamiento lógico y matemático de los componentes. En esta sección documentaremos dos procesos fundamentales en el entorno de simulación **NI Multisim**: el análisis de barrido en corriente continua (DC Sweep) de un transistor y la instrumentación virtual (rectificación de media onda).

---

## 5.1 Análisis de Barrido en Corriente Continua (DC Sweep)

El análisis **DC Sweep** nos permite someter un circuito a múltiples variaciones de voltaje o corriente de forma automatizada, generando una familia de curvas características que describen el comportamiento del componente (en este caso, un transistor BJT).

### Construcción del Circuito Base
El esquema base consta de un transistor NPN modelo `2N2222A` (etiquetado como `Q1`). Este componente es polarizado por dos fuentes independientes:
*   **Fuente de Voltaje (VCE):** Conectada al colector (malla derecha), será nuestra "Source 1".
*   **Fuente de Corriente (IB):** Conectada a la base (malla izquierda), será nuestra "Source 2".

![Circuito Base Transistor](img/fotos_multisim/Imagen7.png){ width="500" }
*Figura 5.1.1: Topología del circuito de prueba para análisis DC.*

### Configuración de Parámetros de Barrido
Para configurar la simulación, nos dirigimos a la barra superior y seleccionamos la herramienta **`DC Sweep`** (indicada en el recuadro rojo de la siguiente imagen).

| Acceso a Herramienta | Parámetros de Fuentes |
| :---: | :---: |
| ![Acceso DC Sweep](img/fotos_multisim/Imagen5.png){ width="400" } | ![Configuración de Barrido](img/fotos_multisim/Imagen6.png){ width="400" } |

Dentro de la ventana de configuración, en la pestaña **Analysis parameters**, indicaremos al simulador qué valores van a ir cambiando:
1.  **Source 1 (VCE):** Se define el rango de operación de la fuente de voltaje principal. Establecemos el valor inicial (`Start value`), el valor final (`Stop value`) a 10V, y determinamos de cuánto en cuánto incrementará.
2.  **Source 2 (IB):** Activamos la casilla "Use source 2" para anidar una segunda variación. Si deseamos modificar la cantidad de curvas que se graficarán, ajustamos el valor de `Increment` de la corriente de base (IB). En este ejemplo, el incremento está ajustado a `0.0005 A`, generando así un número específico de trazos.

### Selección de Variables de Salida (Output)
Para que el simulador sepa qué información debe graficar, debemos pasar a la pestaña **Output (Salidas)**.

1.  En la columna izquierda (`Variables in circuit`), localizamos y seleccionamos la variable que deseamos analizar; en este caso, la corriente de colector del transistor: `I(Q1[IC])`.
2.  Hacemos clic en el botón **Add** (Añadir) para trasladar la variable a la columna de análisis seleccionada a la derecha.
3.  Con la variable configurada, presionamos el botón **Run** (ícono verde de Play) en la parte inferior para iniciar el cálculo matemático.

| Selección de Variable Output | Ejecución de Simulación |
| :---: | :---: |
| ![Añadir Variable](img/fotos_multisim/Imagen2.png){ width="400" } | ![Botón Run](img/fotos_multisim/Imagen3.png){ width="400" } |

### Análisis del Graficador (Grapher View)
Al ejecutar la simulación, se desplegará una nueva ventana denominada **Grapher View** mostrando las "3 barridas" calculadas por el software basándose en los parámetros previamente ingresados.

El gráfico `DC Transfer Characteristic` nos muestra la corriente de colector (Eje Y) en función del voltaje colector-emisor (Eje X). El comportamiento se divide en tres curvas según la corriente de base (IB):

*   ⬇️ **Flecha Amarilla (Línea Roja):** Representa el estado de corte, donde la corriente de base (IB) es 0.
*   ➡️ **Flecha Naranja (Línea Verde):** Muestra el estado activo de amplificación cuando la corriente IB incrementó a 0.0005 A.
*   ⬆️ **Flecha Azul (Línea Azul):** Ilustra el punto de saturación superior, cuando IB alcanza su valor máximo configurado de 0.001 A.

![Resultados DC Sweep](img/fotos_multisim/Imagen4.png){ width="700" }
*Figura 5.1.2: Familia de curvas características del transistor 2N2222A.*

---

## 5.2 Instrumentación Virtual: Rectificación de Media Onda

En esta segunda fase, utilizaremos herramientas de instrumentación virtual para analizar el comportamiento transitorio de una señal en corriente alterna (AC) al atravesar un diodo rectificador.

### Selección de Componentes y Ensamblaje
Nos dirigimos a la barra de herramientas superior y abrimos la base de datos de componentes haciendo clic en el icono del diodo.

| Icono de Base de Datos | Selección de Componentes |
| :---: | :---: |
| ![Icono Diodo](img/fotos_multisim/Imagen9.png){ width="200" } | ![Selección de Diodo](img/fotos_multisim/Imagen11.png){ width="300" } |

En la ventana emergente `Select a Component`:
1.  Buscamos en el grupo de familias la opción **DIODE** y seleccionamos el modelo rectificador `1BH62`.
2.  Repetimos el proceso buscando la familia **RESISTOR** para insertar una resistencia de carga de `1kΩ`.

![Selección de Resistencia](img/fotos_multisim/Imagen12.png){ width="500" }
*Figura 5.2.1: Selección de resistor desde la librería virtual.*

### Generación y Monitoreo de Señales

Para inyectar una señal alterna al circuito, debemos insertar un **Generador de Funciones** (`Function Generator`). Este se localiza en la barra de instrumentos virtual del lado derecho.

| Icono Generador | Interfaz de Configuración |
| :---: | :---: |
| ![Icono Generador](img/fotos_multisim/Imagen8.png){ width="150" } | ![Parámetros Generador](img/fotos_multisim/Imagen14.png){ width="350" } |

Haciendo doble clic sobre el bloque del generador (etiquetado como `XFG1`), configuramos los parámetros para simular la red eléctrica convencional:
*   **Frecuencia (Frequency):** `60 Hz`.
*   **Amplitud (Amplitude):** `120 Vp` (Voltios pico).

Para visualizar el resultado de la rectificación, añadimos un **Osciloscopio** desde la misma barra de instrumentos lateral (cuarto ícono).

| Icono Osciloscopio | Circuito Interconectado |
| :---: | :---: |
| ![Icono Osciloscopio](img/fotos_multisim/Imagen19.png){ width="150" } | ![Circuito Rectificador](img/fotos_multisim/Imagen13.png){ width="450" } |

### Configuración del Modo Interactivo

Es crucial verificar que el simulador esté configurado correctamente para leer instrumentos en tiempo real. En el menú superior de simulación, debemos asegurarnos de que la opción seleccionada sea **`Interactive Simulation`**. Si se deja en `DC Sweep` o en otro modo de análisis avanzado, el programa arrojará un error al intentar utilizar el osciloscopio.

| Menú de Tipo de Simulación | Confirmación Visual |
| :---: | :---: |
| ![Configuración Interactiva](img/fotos_multisim/Imagen20.png){ width="300" } | ![Modo Interactivo Activo](img/fotos_multisim/Imagen1.png){ width="300" } |

Al iniciar la simulación en modo interactivo, podremos hacer doble clic en el osciloscopio (`XSC1`) para visualizar la gráfica en tiempo real. El instrumento revelará la onda recortada, evidenciando el fenómeno físico de la rectificación de media onda provocado por el diodo al bloquear el semiciclo negativo de la señal senoidal original.

![Resultado Osciloscopio](img/fotos_multisim/Imagen22.png){ width="600" }
*Figura 5.2.2: Forma de onda rectificada capturada por el osciloscopio virtual estándar.*

---

## 5.3 Técnicas Avanzadas de Visualización 

Cuando se analizan múltiples señales simultáneamente, es imperativo establecer un código de colores en el esquemático. El color de las trazas graficadas por el osciloscopio virtual hereda automáticamente el color del cable (Net) conectado a su canal de entrada.

### Asignación de Color a Redes (Nets)
Para diferenciar las señales en el graficador, aplicaremos colores distintos a los nodos de entrada y salida:

1.  Hacemos clic derecho sobre el segmento de cable deseado y seleccionamos **`Properties`** (Propiedades) en el menú contextual.
2.  En la ventana `Net Properties`, navegamos a la pestaña `Net name`.
3.  Hacemos clic en el cuadro inferior denominado **`Net color`** para desplegar la paleta cromática.
4.  Seleccionamos un color de alto contraste (por ejemplo, verde claro) y confirmamos haciendo clic en **OK**.

| Menú Contextual (Clic Derecho) | Propiedades de Red | Paleta de Colores |
| :---: | :---: | :---: |
| ![Propiedades Cable](img/fotos_multisim/Imagen23.png){ width="200" } | ![Ventana Net Properties](img/fotos_multisim/Imagen24.png){ width="250" } | ![Paleta de Color](img/fotos_multisim/Imagen25.png){ width="350" } |

### Implementación del Osciloscopio Tektronix (4 Canales)

Multisim ofrece simulaciones de equipos de laboratorio comerciales. Para obtener una lectura más robusta y detallada, podemos sustituir el osciloscopio genérico por el modelo **Tektronix TDS 2024** (ubicado en la barra lateral derecha).

| Selección Tektronix | Conexiones de Prueba |
| :---: | :---: |
| ![Icono Tektronix](img/fotos_multisim/Imagen27.png){ width="150" } | ![Conexión Avanzada](img/fotos_multisim/Imagen26.png){ width="450" } |

Reconfiguramos nuestro circuito aplicando la técnica de color en los cables y enlazándolos a los puertos del nuevo instrumento:
*   **Canal 1 (Cable Verde):** Conectado al nodo inicial (antes del diodo) para monitorear la señal senoidal completa proveniente del generador.
*   **Canal 2 (Cable Rojo):** Conectado al nodo central (entre el diodo y la resistencia) para registrar la señal resultante (rectificada).

![Conexión en Circuito con Tektronix](img/fotos_multisim/Imagen28.png){ width="600" }
*Figura 5.3.1: Configuración final del circuito integrando el osciloscopio avanzado.*

Al correr la simulación y hacer doble clic sobre el bloque del Tektronix, se desplegará una interfaz idéntica al equipo físico real. 

![Interfaz Tektronix Real](img/fotos_multisim/Imagen29.png){ width="600" }
*Figura 5.3.2: Osciloscopio Tektronix mostrando la comparación simultánea entre la señal de entrada completa (Canal 1 - Verde) y la señal rectificada (Canal 2 - Rojo).*

Este tipo de instrumentos virtuales avanzados permite no solo visualizar las formas de onda, sino que incorpora botoneras funcionales para activar cursores matemáticos, medir desfases y analizar frecuencias mediante la Transformada Rápida de Fourier (FFT), demostrando la potencia de la simulación previa a la fabricación.
