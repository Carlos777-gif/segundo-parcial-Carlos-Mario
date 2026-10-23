# Práctica 5: Introducción al Maquinado CNC, Simulación en NC Viewer y Router Asia Robótica

**Institución:** Universidad Iberoamericana Puebla (Ibero Puebla)  
**Materia:** Proyecto de Ingeniería  
**Alumno:** Carlos Mario Díaz Moscoso  
**Profesor:** Oliver Ochoa García  
**Ubicación:** Fab Lab Puebla  
**Fecha:** 9 de octubre de 2026  

---

## 1. Introducción y el Papel del NC Viewer en el Proceso CAM
Antes de operar una máquina de control numérico computarizado (CNC) física, es indispensable contar con herramientas de validación digital que nos permitan prevenir errores graves de colisión, rotura de fresas o fallas en el material. Aquí es donde entra **NC Viewer** (`ncviewer.com`), una plataforma de simulación basada en navegador web que cumple un rol fundamental en la etapa previa al maquinado real.

El propósito principal de utilizar NC Viewer es visualizar de manera gráfica y tridimensional las trayectorias que seguirá la herramienta de corte a partir del código G generado:
* **Validación de cotas:** Comprobar que las coordenadas programadas correspondan exactamente al diseño deseado sin saltos extraños.
* **Prevención de colisiones:** Identificar si existen movimientos erróneos en los ejes o profundidades de corte excesivas ($Z$) antes de enviarlas al controlador de la máquina real.
* **Traducción cinemática:** Entender la lógica matemática detrás de los comandos numéricos y cómo el software traduce los vectores en instrucciones físicas para los motores.

<p align="center">
  <img src="img/01_interfaz_ncviewer.png" alt="Interfaz NC Viewer" width="650"/>
  <br><em>Entorno gráfico y visualizador de trayectorias en NC Viewer</em>
</p>

---

## 2. Programación y Control en G-Code

### 2.1. Sintaxis y Diccionario de Comandos G y M

| Comando / Var. | Descripción / Función | Clasificación |
| :--- | :--- | :--- |
| **G0 / G00** | Movimiento rápido de posicionamiento (sin realizar corte). | Movimiento |
| **G1 / G01** | Movimiento lineal controlado con avance de corte definido por F. | Interpolación |
| **G2 / G02** | Interpolación circular en sentido horario (CW - Clockwise). | Interpolación |
| **G3 / G03** | Interpolación circular en sentido antihorario (CCW). | Interpolación |
| **G04** | Temporización o pausa (*Dwell*) mediante parámetro P o X. | Control Temporal |
| **G17 / G18 / G19** | Selección de planos de trabajo XY, XZ y YZ respectivamente. | Selección de Plano |
| **G20 / G21** | Selección de unidades: pulgadas (G20) o milímetros (G21). | Unidades |
| **G28** | Retorno automático al punto de referencia de la máquina (Home). | Referencia |
| **G40 / G41 / G42** | Cancelación y activación de compensación de radio de herramienta. | Compensación |
| **G54 a G59** | Selección de Sistemas de Coordenadas de Trabajo (WCS). | Sistema Coord. |
| **G80 / G81 / G83** | Cancelación y ejecución de ciclos fijos de taladrado simple y profundo. | Ciclos Fijos |
| **G90 / G91** | Coordenadas absolutas (G90) o incrementales (G91). | Modo Coord. |
| **X, Y, Z** | Coordenadas espaciales de los ejes cartesianos. | Posición |
| **I, J, K** | Distancias incrementales al centro de un arco en ejes X, Y, Z. | Parám. Arco |
| **F / S / T** | Avance (*Feed Rate*), revoluciones (*Spindle Speed*) y herramienta (*Tool*). | Parám. Máquina |
| **M3 / M5** | Encendido de husillo en sentido horario y apagado de husillo. | Función Auxiliar |
| **M30** | Fin del programa, reinicio y rebobinado. | Función Auxiliar |

### 2.2. Simulación en NC Viewer (Ejercicio del Pentagrama)
Como parte del aprendizaje práctico en clase con el maestro Oliver, pusimos a prueba la lógica de coordenadas y la estructura del código G realizando la simulación de un pentagrama:

```gcode
G21
G90
G00 X50.0 Y0.0 Z5.0 F1000
G01 Z-1.0 F300
G02 X50.0 Y0.0 I-50.0 J0.0 F500
G00 X0.0 Y50.0
G01 X29.39 Y-40.45
G01 X-47.55 Y15.45
G01 X47.55 Y15.45
G01 X-29.39 Y-40.45
G01 X0.0 Y50.0
G00 Z5.0
M02
```

<p align="center">
  <img src="img/02_simulacion_pentagrama_gcode.png" alt="Simulación pentagrama en NC Viewer" width="650"/>
  <br><em>Validación de interpolación circular perimetral y trazo de estrella pentagonal en NC Viewer</em>
</p>

---

## 3. Preparación CAM en VCarve Pro y Transferencia vía USB
Para procesar el diseño vectorial y alistarlo para la máquina:
1. **Importación a VCarve Pro:** Se importó el diseño vectorial al software CAM del taller.
2. **Configuración de Material y Trayectorias:** Se definieron las dimensiones del bloque de espuma rosa, la selección de la fresa, velocidad de avance, RPM del husillo y profundidad de corte por pasada.
3. **Generación del Código G:** Se calcularon las trayectorias (*Toolpaths*) y se exportó el código con el postprocesador específico del router.
4. **Transferencia mediante USB:** El archivo de maquinado se guardó en una memoria USB para cargarla directamente en el controlador DSP del router CNC.

---

## 4. Descripción y Operación del Router CNC Asia Robótica (Shop-1325)
Para el maquinado físico en el Fab Lab Puebla utilizamos el **Router CNC Asia Robótica Shop-1325**. Es un equipo de gran formato diseñado para el fresado y corte de tableros, acrílicos y polímeros, equipado con motores de alta precisión y husillo de alta velocidad. Se utilizó espuma rosa por su baja densidad, facilidad para arranque de viruta y gran estabilidad dimensional.

<p align="center">
  <img src="img/03_router_cnc_asia_robotica_shop1325.png" alt="Router CNC Asia Robótica" width="450"/>
  <br><em>Router CNC Asia Robótica Shop-1325 en el Fab Lab Puebla</em>
</p>

---

## 5. Protocolo de Preparación y Maquinado de la Espuma Rosa
1. **Limpieza de la base:** Limpieza exhaustiva de la cama de sacrificio para evitar irregularidades en el eje Z.
2. **Fijación del material:** El bloque de espuma rosa se aseguró mediante bridas y prensas mecánicas para evitar vibraciones.
3. **Carga del archivo:** Inserción de la memoria USB en el controlador DSP de la máquina.
4. **Calibración de Ceros (WCS):** Posicionamiento de la fresa en la esquina del material para fijar el origen (X0, Y0, Z0).
5. **Ejecución y Supervisión:** Maquinado con extracción de viruta activa y monitoreo constante junto al botón de paro de emergencia (*E-stop*).

| Ajuste de Boquilla y Fresa | Calibración de Ceros WCS |
| :---: | :---: |
| ![Ajuste fresa](img/04_cambio_herramienta_boquilla.png) | ![Calibración](img/05_calibracion_ceros_wcs_espuma.png) |

### Resultado Final Maquinado:
<p align="center">
  <img src="img/06_pieza_final_cortada_espuma.png" alt="Pieza final en espuma rosa" width="450"/>
  <br><em>Acabado superficial y canales maquinados en espuma rosa con fresado de alta definición</em>
</p>

---

## 6. Conclusión
La práctica en el Fab Lab Puebla ofreció una visión integral del proceso de manufactura asistida por computadora. La simulación inicial en NC Viewer permitió dominar la sintaxis del código G y la lógica espacial de las coordenadas. Por otro lado, la transición a VCarve Pro para procesar una plantilla de internet, exportarla a una memoria USB y ejecutar el corte en la máquina Asia Robótica sobre espuma rosa, reforzó la importancia de la limpieza de base, la fijación correcta del material y la calibración precisa en el mundo real.
