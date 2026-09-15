<div style="display: flex; align-items: center; justify-content: center; gap: 20px; margin-bottom: 30px;">
  <!-- Logo de tu equipo -->
  <img src="img/logo.png" alt="Logo del Equipo" width="100">
  
  <!-- Logo de KiCad actualizado a tu archivo local -->
  <img src="img/KiCad-Logo.svg.webp" alt="Logo KiCad" width="100">
</div>

# Documentación de Diseño de PCB

<!-- BARRA LATERAL FLOTANTE DE ICONOS -->
<div style="float: right; display: flex; flex-direction: column; gap: 15px; background: #1e1e1e; padding: 12px; border-radius: 12px; margin: 0 0 20px 20px; box-shadow: 0 4px 15px rgba(0,0,0,0.5); border: 1px solid #333; z-index: 10;">
  
  <a href="https://discord.com/invite/FANuKv8sZn" target="_blank" title="Discord Oficial de KiCad">
    <!-- Ícono oficial de Discord -->
    <img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/636e0a6a49cf127bf92de1e2_icon_clyde_blurple_RGB.png" width="40" style="border-radius: 8px;">
  </a>
  
  <a href="https://www.kicad.org/blog/" target="_blank" title="Blog de KiCad">
    <img src="img/KiCad-Logo.svg.webp" width="40" style="border-radius: 8px; background: white; padding: 4px;">
  </a>
  
  <a href="https://downloadcenter.rolanddg.com/SRM-20" target="_blank" title="Descargar VPanel SRM-20">
    <img src="img/icono-monofab.png" width="40" style="border-radius: 8px;">
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

-   <img src="img/icono-esquematico.jpg" width="35" align="left" style="margin-right: 12px; border-radius: 6px;"> **[1. Esquemático](esquematico.md)**
    
    ---
    
    Documentación del diagrama lógico, selección de componentes y cableado.
    
    [Ver documentación ➔](esquematico.md)

-   <img src="img/icono-placa.png" width="35" align="left" style="margin-right: 12px; border-radius: 6px;"> **[2. Editor de Placas (Layout)](editor-placas.md)**
    
    ---
    
    Proceso de ruteo, distribución de huellas y diseño físico de la PCB.
    
    [Ver documentación ➔](editor-placas.md)

-   ⚙️ **[3. Mods CE](mods-ce.md)**
    
    ---
    
    Modificaciones aplicadas, correcciones y consideraciones técnicas.
    
    [Ver documentación ➔](mods-ce.md)

-   📚 **[4. Recursos](recursos.md)**
    
    ---
    
    Material de referencia, hojas de datos y guías para el manejo de KiCad.
    
    [Ver documentación ➔](recursos.md)

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

  <!-- Juan Manuel -->
  <div style="width: 200px; margin-bottom: 20px;">
    <img src="img/juan.jpg" style="width: 150px; height: 150px; object-fit: cover; border-radius: 50%; border: 4px solid #e53935; box-shadow: 0 4px 15px rgba(229, 57, 53, 0.4); margin: 0 auto;">
    <h3 style="margin-bottom: 0; margin-top: 15px; font-size: 1.1em;">Juan Manuel Gaona Serrano</h3>
    <p style="color: #888; font-size: 0.9em;">Integración y Pruebas</p>
  </div>

  <!-- Brandon -->
  <div style="width: 200px; margin-bottom: 20px;">
    <img src="img/brandon.jpg" style="width: 150px; height: 150px; object-fit: cover; border-radius: 50%; border: 4px solid #e53935; box-shadow: 0 4px 15px rgba(229, 57, 53, 0.4); margin: 0 auto;">
    <h3 style="margin-bottom: 0; margin-top: 15px; font-size: 1.1em;">Brandon Saúl Ruvalcaba Pérez</h3>
    <p style="color: #888; font-size: 0.9em;">Control de Calidad</p>
  </div>

</div>
