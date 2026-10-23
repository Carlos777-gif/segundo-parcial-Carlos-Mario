# Práctica 1: Modelado de Mecanismo Concéntrico Articulado en SolidWorks

**Institución:** Universidad Iberoamericana Puebla (Ibero Puebla)  
**Materia:** Proyecto de Ingeniería  
**Alumno:** Carlos Mario Díaz Moscoso  
**Profesor:** Oliver Ochoa García  
**Fecha:** 18 de septiembre de 2026  

---

## 1. Introducción y Objetivo de la Clase
En esta sesión con el maestro Oliver, nos enfocamos en aprender los conceptos clave de diseño para prepararnos en la creación de piezas articuladas y con movimiento en SolidWorks. El objetivo principal fue entender cómo estructurar un mecanismo tipo *Print-in-Place* a nivel digital, logrando que una sola pieza contenga partes móviles independientes diseñadas directamente desde el croquis.

---

## 2. Guía de Materiales, Ventajas y Desventajas
Durante la clase revisamos los filamentos de uso frecuente en impresión 3D FDM, comprendiendo sus propiedades térmicas, ventajas y desventajas al momento de seleccionar el material adecuado para un proyecto:

| Material | Temp. Boquilla | Temp. Cama | Ventajas Principales / Desventajas |
| :--- | :---: | :---: | :--- |
| **PLA** | 190 - 220 °C | 50 - 60 °C | Fácil de imprimir, económico, biodegradable, sin warping. / *Desventaja:* Baja resistencia térmica (>60 °C), frágil. |
| **ABS** | 230 - 250 °C | 80 - 110 °C | Alta resistencia al impacto, buena estabilidad térmica, fácil de pulir. / *Desventaja:* Warp severo, vapores nocivos, requiere cabina cerrada. |
| **PETG** | 230 - 250 °C | 70 - 80 °C | Excelente adherencia, resistente a químicos e impactos, sin cabina. / *Desventaja:* Tiende a dejar hilos (*stringing*) y se raya fácilmente. |
| **Nylon (PA)** | 240 - 260 °C | 70 - 100 °C | Extremadamente duradero, flexible bajo alta tensión, bajo coeficiente de fricción. / *Desventaja:* Higroscópico (absorbe humedad), complejo de adherir. |
| **TPU** | 210 - 230 °C | 20 - 60 °C | Gran elasticidad, alta resistencia al desgaste, amortiguación. / *Desventaja:* Velocidad de impresión lenta, requiere extrusor directo. |

---

## 3. Puntos Clave de Diseño para Piezas Articuladas
* **Tolerancias de separación:** Se debe dejar un espacio libre adecuado entre las piezas móviles adyacentes para asegurar el juego mecánico y evitar fusiones indeseadas durante la impresión.
* **Ángulo de voladizo:** Las superficies con inclinaciones pronunciadas requieren consideraciones geométricas en los perfiles para que puedan fabricarse adecuadamente sin colapsar.
* **Orientación geométrica:** Planear la disposición de los elementos considerando cómo se comportarán las uniones y las tensiones estructurales a lo largo de las capas.
* **Estrategia de relleno (Infill):** Uso de porcentajes moderados y patrones adecuados según las necesidades mecánicas del modelo.

---

## 4. Ejercicio Práctico en SolidWorks
Como práctica principal, modelamos una pieza concéntrica articulada (tipo 'cebolla') aplicando los siguientes pasos:
1. **Uso de la Herramienta Revolución:** En SolidWorks elaboramos el croquis con el perfil de los anillos —empleando formas esféricas cóncavas y convexas— y aplicamos la operación de *Saliente/Base Revolucionado* para generar la geometría tridimensional concéntrica.
2. **Holgura específica de 0.25 mm:** En el croquis se estableció una separación exacta de 0.25 mm entre cada anillo vecino para asegurar el espacio libre necesario entre las partes móviles.
3. **Geometría de topes:** Las curvas diseñadas mediante la revolución actúan como topes mecánicos que impiden que los anillos se salgan verticalmente de su posición, permitiendo únicamente su movimiento deslizante relativo entre ellos.

---

## 5. Evidencia Visual del Proyecto

| Croquis con cotas y holgura de 0.25 mm | Modelo 3D concéntrico revolucionado |
| :---: | :---: |
| ![Croquis en SolidWorks](img/01_croquis_revolucion_cotas.png) | ![Modelo 3D](img/02_modelo_3d_concentrico.png) |
| *Definición de radios y separación de 0.25 mm en croquis* | *Geometría esférica concéntrica terminada en SolidWorks* |

---

## 6. Conclusión
En lo personal, esta práctica me sirvió muchísimo para entender cómo planear y diseñar piezas articuladas desde cero en SolidWorks. Comprender la importancia de dejar la tolerancia exacta —como los 0.25 mm en los anillos concéntricos— y usar herramientas como la revolución me hizo ver lo crucial que es anticiparse a la impresión 3D. Al final, es un proceso de ir afinando detalles para que las partes realmente se muevan sin fundirse, lo cual hace que todo cobre sentido al momento de fabricarlo.
