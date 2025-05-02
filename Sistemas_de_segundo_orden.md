# Apuntes Segundo Corte
### Trabajo realizado por:
- Alejandro Manrique Gonzalez
- Juan Camilo Villabón Sepúlveda
# Sistemas de segundo orden
## ¿Que es?
Un sistema de segundo orden es aquel cuya función de transferencia presenta dos polos.
Al igual que en los sistemas de primer orden, en cualquier sistema físico real, el número de ceros debe ser menor o igual al número de polos.
Por esta razón, los sistemas de segundo orden pueden tener hasta dos ceros como máximo. Estos sistemas son muy comunes en el análisis y diseño de controladores, ya que modelan muchos fenómenos naturales como vibraciones mecánicas, circuitos eléctricos RLC, o movimientos de sistemas amortiguados.

- Estructura general de una ecuación de segundo orden es:

$$ \ddot{y}(t) + a_{1}\dot{y}(t) + a_{0}y(t) = b_{0}u(t) $$

- Función de trasnferencia

$$ \frac{Y(s)}{U(s)} = \frac{b_{0}}{s^{2}+a_{1}s+a_{0}} $$

## Forma canónica

La forma canónica de un sistema de segundo orden es una manera estándar de escribir la función de transferencia, resaltando los parámetros más importantes para analizar la estabilidad y la respuesta del sistema.
Cuando se usa la forma canónica en un sistema de segundo orden, se establecen relaciones específicas entre los coeficientes del denominador y numerador de la función de transferencia.

- Estas relaciones son:

$$ a_{1} = 2ζw_{n} $$
$$ a_{0} = {w_{n}}^{2} $$
$$ b_{0} = K * {w_{n}}^{2} $$

- Se representa de la siguiente manera:

$$ G(s) = \frac{Y(s)}{U(s)} = \frac{K*{w_{n}}^{2}}{s^{2}+2𝜁{w_{n}}^{2}s+{w_{n}}^{2}} $$

Donde:

- $K$ es la ganancia estática
- $w_{n}$ es la frecuencia natural del sistema
- $ζ$ es el factor de amortiguamiento del sistema

## Factor de amortiguamiento 

El factor de amortiguamiento ζ es un parámetro clave que describe cómo responde un sistema a cambios o perturbaciones. Indica cuánto se disipa la energía en el sistema y afecta directamente la forma de la respuesta.

Dependiendo del valor de ζ, un sistema puede tener distintos tipos de comportamiento:

### 1. Sobre-amortiguado:

El sistema regresa lentamente al equilibrio sin oscilar.

$$ ζ > 1 $$

![image](https://github.com/user-attachments/assets/9e6d70f8-d6e4-4e13-a676-2fef3963eb96)

Ubicación de polos: Los polos son reales y negativos, pero están separados. El sistema no oscila, pero su respuesta a una perturbación es más lenta en comparación con el amortiguamiento crítico.

![image](https://github.com/user-attachments/assets/a5ca52e5-0f5c-4aba-93c7-b25d6cb15b00)

### 2. Críticamente amortiguado:

El sistema regresa al equilibrio lo más rápido posible sin oscilar.

$$ ζ = 1 $$

![image](https://github.com/user-attachments/assets/9a695c98-6d31-41dd-970e-dd34e4e6bd42)

Ubicación de polos: Los polos están ubicados en una posición real negativa, simétricamente, en el plano complejo. En este caso, el sistema no tiene oscilaciones y se estabiliza lo más rápido posible.

![image](https://github.com/user-attachments/assets/18a7a026-84f8-49a9-a92d-003318e26541)

### 3. Sub-amortiguado:

El sistema oscila alrededor del equilibrio antes de estabilizarse.

$$ ζ < 1 $$

![image](https://github.com/user-attachments/assets/e34d7366-27c7-4846-80a1-bfd1ae978981)

Ubicación de polos: Los polos están ubicados en el plano complejo, a una distancia 
de la parte real y de la parte imaginaria.

![image](https://github.com/user-attachments/assets/d34e2ae5-47c3-4c6d-a05f-275822fae6d9)

## Ejemplos: Que tipo de respuesta se espera para cada sistema

#### 1. $G(s) = \frac{12}{s^{2}+8s+12}$

$$ 2ζw_{n} = 8 $$

${w_{n}}^{2} = 12$ ----> $w_{n} = \sqrt{12}$

$$ \frac{8}{2\sqrt{12}} $$

Resultado = 1.15 por lo que es sobreamortiguada

#### 2. $G(s) = \frac{16}{s^{2}+8s+16}$

$$ 2ζw_{n} = 8 $$

${w_{n}}^{2} = 16$ ----> $w_{n} = \sqrt{16}$

$$ \frac{8}{2\sqrt{16}} $$

Resultado = 1 por lo que es críticamente amortiguada

#### 3. $G(s) = \frac{20}{s^{2}+8s+20}$

$$ 2ζw_{n} = 8 $$

${w_{n}}^{2} = 20$ ----> $w_{n} = \sqrt{20}$

$$ \frac{8}{2\sqrt{20}} $$

Resultado = 0.89 por lo que es subamortiguada

## Ejercicios:

####  1. Ejercicio de Sistema de Segundo Orden: Se tiene una función de transferencia de un sistema de segundo orden dada por

$$ G(s) = \frac{25}{s^2 + 6s + 25} $$

- Obtenemos:

$$ 2\zeta \omega_n = 6 $$

$$  \quad \omega_n^2 = 25 \Rightarrow \omega_n = \sqrt{25} = 5 $$

- Sustituyendo:
  
$$ 2\zeta \cdot 5 = 6 \Rightarrow \zeta = \frac{6}{10} = 0.6 $$

- Resultado:

- $\zeta = 0.6$

- $w_{n} = 5$

- Tipo de amortiguamiento: Subamortiguadao $\zeta < 1$

### 2. Ejercicio: Dada la siguiente función de transferencia:

$$ G(s) = \frac{100}{s^2 + 10s + 100} $$

- Obtenemos:

$$ 2\zeta \omega_n = 10 $$

$$ \quad \omega_n^2 = 100 \Rightarrow \omega_n = \sqrt{100} = 10 $$

- Sustituyendo:

$$ 2\zeta \cdot 10 = 10 \Rightarrow \zeta = \frac{10}{20} = 0.5 $$

- Resultados

- $\zeta = 0.5$

- $w_{n} = 10$

- Tipo de amortiguamiento: Subamortiguado $\zeta < 1$
  
## Efecto de los ceros

Los ceros en un sistema de amortiguamiento son los valores de $s$ que hacen que el numerador de la función de transferencia se haga cero. Los ceros afectan la forma de la respuesta del sistema, pero no influyen directamente en el comportamiento del sistema a largo plazo (como los polos). Sin embargo, sí modifican el comportamiento transitorio y la frecuencia de resonancia en un sistema.

- Ejemplo:

![image](https://github.com/user-attachments/assets/6243b2b6-f174-4153-a00d-e737892ef493)

## Sistemas de orden superior

Un sistema de orden superior tiene más de dos polos. Esto hace que la ecuación característica que describe al sistema sea de grado mayor a dos. Como resultado, el comportamiento del sistema involucra más modos, y la respuesta será más compleja.
Los sistemas de orden superior pueden descomponerse en sub-sistemas de primer o segundo orden. Esto significa que, aunque el sistema global sea de orden mayor, se puede analizar separadamente en modos que se comportan como sistemas de segundo orden o incluso de primer orden.

- Comportamiento de sistemas de orden superior:
  
- Polos: A medida que el orden del sistema aumenta, el número de polos también aumenta. Esto puede hacer que el sistema tenga más modos de respuesta. Dependiendo de la ubicación de estos polos, el sistema puede experimentar más oscilaciones, más retardos o un comportamiento más complejo.
  
- Ceros: Los ceros no afectan la estabilidad del sistema, pero sí modifican la respuesta transitoria. Los sistemas de orden superior pueden tener ceros que cambian las características de la salida, como el tiempo que tarda en alcanzar el valor final o el tipo de oscilación.
