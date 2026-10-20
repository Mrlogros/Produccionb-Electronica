# 6. Diseño Avanzado de PCB en Altium Designer

Altium Designer es una de las herramientas de automatización de diseño electrónico (EDA) más potentes y utilizadas a nivel industrial. En esta sección documentaremos el flujo de trabajo inicial, desde la configuración del entorno y licencias académicas, hasta la creación del proyecto y captura del diagrama esquemático.

---

## 6.1 Instalación y Configuración del Entorno

El primer paso para utilizar Altium Designer es instalar la suite y vincular la licencia correspondiente a nuestra institución.

### Descarga del Instalador
Para obtener el software, nos dirigimos al portal oficial de descargas de Altium. En la sección de Altium Designer, seleccionamos la opción de **Online Installer (exe)**, la cual se encargará de gestionar los paquetes necesarios durante la instalación.

![Descarga Altium Designer](img/fotos_altium/Imagen1.png){ width="700" }
*Figura 6.1.1: Portal oficial de descargas de Altium.*

### Gestión de Licencias
La primera vez que ejecutemos el programa, se mostrará el panel de administración de licencias (`License Management`). Para habilitar las herramientas de diseño, es necesario iniciar sesión y seleccionar una licencia activa. En este caso, seleccionaremos la licencia profesional institucional (indicada en el recuadro rojo) y haremos clic en el botón para activarla.

![Gestión de Licencias](img/fotos_altium/Imagen3.png){ width="700" }
*Figura 6.1.2: Activación de la licencia institucional en el panel de Altium.*

### Conexión al Workspace Institucional
El último paso crítico antes de diseñar es vincular nuestro entorno con el espacio de trabajo en la nube de la universidad (Altium 365). 

Nos dirigimos a la esquina superior derecha de la interfaz. Si no estamos conectados, hacemos clic en el icono de usuario y seleccionamos **Unirse a un grupo**. Introducimos nuestro correo institucional, la contraseña asignada, y el código de verificación enviado al correo. Al finalizar, el indicador mostrará el estado de conexión activa.

![Conexión Workspace](img/fotos_altium/Imagen4.png){ width="450" }
*Figura 6.1.3: Verificación de conexión activa al Workspace universitario.*

---

## 6.2 Creación y Estructura del Proyecto

Altium Designer organiza los archivos mediante un archivo maestro de proyecto (`.PrjPcb`) que vincula lógicamente los esquemáticos y los diseños físicos de la placa.

### Inicialización del Proyecto
Para crear el directorio contenedor, nos dirigimos a la esquina superior izquierda y seleccionamos la ruta: **`File > New > Project...`**.

![Crear Nuevo Proyecto](img/fotos_altium/Imagen5.png){ width="350" }
*Figura 6.2.1: Ruta de acceso para la creación de un nuevo proyecto.*

En la ventana de creación (`Create Project`), por defecto el sistema sugiere guardar el proyecto en la nube institucional. Si deseamos trabajarlo localmente, seleccionamos la opción de **Version Control** o **Local Projects**. Asignamos un nombre estructurado (por ejemplo, `Placa_prueba`) en el campo `Project Name` y hacemos clic en **Create**.

![Ventana Create Project](img/fotos_altium/Imagen6.png){ width="600" }
*Figura 6.2.2: Configuración de nombre y ubicación del proyecto.*

Una vez creado, en el panel lateral **`Projects`** aparecerá el contenedor principal identificado con el ícono verde característico (`.PrjPcb`).

![Panel Projects](img/fotos_altium/Imagen7.png){ width="300" }
*Figura 6.2.3: Contenedor del proyecto inicializado en el panel lateral.*

### Creación del Diagrama Esquemático
Para agregar nuestra primera hoja de diseño, hacemos clic derecho sobre el nombre del proyecto en el panel lateral, pasamos el cursor sobre **`Add New to Project`** y seleccionamos **`Schematic`**.

![Añadir Esquemático](img/fotos_altium/Imagen8.png){ width="450" }
*Figura 6.2.4: Ruta para añadir un nuevo documento esquemático al proyecto.*

Al realizar esta acción, se generará una hoja en blanco y se abrirá el entorno de captura lógica. Es imperativo **guardar localmente el archivo**. Al notar que el documento tiene un ícono rojo en el panel (indicando que no está guardado), presionamos `Ctrl + S`, asignamos un nombre (`Placa_prueba.SchDoc`) y lo guardamos en nuestro directorio de trabajo.

| Guardado de Archivo | Explorador de Archivos |
| :---: | :---: |
| ![Archivo no guardado](img/fotos_altium/Imagen10.png){ width="300" } | ![Guardar archivo local](img/fotos_altium/Imagen11.png){ width="450" } |

![Lienzo Esquemático](img/fotos_altium/Imagen9.png){ width="650" }
*Figura 6.2.5: Interfaz del editor de esquemas listo para trabajar.*

---

## 6.3 Exploración de Paneles y Herramientas

Para trabajar de manera fluida, es necesario familiarizarse con la activación y el uso de los paneles de herramientas de Altium Designer.

### Paneles Laterales
En el borde derecho de la interfaz se encuentran pestañas de acceso rápido colapsadas por defecto (`Components`, `Properties`, etc.). El panel **`Components`** es la vía principal para buscar y colocar piezas desde librerías locales. 

Si por error cerramos algún panel lateral, podemos recuperarlo dirigiéndonos a la esquina inferior derecha, haciendo clic en el botón **`Panels`** y seleccionando el panel deseado.

| Panel Components | Recuperación de Paneles |
| :---: | :---: |
| ![Pestaña Components](img/fotos_altium/Imagen12.png){ width="300" } | ![Botón Panels](img/fotos_altium/Imagen13.png){ width="300" } |

### Búsqueda Avanzada: Manufacturer Part Search
A diferencia de las librerías estáticas, Altium ofrece el panel **`Manufacturer Part Search`**. Esta herramienta se conecta en tiempo real con bases de datos globales de proveedores, permitiendo buscar cualquier componente mediante su matrícula o navegando por categorías.

![Manufacturer Part Search](img/fotos_altium/Imagen14.png){ width="350" }
*Figura 6.3.1: Interfaz de búsqueda global de componentes.*

### Activación de Barras de Herramientas Superiores
Para agilizar el proceso de dibujo, debemos activar las barras de acceso rápido. Al hacer clic derecho sobre el espacio vacío en la barra superior, desplegaremos un menú contextual.

Activamos la casilla **`Wiring`** (Cableado) para mostrar las herramientas de conexión eléctrica (cables, GND, VCC). También activamos **`Schematic Standard`**, **`Formatting`** y **`Utilities`** para habilitar las opciones de dibujo gráfico, zoom y guardado rápido.

![Activación de Barras](img/fotos_altium/Imagen15.png){ width="700" }
*Figura 6.3.2: Configuración y habilitación de barras de herramientas superiores.*

---

## 6.4 Organización Visual del Esquemático

Para mantener un diseño profesional y ordenado, estructuraremos el lienzo en bloques funcionales utilizando herramientas de dibujo gráfico.

### Dibujo de Figuras Geométricas
En la barra de utilidades superior, desplegamos el menú del ícono de la regla y el lápiz. Esta herramienta nos permite dibujar formas (`Rectangle`, `Polyline`, `Ellipse`) que servirán como delimitadores visuales para distintas etapas del circuito (ej. entradas, salidas, potencia).

![Herramientas Gráficas](img/fotos_altium/Imagen16.png){ width="350" }
*Figura 6.4.1: Menú de formas geométricas y anotaciones.*

### Edición de Propiedades Visuales
Al trazar una figura y hacer doble clic sobre ella, se abrirá el panel **`Properties`**. Aquí podemos modificar el grosor de línea (`Line Size`), el color del borde y, activando la casilla `Fill Color`, asignar un color de fondo para resaltar el área.

| Trazo Inicial | Propiedades de Línea |
| :---: | :---: |
| ![Cuadro sin formato](img/fotos_altium/Imagen17.png){ width="250" } | ![Propiedades Linea](img/fotos_altium/Imagen18.png){ width="350" } |
| **Propiedades de Relleno** | **Cuadro Terminado** |
| ![Propiedades Relleno](img/fotos_altium/Imagen19.png){ width="350" } | ![Cuadro Relleno](img/fotos_altium/Imagen20.png){ width="250" } |

### Etiquetado de Bloques
Para identificar cada área, seleccionamos la herramienta de texto (ícono de la letra "A") y la colocamos dentro de nuestro bloque. En el panel `Properties` del texto, ingresamos el nombre de la sección (ej. "Entradas") y ajustamos la fuente, tamaño, color y justificación.

![Anotación de Texto](img/fotos_altium/Imagen21.png){ width="550" }
*Figura 6.4.2: Bloque funcional delimitado e identificado profesionalmente.*

---

## 6.5 Selección y Verificación de Componentes

La correcta elección de componentes es el pilar de un buen diseño. En Altium, debemos garantizar que cada símbolo esquemático posea su representación física correspondiente.

### Búsqueda de Componentes en la Librería
Abrimos el panel **`Components`**. Podemos filtrar la búsqueda desplegando la lista de categorías (ej. `Connectors`, `Diodes`) o ingresando directamente la matrícula del componente en la barra de búsqueda superior.

| Filtrado por Categoría | Búsqueda por Matrícula |
| :---: | :---: |
| ![Filtro de Categorías](img/fotos_altium/Imagen22.png){ width="300" } | ![Barra de búsqueda](img/fotos_altium/Imagen23.png){ width="300" } |

### Verificación de Huella (Footprint) y Datasheet
Al seleccionar un componente de la lista, en la sección inferior `Details` se mostrarán sus propiedades técnicas.
1.  **Modelos 3D y Huellas:** Es obligatorio verificar en la sección `Models` que el componente cuente con su símbolo, huella de PCB y diseño 3D. Si carece de huella, no se podrá maquinar.
2.  **Hojas de Datos:** En la sección `References` o `Part Choices`, encontraremos enlaces directos al `Datasheet` en formato PDF. Al hacer clic, Altium abrirá el documento técnico del fabricante.

| Verificación de Huella | Enlace a Datasheet |
| :---: | :---: |
| ![Modelos y Footprints](img/fotos_altium/Imagen24.png){ width="300" } | ![Enlaces a Referencias](img/fotos_altium/Imagen25.png){ width="300" } |

![Datasheet Tyco Electronics](img/fotos_altium/Imagen26.png){ width="500" }
*Figura 6.5.1: Hoja de datos del fabricante para consulta de distribución de pines.*

### Solución a Componentes sin Huella (SnapMagic)
Si el componente deseado no incluye una huella en las librerías predeterminadas, podemos recurrir a repositorios CAD externos como **SnapMagic Search**. Esta plataforma permite descargar gratuitamente el símbolo, huella y modelo 3D en formato nativo para integrarlo a Altium.

| Modelo 3D Ausente/Básico | Plataforma SnapMagic |
| :---: | :---: |
| ![Verificación de modelos](img/fotos_altium/Imagen27.png){ width="300" } | ![SnapMagic Search](img/fotos_altium/Imagen28.png){ width="450" } |

---

## 6.6 Emplazamiento y Ruteo Lógico

Con los componentes verificados, procedemos a armar el esquema del circuito eléctrico.

### Acomodo y Rotación
Arrastramos los componentes desde el panel al área de trabajo. Para rotar un componente $90^\circ$, lo seleccionamos con un clic y presionamos la barra espaciadora. Ubicamos estratégicamente los elementos en el lienzo.

![Acomodo de Componentes](img/fotos_altium/Imagen29.png){ width="600" }
*Figura 6.6.1: Distribución preliminar de los componentes en el lienzo.*

### Trazado de Conexiones (Wires)
Para interconectar los elementos, activamos el modo de cableado haciendo clic en el ícono **`Place Wire`** (en la barra `Wiring`) o usando el atajo `Ctrl + W`. Al acercar el cursor a la terminal de un componente, aparecerá una cruz roja indicando un nodo válido. 

| Herramienta Place Wire | Detección de Nodo (Cruz Roja) |
| :---: | :---: |
| ![Icono Wire](img/fotos_altium/Imagen30.png){ width="400" } | ![Cruce de conexión](img/fotos_altium/Imagen31.png){ width="300" } |

### Puertos de Alimentación (Power Ports)
Para conectar las referencias de energía, localizamos el ícono de Tierra en la barra de cableado. Haciendo clic derecho sobre él, desplegamos el menú completo de opciones de voltaje.

| Menú de Puertos | Opciones de Alimentación |
| :---: | :---: |
| ![Icono GND](img/fotos_altium/Imagen32.png){ width="350" } | ![Lista Power Ports](img/fotos_altium/Imagen33.png){ width="250" } |

![Circuito con Voltaje](img/fotos_altium/Imagen34.png){ width="500" }
*Figura 6.6.2: Consolidación del circuito con nodos de VCC y GND.*

---

## 6.7 Etiquetas de Red (Net Labels) y Anotación

Para evitar un exceso de cables cruzando todo el diseño, utilizaremos variables de interconexión inalámbrica.

### Implementación de Net Labels
En la barra de herramientas, hacemos clic derecho sobre el ícono de alambre y seleccionamos **`Net Label`**. Colocamos la etiqueta asegurándonos de que su punto de anclaje toque la línea del cable de destino.

| Selección de Herramienta | Edición de Nombre |
| :---: | :---: |
| ![Herramienta Net Label](img/fotos_altium/Imagen35.png){ width="300" } | ![Panel Net Name](img/fotos_altium/Imagen36.png){ width="300" } |
| **Lista de Redes Predefinidas** | **Conector Etiquetado** |
| ![Opciones Net Name](img/fotos_altium/Imagen37.png){ width="300" } | ![Conector con Nets](img/fotos_altium/Imagen38.png){ width="300" } |

![Circuito Etiquetado](img/fotos_altium/Imagen39.png){ width="600" }
*Figura 6.7.1: Circuito lógico interconectado mediante Etiquetas de Red.*

### Anotación Automática de Designadores
Al colocar componentes nuevos, Altium les asigna un signo de interrogación por defecto (R?, D?, C?). Para resolverlo, ejecutamos la herramienta de anotación automática: **`Tools > Annotation > Annotate Schematics Quietly`**.

| Menú de Anotación | Circuito Final Numerado |
| :---: | :---: |
| ![Herramienta de Anotación](img/fotos_altium/Imagen40.png){ width="350" } | ![Circuito Designado](img/fotos_altium/Imagen41.png){ width="500" } |

---

## 6.8 Exportación al Entorno PCB

Con el esquemático finalizado, procedemos a crear el documento de la placa. En el panel lateral, hacemos clic derecho sobre el proyecto (`Placa_prueba.PrjPcb`), seleccionamos **`Add New to Project`** y elegimos **`PCB`**.

![Añadir Documento PCB](img/fotos_altium/Imagen42.png){ width="450" }
*Figura 6.8.1: Ruta para generar el lienzo de ruteo físico de la tarjeta de circuito impreso.*

---

## 6.9 Transferencia del Diseño al Entorno PCB

Una vez creado el archivo de la placa (`.PcbDoc`), debemos transferir toda la información lógica (Netlist) y las huellas de los componentes desde el esquemático hacia el lienzo físico.

### Actualización del Documento PCB
Desde el editor del esquemático, nos dirigimos a la barra superior y seleccionamos **`Design > Update PCB Document Placa_prueba.PcbDoc`**. 

![Update PCB Document](img/fotos_altium_2/Imagen2.png)
*Figura 6.9.1: Herramienta de sincronización entre el esquemático y la placa.*

<br><br>

Se abrirá la ventana de Órdenes de Cambio de Ingeniería (ECO - Engineering Change Order). Aquí debemos hacer clic primero en **`Validate Changes`** (Validar cambios) para comprobar que no haya errores de librerías, y posteriormente en **`Execute Changes`** (Ejecutar cambios) para importar los componentes.

![Ventana ECO](img/fotos_altium_2/Imagen3.png)
*Figura 6.9.2: Validación y ejecución de cambios (ECO).*

<br><br>

Al cerrar la ventana, los componentes aparecerán agrupados en un recuadro de color a un costado de la zona de trabajo, interconectados por finas líneas de guía conocidas como *Ratsnest* (nido de ratas).

![Componentes Importados](img/fotos_altium_2/Imagen4.png)
*Figura 6.9.3: Componentes y huellas importados exitosamente al entorno PCB.*

---

## 6.10 Definición de la Tarjeta (Board Shape) y Origen

Antes de acomodar los componentes, es fundamental establecer las dimensiones físicas de la placa de cobre y su punto de origen coordenado.

### Área de Trabajo
Para ajustar el tamaño del lienzo oscuro (la placa de circuito impreso), seleccionamos **`Design > Board Shape > Edit Board Shape`**. Esto activará nodos en las esquinas del área oscura, permitiéndonos arrastrarlos para reducir o ampliar las dimensiones físicas de la tarjeta según las necesidades mecánicas de nuestro ensamble.

![Edit Board Shape](img/fotos_altium_2/Imagen5.png)
*Figura 6.10.1: Edición del contorno y dimensiones de la placa (Board Shape).*

<br><br>

### Definición del Origen (Zeroing)
Para que los archivos de manufactura CNC o Gerber se generen correctamente, debemos establecer un punto de origen `(X:0, Y:0)`. Nos dirigimos a **`Edit > Origin > Set`** y hacemos clic en la esquina inferior izquierda de nuestra placa delimitada.

![Definición de Origen](img/fotos_altium_2/Imagen6.png)
*Figura 6.10.2: Punto de origen anclado en la esquina inferior izquierda del Board Shape.*

---

## 6.11 Emplazamiento de Componentes y Visor 3D

El acomodo de los componentes (Placement) dicta la viabilidad del ruteo. Arrastramos individualmente las huellas hacia el interior de la placa, buscando minimizar el cruce de las líneas del Ratsnest.

![Placement 2D](img/fotos_altium_2/Imagen7.png)
*Figura 6.11.1: Distribución 2D de componentes sobre la tarjeta.*

<br><br>

### Visualización y Ajuste en 3D
Altium Designer integra un potente motor de renderizado 3D en tiempo real. Presionando la **tecla `3`**, el lienzo pasará a modo tridimensional (para regresar al modo 2D se presiona la **tecla `2`**). 

En el modo 3D podemos verificar la altura, interferencia mecánica y el aspecto real de los encapsulados.

![Vista 3D 1](img/fotos_altium_2/Imagen8.png)
*Figura 6.11.2: Vista 3D frontal del ensamble.*

<br><br>

![Vista 3D 2](img/fotos_altium_2/Imagen9.png)
*Figura 6.11.3: Inspección de interferencia y alturas de componentes.*

<br><br>

Incluso es posible seleccionar y mover componentes directamente en esta vista, presionando la barra espaciadora para rotarlos.

![Rotación 3D](img/fotos_altium_2/Imagen10.png)
*Figura 6.11.4: Ajuste de posición y rotación directamente desde el visor tridimensional.*

---

## 6.12 Configuración de Cuadrícula y Reglas de Diseño (DRC)

El diseño de una placa requiere precisión milimétrica. Para garantizar la manufactura, debemos parametrizar las reglas de diseño eléctrico y físico.

### Unidades y Cuadrícula (Grid)
En el panel `Properties` (sin tener nada seleccionado), verificamos que el sistema de unidades esté configurado correctamente (mm o mils). *(Nota: En la pestaña inferior, nos aseguramos de estar trabajando en la capa `Top Layer` para placas de una sola cara).*

![Unidades](img/fotos_altium_2/Imagen11.png)
*Figura 6.12.1: Verificación del sistema de unidades en el panel Properties.*

<br><br>

![Layer Stack](img/fotos_altium_2/Imagen15.png)
*Figura 6.12.2: Selección de la capa de trabajo principal (Top Layer).*

<br><br>

Además, presionando la tecla **`G`**, podemos ajustar la resolución de la cuadrícula de chasquido (Snap Grid) para lograr mayor precisión al mover trazos.

![Snap Grid](img/fotos_altium_2/Imagen16.png)
*Figura 6.12.3: Ajuste de resolución de la cuadrícula (Snap Grid).*

<br><br>

### Parámetros de Diseño (Design Rules)
Nos dirigimos a **`Design > Rules...`** para abrir el gestor de reglas de diseño. 

![Design Rules Menu](img/fotos_altium_2/Imagen17.png)
*Figura 6.12.4: Acceso al gestor global de reglas de diseño.*

<br><br>

![DRC Editor](img/fotos_altium_2/Imagen18.png)
*Figura 6.12.5: Interfaz del editor de reglas de diseño.*

<br><br>

1. **Clearance (Aislamiento):** En la sección `Electrical > Clearance`, establecemos la separación mínima permitida entre pistas y pads. Esto evita cortocircuitos durante el fresado o atacado químico.

![Clearance](img/fotos_altium_2/Imagen19.png)
*Figura 6.12.6: Configuración del aislamiento mínimo (Clearance).*

<br><br>

2. **Width (Ancho de Pista):** En la sección `Routing > Width`, definimos el grosor de nuestras líneas de cobre (Mínimo, Preferido y Máximo). Un grosor adecuado asegura que la pista soporte la corriente necesaria sin sobrecalentarse.

![Width](img/fotos_altium_2/Imagen20.png)
*Figura 6.12.7: Parametrización del grosor de las pistas de cobre (Width).*

<br><br>

![Aplicación de Reglas](img/fotos_altium_2/Imagen22.png)
*Figura 6.12.8: Confirmación de los valores paramétricos aplicados a la tarjeta antes de rutear.*

---

## 6.13 Ruteo Interactivo (Interactive Routing)

Con las reglas establecidas, procedemos a trazar el cableado físico de cobre. Activamos la herramienta **`Interactive Routing`** (`Ctrl + W` o ícono en la barra superior). 

Hacemos clic en un pad y guiamos la pista hacia su destino. Altium respetará automáticamente el aislamiento (Clearance) configurado, empujando o rodeando obstáculos de ser necesario.

![Ruteo 1](img/fotos_altium_2/Imagen23.png)
*Figura 6.13.1: Inicio del ruteo interactivo desde un pad.*

<br><br>

![Ruteo 2](img/fotos_altium_2/Imagen24.png)
*Figura 6.13.2: Trazado de pistas respetando ángulos de 45 grados.*

<br><br>

![Ruteo 3](img/fotos_altium_2/Imagen25.png)
*Figura 6.13.3: Circuito ruteado exitosamente respetando todos los parámetros de aislamiento.*

---

## 6.14 Plano de Masa (Polygon Pour)

Para mejorar la disipación térmica, aislar ruidos electromagnéticos y ahorrar tiempo de mecanizado, implementaremos un vertido de cobre o plano de masa.

Nos dirigimos a **`Place > Polygon Pour`**. Se activará el cursor para trazar un polígono cerrado por el borde interior de nuestra placa. 

![Polygon Pour Menu](img/fotos_altium_2/Imagen26.png)
*Figura 6.14.1: Acceso a la herramienta de vertido de polígono.*

<br><br>

Una vez cerrado el polígono, debemos seleccionarlo e ir al panel de `Properties`. En el apartado de `Net`, es obligatorio **asignarlo a la red `GND`**.

![Propiedades Polygon](img/fotos_altium_2/Imagen27.png)
*Figura 6.14.2: Asignación del polígono de cobre a la red de tierra (GND).*

<br><br>

Al presionar aplicar, el software rellenará automáticamente las áreas vacías con cobre, respetando las zonas de aislamiento térmico de los pads.

![Plano de Masa Rellenado](img/fotos_altium_2/Imagen28.png)
*Figura 6.14.3: Vista del polígono de cobre en formato de alambre.*

<br><br>

![Plano GND](img/fotos_altium_2/Imagen29.png)
*Figura 6.14.4: Renderizado final del polígono de cobre conectado a tierra en el visor PCB.*

---

## 6.15 Verificación Final (DRC) y Contorno (Keep-Out)

El último filtro de seguridad es el chequeo automatizado de reglas. Ejecutamos **`Tools > Design Rule Check`** y presionamos **`Run Design Rule Check`**. 

![Run DRC](img/fotos_altium_2/Imagen30.png)
*Figura 6.15.1: Ejecución del chequeo automatizado de reglas de diseño.*

<br><br>

El sistema emitirá un reporte detallando si existen pistas superpuestas, aislamientos violados o componentes sin conectar. Si todo está correcto, el informe mostrará cero errores.

![DRC Report](img/fotos_altium_2/Imagen31.png)
*Figura 6.15.2: Reporte oficial de DRC validando que no existen errores ni violaciones en el diseño.*

<br><br>

### Capa de Contorno (Keep-Out Layer)
Para que la máquina CNC sepa exactamente por dónde cortar físicamente la tarjeta terminada, debemos trazar un límite de restricción. Cambiamos a la capa **`Keep-Out Layer`** (pestaña inferior rosada).

![Capa Keep-Out](img/fotos_altium_2/Imagen32.png)
*Figura 6.15.3: Selección de la capa física de contorno.*

<br><br>

A continuación, trazamos una línea perimetral utilizando `Place > Keepout > Track`.

![Trazo Keep-Out](img/fotos_altium_2/Imagen33.png)
*Figura 6.15.4: Definición del perímetro de corte físico finalizado.*

---

## 6.16 Salidas de Fabricación (Gerber y NC Drill)

El paso culminante de nuestro diseño es la generación de los archivos universales de manufactura, listos para ser enviados a la fresadora CNC o a una casa fabricante de placas.

Nos dirigimos a **`File > Fabrication Outputs`** y seleccionamos **`Gerber Files`** (para las pistas, polígonos y bordes).

![Fab Outputs](img/fotos_altium_2/Imagen34.png)
*Figura 6.16.1: Menú de generación de salidas de fabricación.*

<br><br>

![Gerber Setup](img/fotos_altium_2/Imagen35.png)
*Figura 6.16.2: Configuración de la exportación de archivos fotográficos Gerber.*

<br><br>

Posteriormente, en el mismo menú, seleccionamos **`NC Drill Files`** (para las coordenadas y diámetros de perforación).

![NC Drill](img/fotos_altium_2/Imagen36.png)
*Figura 6.16.3: Configuración y generación de archivos de coordenadas de perforación NC Drill.*

<br><br>

Con los archivos Gerber exportados, nuestro diseño está oficialmente terminado y listo para producción.

![PCB Final en 3D](img/fotos_altium_2/Imagen37.png)
*Figura 6.16.4: Modelo tridimensional de la placa de circuito impreso completamente ruteada y validada en Altium Designer.*
