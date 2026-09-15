# 📝 Diseño del Esquemático

Bienvenidos a la primera fase técnica de nuestro proyecto. En esta sección, el **KiCad Squad** documentará paso a paso el proceso que seguimos y las herramientas que utilizamos para construir nuestro primer diagrama esquemático.

El objetivo de esta etapa es definir la lógica de nuestro circuito, configurar el entorno con las librerías necesarias y establecer las conexiones eléctricas correctas.

---

## 🚀 Proceso de Diseño Paso a Paso

A continuación, detallamos el flujo de trabajo utilizado para la creación de nuestro esquemático en KiCad:

### 1. Creación y Apertura del Proyecto
Comenzamos inicializando nuestro entorno de trabajo. Abrimos KiCad y cargamos nuestro archivo de proyecto principal (`.kicad_pro`). Mantener los archivos organizados en su respectiva carpeta es vital para evitar pérdida de enlaces.

![Apertura del proyecto en KiCad](img/Imagen 1.png)
*Interfaz principal de KiCad con el proyecto cargado.*

![Explorador de archivos](img/Imagen 2.png)
*Directorio raíz del proyecto asegurando la correcta ubicación de los archivos.*

### 2. Instalación de Librerías Externas (FabLib)
Para estandarizar nuestros componentes, utilizamos librerías específicas. Abrimos el **Administrador de complementos y contenido** desde la pantalla principal.

![Administrador de complementos](img/Imagen 3.png)
*Búsqueda de librerías en el gestor de paquetes de KiCad.*

Buscamos e instalamos la librería **KiCad FabLib**, la cual nos proporciona huellas y símbolos compatibles con inventarios estándar de fabricación.

![Instalación de FabLib](img/Imagen 4.png)
*Confirmación de la librería FabLib instalada.*

### 3. Acceso al Entorno de Diseño
Una vez configuradas las librerías, procedimos a abrir el entorno de diseño lógico. Esto se puede hacer desde la pantalla principal o utilizando el menú de herramientas seleccionando el **Editor de esquemas** (atajo `Ctrl + E`).

![Menú de Editor de Esquemas](img/Imagen 5.png)
*Accediendo al Eeschema.*

### 4. Selección y Colocación de Componentes
Dentro del editor, utilizamos la barra de herramientas lateral derecha. Seleccionamos la herramienta **Colocar símbolos** (atajo de teclado `A`) para buscar las partes que conformarán nuestro circuito.

![Herramienta Colocar Símbolos](img/Imagen 6.png)
*Icono de la herramienta para agregar componentes.*

Utilizamos el buscador para localizar un diodo emisor de luz. En este caso, seleccionamos un `LED_1206` asegurándonos de usar el componente proveniente de nuestra librería previamente instalada.

![Selección de LED](img/Imagen 7.png)
*Ventana de selección de símbolos ubicando el LED SMD 1206.*

### 5. Configuración de Alimentación
Todo circuito requiere referencias de voltaje y tierra. Seleccionamos la herramienta **Colocar símbolos de alimentación** (atajo de teclado `P`).

![Herramienta de Alimentación](img/Imagen 8.png)
*Icono de la herramienta para agregar puertos de energía.*

Elegimos el símbolo `PWR_3V3` para indicar la línea de voltaje positivo que alimentará nuestro sistema de LEDs.

![Selección de PWR_3V3](img/Imagen 9.png)
*Seleccionando la etiqueta global de alimentación a 3.3V.*

### 6. Ruteo Lógico y Conexiones (Wiring)
Finalmente, con los símbolos y las referencias de poder en la hoja de trabajo, utilizamos la herramienta **Dibujar cables** (atajo de teclado `W`) para interconectar los pines y cerrar el circuito lógico.

![Herramienta Dibujar Cables](img/Imagen 10.png)
*Icono de la herramienta de cableado.*

### 7. Organización y Legibilidad del Diagrama
Un buen esquemático no solo debe funcionar, sino que debe ser fácil de leer para cualquier ingeniero. Para lograr esto, utilizamos etiquetas de red (Net Labels) en lugar de trazar líneas largas por toda la pantalla.

![Propiedades de la etiqueta](img/Imagen 11.png)
*Configuración de etiquetas de red para organizar las conexiones lógicas.*

Para delimitar las diferentes etapas de nuestro circuito, usamos la herramienta de **Texto** y **Dibujar rectángulos**. 

![Propiedades del texto](img/Imagen 12.png)
*Herramienta de texto para nombrar los módulos del circuito.*

![Herramienta de rectángulos](img/Imagen 13.png)
*Icono de la herramienta gráfica para crear bloques visuales.*

Con estas herramientas gráficas, separamos el diseño en bloques funcionales claros (por ejemplo, el bloque de "Pines" y el bloque de "Switches").

![Esquemático General Organizado](img/Imagen 14.png)
*Vista general del esquemático final, organizado por bloques y etiquetas, garantizando una excelente legibilidad.*

Aquí podemos observar en detalle cómo las etiquetas (`V 3.3`) conectan virtualmente la alimentación a los componentes sin necesidad de cruzar cables por todo el plano.

![Detalle de conexiones y resistencias](img/Imagen 15.png)
*Acercamiento al bloque de LEDs mostrando resistencias pull-down/pull-up y referencias.*

![Detalle de etiqueta de voltaje](img/Imagen 16.png)
*Detalle de la conexión virtual mediante etiquetas de red.*

### 8. Configuración de Componentes (Valores y Huellas)
El siguiente paso crítico fue definir las propiedades físicas y eléctricas de cada símbolo. Haciendo doble clic sobre los componentes (o usando la tecla `E`), entramos a la ventana de propiedades.

![Propiedades del Símbolo](img/Imagen 17.png)
*Asignando valores (ej. R_220 para 220 ohms) y vinculando la huella física (Footprint) correcta desde la librería FabLib.*

### 9. Verificación de Reglas Eléctricas (ERC)
Como control de calidad final antes de pasar a fabricar la placa física, ejecutamos el **Control de Reglas Eléctricas (ERC)**. Esta herramienta de KiCad escanea el esquemático en busca de pines sin conectar, cortocircuitos o conflictos de alimentación.

![Icono de ERC](img/Imagen 18.png)
*Ejecución del verificador de reglas eléctricas en la barra superior.*

![Resultados del ERC](img/Imagen 19.png)
*Reporte final del ERC.*

!!! success "Validación Exitosa"
    El reporte arrojó **0 Errores**, lo que significa que no existen cortocircuitos ni conexiones críticas faltantes. Las dos advertencias mostradas son informativas (uso de múltiples etiquetas como `PWR_GND` y `GND` para la misma red), lo cual es una práctica segura. **¡El esquemático está listo para pasar al Editor de Placas (Layout)!**
