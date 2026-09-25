<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin-bottom: 30px;">
  <!-- Logo de tu equipo -->
  <img src="img/logo.png" alt="Logo del Equipo" width="100">
  
  <!-- Logo de KiCad actualizado a tu archivo local -->
  <img src="img/KiCad-Logo.svg.webp" alt="Logo KiCad" width="100">
</div>

# Documentación de Diseño de PCB

<!-- BARRA LATERAL FLOTANTE DE ICONOS -->
<div class="sidebar-glass">
  
  <a href="https://discord.com/invite/FANuKv8sZn" target="_blank" title="Discord Oficial de KiCad">
    <img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/636e0a6a49cf127bf92de1e2_icon_clyde_blurple_RGB.png" width="40" style="border-radius: 8px;">
  </a>
  
  <a href="https://www.kicad.org/blog/" target="_blank" title="Blog de KiCad">
    <img src="img/kicad-icon.png" width="40" style="border-radius: 8px; background: white; padding: 4px;">
  </a>
  
  <a href="https://downloadcenter.rolanddg.com/SRM-20" target="_blank" title="Descargar VPanel SRM-20">
    <img src="img/icono-monofab.jpg" width="40" style="border-radius: 8px;">
  </a>

</div>
<!-- FIN BARRA LATERAL -->

Bienvenido a la bitácora del proyecto de diseño de nuestra placa de circuito impreso (PCB). Este sitio documenta el flujo de trabajo realizado en **KiCad**.

<div align="center" style="margin-top: 20px; margin-bottom: 40px;">
  <a href="https://www.kicad.org/download/" target="_blank" class="btn-descarga">
    📥 Descargar KiCad Oficial
  </a>
</div>

## 🎬 Introducción al Entorno (Curso)

Si apenas estás comenzando, te recomendamos ver el primer episodio del curso **KiCad desde Cero** (por *Easy Learning*). En esta vista previa podrás familiarizarte con el entorno de trabajo antes de replicar nuestra documentación:

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.5); margin-bottom: 40px; margin-top: 20px;">
  <iframe style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;" src="https://www.youtube.com/embed/d3H3tfU4zBI" title="KiCad desde Cero - Entorno" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

---

## Fases del Proyecto

<div class="grid cards" markdown>

-   <img src="img/icono-esquematico.jpg" width="35" align="left" style="margin-right: 12px; border-radius: 6px;"> **[1. Esquemático](desarrollo-pcb.md)**
    
    ---
    
    Documentación del diagrama lógico, selección de componentes y cableado.
    
    [Ver documentación ➔](desarrollo-pcb.md)

-   <img src="img/icono-placa.png" width="35" align="left" style="margin-right: 12px; border-radius: 6px;"> **[2. Editor de Placas (Layout)](desarrollo-pcb.md#2-editor-de-placas-pcb-layout)**
    
    ---
    
    Distribución de huellas, ruteo físico de pistas y zonas de cobre.
    
    [Ver documentación ➔](desarrollo-pcb.md#2-editor-de-placas-pcb-layout)

-   <img src="img/icono-monofab.jpg" width="35" align="left" style="margin-right: 12px; border-radius: 6px;"> **[3. Manufactura CAM (Mods CE)](desarrollo-pcb.md#3-manufactura-cam-y-generacion-de-trayectorias-mods-ce)**
    
    ---
    
    Generación de trayectorias (G-Code/Toolpaths) para la fresadora CNC SRM-20.
    
    [Ver documentación ➔](desarrollo-pcb.md#3-manufactura-cam-y-generacion-de-trayectorias-mods-ce)

-   :material-book-open-variant: **[4. Recursos y Referencias](recursos.md)**
    
    ---
    
    Material de referencia, repositorios y guías útiles para el proyecto.
    
    [Ver recursos ➔](recursos.md)

</div>

---

## Nuestro Equipo: KiCad Squad
<p style="text-align: center; color: #888; margin-top: -10px;">Proyecto de Electrónica - IBERO Puebla</p>

<!-- Contenedor del equipo ajustado para 4 personas -->
<div style="display: flex; justify-content: center; gap: 40px; text-align: center; margin-top: 30px; flex-wrap: wrap;">
  
  <!-- Carlos -->
  <div style="width: 200px; margin-bottom: 20px;">
    <img src="img/carlos.jpg" style="width: 150px; height: 150px; object-fit: cover; border-radius: 50%; border: 4px solid #e53935; box-shadow: 0 4px 15px rgba(229, 57, 53, 0.4); margin: 0 auto;">
    <h3 style="margin-bottom: 0; margin-top: 15px; font-size: 1.1em;">Carlos Alberto Vázquez Peraza</h3>
    <p style="color: #888; font-size: 0.9em;">Ingeniería de Diseño</p>
  </div>

  <!-- Luis -->
  <div style="width: 200px; margin-bottom: 20px;">
    <img src="img/luis.jpg" style="width: 150px; height: 150px; object-fit: cover; border-radius: 50%; border: 4px solid #e53935; box-shadow: 0 4px 15px rgba(229, 57, 53, 0.4); margin: 0 auto;">
    <h3 style="margin-bottom: 0; margin-top: 15px; font-size: 1.1em;">Luis Ernesto Tamez Velásquez</h3>
    <p style="color: #888; font-size: 0.9em;">Desarrollo y Documentación</p>
  </div>

</div>
