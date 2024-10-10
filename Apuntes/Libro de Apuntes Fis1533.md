Tags: [[PUC]], [[Apuntes]]
## Resumen
	Créditos a las ayudantías del curso hechas por Vicente Sepúlveda y Sebastián Carmona. También algunas definiciones/ejercicios fueron sacados del libro "Introduction to Electrodynamics" de David J. Griffiths y claramente a mis apuntes personales de clases. - Rafa L

### Fuerza y campo eléctrico
#### Distribución discreta
Dos cuerpos con cargas $q_{1}$ y $q_{2}$, separados una distancia *r* sienten una fuerza que es proporcional al producto de las cargas e inversamente proporcional al cuadrado de la distancia. Esta fuera se llama **fuerza eléctrica** $F_{e}$ y su magnitud está dada por:

$$F_{e} = \frac{|q_{1}||q_{1}|}{r^2}$$

Esta fuerza será atractiva para cargas de distinto signo, y repulsiva para cargas de igual signo. Vectorialmente, es posible encontrar también la dirección de la fuerza que el cuerpo 1 ejerce sobre el cuerpo 2, de la forma:

$$\vec{F_{12}} = k_{e}\frac{q_1*q_2}{r{^2}_{12}}\hat{r} \ , \ r_{12} = |\vec{r_2}-\vec{r_1}|\ \& \ \hat{r_{12}}=\frac{\vec{r_2}-\vec{r_1}}{|\vec{r_2}-\vec{r_1}|}$$

Esta formula que permite encontrar la fuerza eléctrica se llama la *Ley de Coulomb.*
El campo eléctrico $\vec{E}$ se define como la fuerza por unidad de carga que se ejerce sobre una carga de prueba en cualquier punto (siempre que la carga de prueba sea suficientemente pequeña para no perturbar a la carga fuente), y matemáticamente corresponde a:

$$\vec{E} = \frac{1}{q_2}\vec{F} = k_e\frac{q_1}{|\hat{r}_{21}|^3}\hat{r}_{21}$$

Esto permite estudiar el efecto que una carga fuente puede tener sobre cualquier otra, independiente de la carga de esta. Por último, una propiedad muy útil, tanto de la fuerza eléctrica como del campo eléctrico, es que para un conjunto de cargas discretas aplica el principio de superposición, esto es, que el campo o fuerza neta en un punto es igual la suma de todos los campos o fuerzas generados por cada una de las cargas en el espacio, matemáticamente:

$$\vec{F}_{neto}=\sum_{i=1}^{n}\vec{F}_i\ \& \ \vec{E}_{neto}=\sum_{i=1}^{n}\vec{E}_i$$

#### Distribución continua

Dada una distribución continua de cargas, se define el campo eléctrico como una distribución continua de cargas como:

$$E(\vec{r}) = \frac{1}{4\pi\epsilon_{0}} \int \frac{1}{(|\vec{r}-\vec{r'}|)^2}\hat{R}dq = \frac{1}{4\pi\epsilon_{0}} \int \frac{1}{(|\vec{r}-\vec{r'}|)^3}(|\vec{r}-\vec{r'}|)dq$$

Donde el diferencial de carga 'dq' dependerá del problema planteado:
- Distribución de carga lineal: dq = $\lambda$dx'
-  Distribución de carga superficial: dq = $\sigma$dA'
- Distribución de carga volumétrica: dq = $\sigma$dV'
En cada caso se tendrá que resolver una integral simple, doble o triple respectivamente.

#### Flujo eléctrico

Medida de "cuanto campo eléctrico" pasa a través de una superficie. Se calcula de la forma:

$$\phi_{E} = \int\int_{S}\vec{E}\cdot d\hat{S}$$

Si la superficie es plana:
$\phi_{E} = \vec{E}\cdot A$ o $\phi_{E} = \vec{E}A\cos{\theta}$, con $\theta$ el ángulo entre el campo y el vector normal a la superficie.

**Ley de Gauss**
Si la superficie es cerrada (o gaussiana), el cálculo anterior el flujo se reduce a la carga encerrada por la superficie, o sea:

$$\phi_{E} = \oint\oint_{S}\vec{E}\cdot d\hat{S} = \frac{Q_{encerrada}}{\epsilon_{0}}$$

*Recordatorio teorema de divergencia:*

La integral de superficie de un campo vectorial sobre una superficie cerrada es igual a la integral de volumen de la divergencia del campo sobre el volumen al interior de la superficie.

$$\oint\oint_{S}\vec{F}\cdot \vec{n}dS = \int\int\int_{V}div\vec{F}dV$$
Podemos reescribir la ley de Gauss entonces como:
$${\epsilon_{0}}\oint\oint_{S}\vec{E}\cdot d\hat{S} =Q$$
$$Q = \int\int\int_{R}div\vec{E}\cdot{\epsilon_{0}}\cdot dV \ , \ div\vec{E}\cdot\epsilon_{0} = \rho \ (densidad\ de\ carga).$$
O bien en su forma diferencial:
$$\vec{\nabla}\cdot\vec{E} = \frac{\rho}{\epsilon_0}$$
Dando como resultado:
$$Q = \int\int\int_R \rho dV$$

### Conductores

No existe el conductor ideal, pero nosotros podemos suponer que para el curso, los conductores cumplen las siguientes propiedades electrostáticas:

- E = 0 **dentro del conductor**
- $\rho$ = 0 **dentro del conductor**: Si el volumen posee una cavidad, la densidad de carga puede ser distinta de 0 en esa región vacía
- E es **perpendicular** justo fuera de la superficie del conductor
- En la frontera: $$\frac{\sigma}{\epsilon_0}= E \ ,\ con\ E\ =\ Campo\ electrico\ fuera\ del\ conductor$$
### Potencial Eléctrico

La fuerza eléctrica es conservativa, esto quiere decir que la integral de linea sobre un camino cerrado es nula. Lo miso se puede decir para la integral sobre un camino cerrado en el campo eléctrico:
$$\oint\vec{F}\cdot d\vec{l} =q\oint\vec{E}\cdot d\vec{l} = 0$$
Con esto se puede mostrar que $\nabla \times \vec{E} = 0$. Debido a este resultado definimos $V(\vec{r})$: $$V(\vec{r}) = -\int_\mathcal{O}^r \vec{E}\cdot{d\vec{l}}\text{ , con}\ \mathcal{O}\ \text{el punto de referencia}$$
$V(\vec{r})$ = Potencial eléctrico, es nulo en $\infty$. Podemos calcular el campo eléctrico como: $$\vec{E} = -\nabla V$$ Se desprende de la ecuación: $$V(\vec{r}) = \frac{1}{4\pi\epsilon_0}\int{\frac{dq}{|\vec{r}-\vec{r'}|}}$$
El potencial está asociado al trabajo eléctrico necesario para mover una carga q bajo la fuerza de un campo eléctrico E: $$W = -\int_{\vec{r_1}}^\vec{r_2}Fd\vec{l} = -q\int_{\vec{r_1}}^\vec{r_2}\vec{E}d\vec{l} =-q(V_2 - V_1)$$ $$U = \frac{\epsilon_0}{2}\int_\text{todo el espacio}|\vec{E}|^2dV = \frac{1}{2}\int Vdq$$
Donde U es la energía y el dV de la primera integral se refiere al Volumen, el V de la segunda al potencial.

### Capacitores

Consideremos dos conductores de cargas opuestas pero de igual magnitud. Ya que el campo es constante sobre los conductores se puede considerar la diferencia de potencial entre ambos: $V_{+} - V_{-} = -\int_{-}^{+}\vec{E}\cdot d\vec{l}$. Aunque no se sepa la distribución de carga, sabemos que el campo es proporcional a Q, por lo tanto V también lo es. Esta razón de proporcionalidad se llama capacitancia y se define como C: $$C = \frac{Q}{V}$$
El trabajo necesario para cargar un condensador es:
$$W = \int_{0}^{Q}\frac{q}{C}dq = \frac{Q^2}{2C}$$
Y si definimos la energía potencial de un condensador como 0, entonces el trabajo es igual a la energía potencial U del condensador con carga:
$$U = \frac{Q^2}{2C} = \frac{CV^2}{2} = \frac{QV}{2}$$
En un circuito podemos conectar condensadores en serie o en paralelo:

- Capacitor en serie: $$\frac{1}{C_{eq}} = \frac{1}{C_{1}} + \frac{1}{C_{2}}$$
- Capacitor en paralelo: $$C_{eq} = C_{1} + C_{2}$$
---
