Audiencia
=========

Estudiantes de doctorado del Instituto de Hidrología de Llanuras, `IHLLA <https://ihlla.conicet.gov.ar/>`_, 
y de otros centros de investigación o universidades, no necesariamente argentinos, pero relacionados con Hidrología, Sensores Remotos, 
Simulación Numérica de Recursos Hídricos, Evaluación de Riesgo de Desastres Naturales o Sistemas de Alerta Temprana.  

Se impartirá en castellano, aunque gran parte de la documentación de soporte y links están en inglés. Todo el software empleado y los
accesos a recursos en internet están en abierto.

Se piensa en sesiones de 4 horas cada una, una o dos por semana, en horario de oficina,  huso UTC-3.

Objetivos
---------
Revisar conceptos básicos de Hidrología para introducirse en la modelización y explotación de datos con las técnicas más recientes, y adquirir autonomía para trabajar con:

* Imágenes satelitales en abierto trabajando con servidores en la nube: Google-Earth-Engine.

* Uso de librerías y software abierto: Python, JavaScript, R, Linux shells.

Como ejemplo práctico de integración se estudiarán los casos: 

* Inundaciones a gran escala: modelos digitales de elevación y simulaciones numéricas con el soporte de imágenes satelitales.

* Inteligencia Artificial y Machine-Learning: pronóstico de series temporales de caudal con redes neuronales LSTM.

* Casos a discutir en la propia cuenca del Azul (DACB, Del Azul Creek Basin).

Requisitos
----------
Conocimientos básicos de Hidrología y programación, aunque se dará un curso previo de inmersión a `Python <https://www.python.org/>`_ 
y `JavaScript de Google-Earth-Engine <https://developers.google.com/earth-engine/tutorials/tutorial_js_01>`_ 

Inicio y duración
-----------------
Previsiblemente a partir de Septiembre de 2023, y de un mínimo de 40 horas de duración.

Organización de las sesiones
-----------------------------

Primer día, 4h:
***************

* Teoría básica de ecuaciones de conservación en derivadas parciales: clasificación, discretización, términos fuente, condiciones contorno, estabilidad.
* Nociones básicas de programación, uso de lenguaje Python.
* Programas elementales en Python para las EDP seleccionadas, y manipulación de series temporales.


Días 2º-3º, 8h:
***************
* Introducción a GEE.
* Detección de cuerpos de agua con GEE e imágenes satelitales MSI:
 * Bases de datos globales: JRC y GFDB.
 * Indice NDWI, clasificación por valor umbral, distribución de Otsu.
 * Caso particular: reservorios.
 * Clasificadores con entrenamiento no supervisados.
 * Clasificadores con entrenamiento supervisados.
* Cruzado con MDE para calcular volúmenes de agua.


Cuarto día, 4h:
***************
* Análisis de Riesgo: Exposición && Vulnerabilidad.
* Casos prácticos:

Quinto día, 4h:
***************
* Revisiones casos de interés previamente discutidos.
* Temas avanzados:
 * Separación de dominios computacionales para GPUs.
 * Procesado de imágenes satelitales SAR.
 * Clasificadores usando redes neuronales convolucionales: U-Net.
