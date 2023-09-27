Audiencia
=========

Estudiantes de doctorado del Instituto de Hidrología de Llanuras, `IHLLA <https://ihlla.conicet.gov.ar/>`_, 
y de otros centros de investigación o universidades, no necesariamente argentinos, pero relacionados con Hidrología, Sensores Remotos, 
Simulación Numérica de Recursos Hídricos, Evaluación de Riesgo de Desastres Naturales o Sistemas de Alerta Temprana.  

Se impartirá en castellano, aunque gran parte de la documentación de soporte y links están en inglés. Todo el software empleado y los
accesos a recursos en internet están en abierto.

Se piensa en sesiones de 3 horas cada una,  dos por semana, en horario de oficina,  huso UTC-3.

Objetivos
---------
Revisar conceptos básicos de Hidrología para introducirse en la modelización y explotación de datos con las técnicas más recientes, y adquirir autonomía para trabajar con:

* Imágenes satelitales en abierto trabajando con servidores en la nube: Google-Earth-Engine.

* Uso de librerías y software abierto: Python, JavaScript, R, Linux shells.


Requisitos
----------
Conocimientos básicos de Hidrología y programación, aunque se dedicarán unas horas de inmersión a `Python <https://www.python.org/>`_ 
y `JavaScript de Google-Earth-Engine <https://developers.google.com/earth-engine/tutorials/tutorial_js_01>`_ 

Inicio y duración
-----------------
Comienza el 10 de Octubre de 2023, se imparte en sesiones de tres horas, dos por semana (Martes y Jueves), con un total de 30 horas de duración, en modalidad híbrida presencial y remota.

Docentes
---------
`Ignacio Villanueva <ivillanueva@ihlla.org.ar>`_ y `Ailé Golin <agolin@ihlla.org.ar>`_.

Sesiones primer bloque
----------------------

10 Octubre: *Python*
********************

* Presentación del curso: alcances, objetivos, estructura de cursado y trabajo en clases, condiciones de evaluación. 
* Problema de partida: inundaciones en la llanura pampeana.
* Nociones básicas de programación, uso de lenguaje *Python* para la ED de balance vertical de una laguna.
* Revisión de dimensionalidad espacial en modelización hidrológica. 
* Presentación del caso particular de `Martín Blanco <martinblanco@ihlla.org.ar>`_: procesado de datos Hidro-Meteorológicos `GFS`_.
* Manipulación de series temporales con *Python*, utilidades para cambio de formato e intervalos de tiempo.

.. _GFS: https://developers.google.com/earth-engine/datasets/catalog/NOAA_GFS0P25

.. image:: ./Pics/DJI_0484.JPG
  :width: 280
  :alt: Finca_Elissondo_Ups
  :align: left 

.. image:: ./Pics/DJI_0508.JPG
  :width: 280
  :alt: Finca_Elissondo_Mid
  :align: center


12 Octubre: *R*
***************

* Resolución del caso particular: procesado de datos Meteorológicos.
* Correlación, tendencias, estacionalidad y predicción de series temporales con *R*.



Sesiones segundo bloque
------------------------
17, 19 y 24 Octubre: *Aplicaciones UAV*, 9h
******************************************

* Uso de drones para obtener Modelos Digitales de Elevación para determinar zonas inundables. Teoría básica de Structure-From-Motion. Filtrado del Modelo Digital de Superficie.

* Software `Open-Drone-Map`_, práctica con los ejemplos: opción *fast-orthophoto* para georeferenciar en 2D un cuerpo de agua como el lago Güemes, y relevamiento 3D del puente de avenida Pellegrini sobre el Arroyo Azul.

.. _Open-Drone-Map: https://www.opendronemap.org/

* Introducción a LSPIV para medir el campo de velocidad de la superficie libre de un fluído.

* Práctica con software LSPIV `RIVeR <https://riverdischarge.blogspot.com>`_ basado en Matlab. 

* Salida de campo para comparar diversas formas de aforo: mecánico frente a sensores remotos.

Sesiones tercer bloque
----------------------
26 y 31 Octubre, 2 Noviembre: *Modelado HD-2D*, 9h
**************************************************

* Modelización Hidrodinámica 2D en escala urbana con las ecuaciones de Saint Venant y `HEC-RAS <https://www.hec.usace.army.mil/software/hec-ras/>`_, caso particular de Azul, Tesina de Maestría de Crysthian Sánchez. Tabla comparativa de las tecnologías involucradas.

* Configuración de escenarios GLOF (*Glacial Lake Outburst Flood*).


Enlaces del software de descarga y Datos compartidos
----------------------------------------------------

`Python <https://www.python.org/downloads/>`_
`GNUPLOT <http://www.gnuplot.info/download.html>`_
`R <https://cran.r-project.org/mirrors.html>`_
`Open-Drone-Map <https://www.opendronemap.org>`_
`RIVeR <https://riverdischarge.blogspot.com>`_
`HEC-RAS <https://www.hec.usace.army.mil/software/hec-ras/>`_

`DATOS `


Cuarto bloque (pospuesto a 2024): *Google-Earth-Engine*, 30h
-------------------------------------------------------------
* Introducción a Google-Earth-Engine.
* Detección de cuerpos de agua con GEE e imágenes satelitales MSI:
 * Bases de datos globales: JRC y GFDB. Barridos anuales para detectar cambios en un área de interés.
 * Indice NDWI, clasificación por valor umbral, distribución de Otsu.
 * Caso particular: reservorios.
 * Clasificadores con entrenamiento no supervisados.
 * Clasificadores con entrenamiento supervisados.
 * Cruzado con MDE para calcular volúmenes de agua.

.. image:: ./Pics/Steps_Donchyts_2023.png
  :width: 300
  :alt: Steps_World-Watch
  :align: center 

 

* Análisis de precipitación diaria en grilla de 0.05° con la misión satelital `CHIRPS`_, y con la misión `GPM-IMERG`_ de grilla 0.1° e intervalo de 30 minutos. Series temporales.

.. _CHIRPS: https://developers.google.com/earth-engine/datasets/catalog/UCSB-CHG_CHIRPS_DAILY

.. _GPM-IMERG: https://developers.google.com/earth-engine/datasets/catalog/NASA_GPM_L3_IMERG_V06 

* Seguimiento de sequías con el índice *NDVI* (Normalized Difference Vegetation Index).
