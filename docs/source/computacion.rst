Computación I
=============

Ecuaciones en Derivadas Parciales (PDEs) 1D
-------------------------------------------

* PDE Elíptica:

.. math::

  \frac{\partial }{\partial x} \left(K \frac{\partial T }{\partial x}\right)=0

* PDE Parabólica:

.. math::

  \frac{\partial T}{\partial t}= K\left( \frac{\partial^2 T }{\partial x^2}\right)


* PDE Hiperbólica:

.. math::

  \frac{\partial (\rho T)}{\partial t}+\frac{\partial (\rho U_xT) }{\partial x}=0

Ejemplo de balance en la vertical
---------------------------------

Ejemplo de la Onda-Difusiva (heat, GW, HD-SWE, SAR backscatter) 2D
------------------------------------------------------------------
Partiendo de la formulación de la conservación de la masa para la especie *C* en un volumen de control:

.. math::

  \frac{\partial C}{\partial t}+ \frac{\partial F_x}{\partial x}+ \frac{\partial F_y}{\partial y}+ \frac{\partial F_z}{\partial z}=0

En caso de que el flujo :math:`F_x` se exprese como :math:`F_x=-D\frac{\partial C}{\partial x}`  (ley de Fick),
y el coeficiente de difusión :math:`D` sea uniforme en x, y análogamente en las coordenadas (y, z), isótropo, se tiene:

.. math::

  \frac{\partial C}{\partial t}= D \left(\frac{\partial^2 C}{\partial x^2}+ \frac{\partial^2 C}{\partial y^2}+ \frac{\partial^2 C}{\partial z^2}\right)

Ecuación de difusión o de propagación del calor (heat), se estudiarán ejemplos básicos para comprender el uso de términos fuente y las condiciones de contorno,
y se extenderá a otros casos más complejos como la ecuación de difusión para aguas subterráneas (GW), usando la ley de Darcy: 

.. math::

  \frac{\partial F_x}{\partial x} \equiv q_x = -K  \frac{\partial h}{\partial x}

y la hidrodinámica para aguas superficiales poco profundas (HD-SWE), usando el caudal:

.. math::

 q_x =  \frac{(h_f)^{5/3}}{n} \left(\frac{\partial(Z_b+h)}{\partial x}\right)^{1/2}  

O también empleada en el filtrado de la intensidad *I* de imágenes satelitales SAR, en este caso con anisotropía en el coeficiente c(x, y):

.. math::

  \frac{\partial I}{\partial t}= \frac{\partial}{\partial x} \left(c \frac{\partial I}{\partial x}\right) + \frac{\partial}{\partial y} \left(c \frac{\partial I}{\partial y}\right) 

Computación II
==============

Aforo no intrusivo mediante LSPIV con `RIVeR <https://riverdischarge.blogspot.com>`_
-------------------------------------------------------------------------------------

Obtención de Modelos Digitales de Elevación con UAVs
----------------------------------------------------


Modelos enfocados a los datos (Data-Driven) y aprendizaje con NNs: pronóstico de series temporales con LSTM
-----------------------------------------------------------------------------------------------------------

Modelos y contribuciones de los propios alumnos
-----------------------------------------------


