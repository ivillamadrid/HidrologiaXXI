Computación I
=============

Ejemplo de inicio: balance en la vertical
-----------------------------------------
En un lago aproximado groseramente como circular y con un lecho parabólico, donde la relación entre la profundidad *h* y el radio *r* es :math:`h=cr^2`, la conservación de la masa se expresa  como:

.. math::

  Q-E-Inf=\frac{dV}{dt}=\frac{\pi r^2 dh}{dt}=\frac{\pi h}{c}\frac{dh}{dt}

Permite calcular la evolución de la profundidad en función de los términos fuente: caudal entrada *Q*, evaporación *E* y la infiltración *Inf*, como veremos.

Ecuaciones en Derivadas Parciales (PDEs) 1D
-------------------------------------------
Si añadimos la dependencia espacial o un dominio de cálculo en el eje X, distinguiremos:

* PDE Elíptica:

.. math::

  \frac{\partial }{\partial x} \left(K \frac{\partial T }{\partial x}\right)=0

* PDE Parabólica:

.. math::

  \frac{\partial C}{\partial t}= D\left( \frac{\partial^2 C }{\partial x^2}\right)


* PDE Hiperbólica:

.. math::

  \frac{\partial (\rho T)}{\partial t}+\frac{\partial (\rho U_xT) }{\partial x}=0


Ejemplos 2D de Onda-Difusiva (heat, GW, HD-SWE, SAR backscatter)
----------------------------------------------------------------
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

En 2D, es:

.. math::

 \boxed{ \frac{\partial h}{\partial t}=\frac{\partial }{\partial x}  \left( K_x \frac{\partial h}{\partial x} \right) + \frac{\partial }{\partial y}  \left( K_y \frac{\partial h}{\partial y} \right) \pm q_{src}}

La hidrodinámica para aguas superficiales poco profundas (HD-SWE), usa el caudal:

.. math::

 q_x =  \frac{(h_f)^{5/3}}{n} \left(\frac{\partial(Z_b+h)}{\partial x}\right)^{1/2}  

O también empleada en el filtrado de la intensidad *I* de imágenes satelitales SAR, en este caso con anisotropía en el coeficiente c(x, y):

.. math::

  \frac{\partial I}{\partial t}= \frac{\partial}{\partial x} \left(c \frac{\partial I}{\partial x}\right) + \frac{\partial}{\partial y} \left(c \frac{\partial I}{\partial y}\right) 

Esquemas en diferencias finitas para las PDEs
---------------------------------------------

Diferentes esquemas de discretización de las ecuaciones anteriores, parten de aproximaciones tipo:

.. math::

  \frac{\partial f}{\partial x} \approx \frac{f(x_{i+1})-f(x_i)}{x_{i+1} - x_i} \equiv \frac{f_{i+1}-f_i}{\Delta x}

  \frac{\partial u}{\partial t} \approx \frac{u^{n+1}-u^n}{\Delta t}

que permiten su resolución, por ejemplo el caso más sencillo de balance puntual, escrito como: 

.. math:: \frac{d U}{d t} = H(U, t)

se resuelve, en discretización temporal explícita de Euler, como 

.. math:: U^{n+1}=U^{n}+\Delta t H(U^n, t^n) 

de forma implícita, como

.. math:: U^{n+1}=U^{n}+\Delta t H(U^{n+1}, t^{n+1})

O la combinación semi-implícita:

.. math:: U^{n+1}=U^{n}+ \Delta t[ (1-\Theta) H(U^n, t^n) + \Theta  H(U^{n+1}, t^{n+1})]

Con el parámetro de peso :math:`0 \le \Theta \le 1`.

Para resolver las PDE, especialmente las de primer orden hiperbólicas, 

.. math:: \frac{\partial U}{\partial t} + \frac{\partial F(U)}{\partial x}=0

se requiere relacionar cuidadosamente los ratios entre :math:`\Delta x` y :math:`\Delta t`, ello se deduce al transformar la PDE a 
notación característica, con :math:`\Lambda=\partial F / \partial U`:

.. math:: \frac{\partial U}{\partial t} + \Lambda \frac{\partial U}{\partial x}=0

de la que se deduce una condición necesaria de convergencia, que aplicando el teorema de Lax, si la discretización es consistente, afirma que la condición necesaria y suficiente de convergencia, es  la estabilidad, que se logra mediante:

.. math:: \frac{\Delta t \lambda_{max}}{\Delta x} \le CFL

o equivalentemente:

.. math:: \Delta t \le CFL \frac{\Delta x}{\lambda_{max}}

Donde *CFL* es el coeficiente originalmente definido por Courant, Friedrichs y Lewy en 1928, y :math:`\lambda_{max}` el autovalor máximo de la matriz 
:math:`\Lambda`.

De modo que en discretización explícita :math:`CFL \le 1` y en implícita se relaja permitiendo :math:`CFL \gt 1`.

La intepretación es que en el esquema explícito el paso temporal :math:`\Delta t` ha de ser menor que el tiempo que le cuesta a la onda más rápida trasladarse en una celda de tamaño :math:`\Delta x`, porque el valor de :math:`U^{n+1}_i`,
se define a través de los valores :math:`(U_{i-1}^n, U_{i}^n , U_{i+1}^n)`. En la discretización implícita el valor de :math:`U^{n+1}_i`,
se define a través de los valores :math:`(U_{i-k}^n, ..., U_{i-1}^n, U_{i}^n , U_{i+1}^n, ..., U_{i+k}^n)` y :math:`(U_{i-k}^{n+1}, ..., U_{i-1}^{n+1}, U_{i}^{n+1} , U_{i+1}^{n+1}, ..., U_{i+k}^{n+1})`, que es una relación más compleja algebraicamente, y se resuelve por medio de iteraciones, pero en teoría es incondicionalmente estable. 

En la práctica, al usar discretización implícita con *CFL* altos, se añade difusión numérica o viscosidad artificial que atenúa las ondas, y se pierde precisión, por lo que
es necesario encontrar un *CFL* de compromiso entre celeridad y precisión, siguiendo a Cunge, 1995.

Ejemplo de discretización explícita para la ecuación de difusión 1D:
********************************************************************
Se resolverá usando el esquema o plantilla (del inglés *stencil*):

.. math:: C_i^{n+1}=C_i^n + \lambda \left( C_{i-1}^n -2C_i^n + C_{i+1}^n \right)

Con :math:`\lambda=D\frac{\Delta t}{\Delta x^2}`


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


