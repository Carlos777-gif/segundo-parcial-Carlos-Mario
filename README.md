# Práctica 2: Ensambles en SolidWorks y Corte Láser (Avión a Escala en MDF)

**Institución:** Universidad Iberoamericana Puebla (Ibero Puebla)  
**Materia:** Proyecto de Ingeniería  
**Alumno:** Carlos Mario Díaz Moscoso  
**Profesor:** Oliver Ochoa García  
**Fecha:** 24 de septiembre de 2026  

---

## 1. Introducción y Fundamentos Técnicos
En esta sesión trabajamos la integración entre el diseño paramétrico en SolidWorks y la manufactura digital mediante corte láser CNC. Al diseñar piezas que se construyen a partir de láminas planas ensambladas por presión (*press-fit*), es fundamental considerar los parámetros físicos del proceso desde la etapa inicial del dibujo:

* **Kerf (Ancho de sangría):** Representa el espesor de material que el haz láser vaporiza o remueve al seguir la trayectoria de corte. Si no se contempla este margen en las cotas, las ranuras quedan más anchas de lo planificado y los dientes de ensamble más delgados, provocando que la estructura quede floja.
* **Tolerancias dimensionales en MDF:** El material base utilizado para el prototipo fue MDF. Dado que las láminas de este material presentan ligeras variaciones de espesor, fue necesario calcular y aplicar tolerancias especializadas en las uniones para lograr que cada pieza embonara a presión de forma firme.

---

## 2. Clasificación de Materiales en Corte Láser
* **Materiales Permitidos:** MDF, madera triplay, papel, cartón, acrílico, fieltro, telas sintéticas/algodón y cuero natural.
* **Materiales Estrictamente Prohibidos:** PVC, vinil y cuerina artificial (liberan gas cloro altamente corrosivo y tóxico), Policarbonato/Lexan (se quema, absorbe mal la luz y genera demasiado humo), ABS (libera vapores de cianuro), HDPE y espuma de poliestireno/unicel (riesgo extremo de incendio e inflamación rápida).

---

## 3. Desarrollo del Proyecto: Avión Escala en MDF

### 3.1. Proceso de Adaptación y Rediseño
Para el desarrollo de mi entregable individual elegí fabricar un modelo de avión. El proceso comenzó tomando como base una plantilla que fui calcando para generar el perfil de las piezas. Sin embargo, el diseño original resultaba ser bastante complejo y no contaba aún con los conocimientos necesarios para llevar a cabo ciertos grabados o partes muy elaboradas que incluía. Por esta razón, tomé la decisión de modificar bastante el diseño original, simplificando la pieza y enfocándome en ajustar los puntos clave de ensamble para que fuera completamente funcional en MDF.

<p align="center">
  <img src="img/01_modelo_avion_solidworks.png" alt="Modelo 3D del avión en SolidWorks" width="600"/>
  <br><em>Modelo tridimensional del avión y ensamble de piezas planas en SolidWorks</em>
</p>

### 3.2. Preparación de Archivos (.DXF) y Anidado (Nesting)
Una vez definidas las formas y estructuras de las piezas:
1. **Generación de vistas planas:** Se crearon las proyecciones a escala real 1:1 dentro del módulo de dibujo de SolidWorks.
2. **Exportación a .DXF:** Cada pieza se guardó en formato `.DXF` (*Drawing Exchange Format*) para su lectura en el software de la máquina láser.
3. **Anidado (Nesting):** En el software de corte se acomodaron todas las piezas optimizando el área de la lámina de MDF para minimizar desperdicios.

<p align="center">
  <img src="img/02_distribucion_piezas_dxf.png" alt="Distribución de piezas en DXF" width="550"/>
  <br><em>Distribución de las piezas vectoriales en formato .DXF para corte láser</em>
</p>

### 3.3. Manufactura y Proceso de Corte Láser
El proceso de corte contó en un inicio con la guía y supervisión directa del profesor Oliver, quien nos ayudó al momento de calibrar y mandar a cortar las piezas. No obstante, al presentarse desajustes en las holguras en el primer ensamblado, acudí por mi cuenta al área de corte para recalibrar cotas, ajustar tolerancias de corte y ejecutar el proceso de forma independiente.

---

## 4. Galería del Prototipo Final

<p align="center">
  <img src="img/03_prototipo_avion_mdf_ensamblado.png" alt="Avión de MDF ensamblado" width="500"/>
  <br><em>Prototipo terminado: Avión a escala de MDF ensamblado a presión (Press-Fit)</em>
</p>

---

## 5. Conclusión
Esta práctica fue un trabajo bastante retador por mi parte y la verdad le puse mucho esfuerzo para que saliera bien. Adaptar un diseño complejo a mis conocimientos actuales, corregir los problemas de tolerancia específicos para el MDF y exportar los planos a formato `.DXF` me dejó un gran aprendizaje. Además, haber solucionado los detalles por mi cuenta e ir a cortar las piezas de forma independiente me dio mucha confianza para usar la cortadora láser en proyectos futuros.
