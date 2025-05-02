# Estabilidad

## 1.¿Qué es la estabilidad?

La estabilidad es una propiedad fundamental que indica si un sistema de control se mantiene controlado o responde de manera predecible ante una perturbación o un cambio en la entrada.
Un sistema es estable si, ante cualquier entrada acotada (limitada), su salida también permanece acotada y, además, si no hay entrada, el sistema tiende a volver a un estado de equilibrio.

### 1.1.Clasificación de estabilidad

  1. Estable: La salida se mantiene limitada y tiende a un valor fijo con el tiempo.
  2. Inestable: La salida crece sin límite ante una pequeña perturbación.
  3. Marginalmente estable: La salida ni crece sin límite ni se reduce a cero, sino que oscila permanentemente (como en un sistema no amortiguado).

## 2.Teorema del valor final

Es una ecuacion bastante util en el analisis de sistemas y en la teoria dde control, donde nos indica cual es el valor final en el estado estacionario del sistema.

Cuando un sistema dinamico que se encuentra representado por nuna ecucion diferencial, llega al estado estacionario cuando el tiempo va para infinito, quiere decir qur los cambios en el sistema se vuelven nulos.

$$\lim_{s \to 0} \left[ sF(s) - f(0) \right]$$
$$\lim_{t \to \infty }[f(t)]$$

Una condicion es que el sistema debe ser estable. Si el sistema no es estable, el teorema del valor final no es estable

### 2.2.Analisis de estabilidad por el teorema de valor final

El análisis de estabilidad por el teorema del valor final consiste en determinar el comportamiento de una señal del sistema (usualmente la salida) cuando el tiempo tiende a infinito, utilizando su transformada de Laplace. Este análisis permite estimar si el sistema tiende a un valor constante (estable), diverge (inestable) o presenta oscilaciones sostenidas (marginalmente estable).

Para la entrada:

$$\lim_{s \to 0} s \cdot \frac{A}{s} = A$$

En cuanto la salida de este es multiplicado por la entrada y se tambien se le aplica el limite.


## 💡1.Ejemplo 1
$$ T(s) = \frac{5}{s^{2}+2s+5} $$

$$ \lim_{t \to \infty} y(t) = \lim_{s \to 0} s \cdot \frac{5}{s(s^2 + 2s + 5)} = \lim_{s \to 0} \frac{5}{s^2 + 2s + 5} = \frac{5}{5} = 1 $$

- Resultado:

El sistema es estable y su salida final es 1

## 3.Análisis de estabilidad por ubicación de polos

El análisis de estabilidad por ubicación de polos es un método fundamental en teoría de control que permite determinar la estabilidad de un sistema dinámico lineal observando la localización de los polos de su función de transferencia en el plano complejo $s$ (plano de Laplace).

- Criterios de estbilidad

- Sistema estable: Todos los polos están en el semiplano izquierdo del plano $s$ (parte real negativa). Esto implica que la respuesta natural del sistema se atenúa con el tiempo.

- Sistema inestable: Uno o más polos están en el semiplano derecho (parte real positiva). La respuesta del sistema crecerá sin límite.

- Sistema marginalmente estable: Polos en el eje imaginario (parte real igual a cero) y no repetidos. El sistema puede oscilar indefinidamente sin converger ni divergir.

- Sistema inestable (también): Polos repetidos en el eje imaginario también conducen a inestabilidad, aunque no estén en el semiplano derecho.

## 💡2. Ejemplo 2

$$ \frac{10}{s^{2}+4s+5} $$

$$ s = \frac{-4+-\sqrt{16 - 20}}{2} = -2+-j $$

- Resultado:

- El sistema es estable

## 4.Respuesta al escalón dependiendo ubicación de polos

![image](https://github.com/user-attachments/assets/adb5984d-146a-4302-87e4-c6b5cac1dae2)

Figura 1: Respuesta del sistema segun la ubicacion de los polos

## 5.Criterio de estabilidad

El criterio de estabilidad permite determinar si un sistema dinámico tiende a un estado constante ante una entrada acotada, o si su salida se vuelve inestable.
Existen varios métodos formales para analizar la estabilidad de un sistema, según el dominio en el que se trabaje.

1. Ubicación de polos
2. Criterio de Routh Hurwitz
3. Lugar de las raíces
4. Respuesta temporal
5. Teorema del valor final

## 6.Criterio de Routh Hurwitz

El criterio de Routh-Hurwitz es un método algebraico utilizado en el análisis de sistemas lineales para determinar la estabilidad de un sistema sin necesidad de calcular explícitamente las raíces del polinomio característico.

- Polinomio

$$ a_{0}s^{n} + a_{1}s^{n-1} + ... + a_{n-1}s + a_{n} = 0 $$

### 6.1Condicion para estabilidad absoluta

Para que un sistema sea estable, todas las raices del polimonio caracteristico deben tener parte negativa. Y todos los elementos de la primera columna de la tabla de Routh tienen el mismo signo (y ninguno es cero).

### 6.2¿Como se aplica?

1. Se forma la tabla de Routh, que es una especie de matriz organizada por filas que representa el polimonio.

2. A partir de los coeficientes del polimonio, se construye las filas sucesivas.

3. Se revisa la primera columna: Si todos los signos son positivos (o todos son negativos), es sistema es estabale. Si hay cambio de signo, hay raices en el simeplano derecho , lo que indica inestabilidad. 

![image](https://github.com/user-attachments/assets/5aa01a3f-131d-4d2a-957b-f127762fed75)

Figura 2: Cuadro de criterio de Routh Hurwizz

- Calculos

![image](https://github.com/user-attachments/assets/f6c28123-1732-4c36-93bc-99613aabd17f)

Figura 3: Como completar el cuadro de criterio de Routh Hurwizz

$$ b_{1} = \frac{a_{1}a_{2} - a_{0}a_{3}}{a_{1}} $$

$$ b_{2} = \frac{a_{1}a_{4} - a_{0}a_{5}}{a_{1}} $$

$$ c_{1} = \frac{b_{1}a_{3} - a_{0}b_{2}}{b_{1}} $$

$$ c_{2} = \frac{b_{1}a_{5} - a_{1}b_{3}}{b_{1}} $$

# Ejercecios
## 📚 1. Ejercicio

$$ P(s) = s^{3} + 2s^{2} + 3s + 4 $$

| Fila  | Coeficientes                            |   |
| ----- | --------------------------------------- | - |
| $s^3$ | 1                                       | 3 |
| $s^2$ | 2                                       | 4 |
| $s^1$ | $\frac{(2 \cdot 3 - 1 \cdot 4)}{2} = 1$ | 0 |
| $s^0$ | 4                                       |   |



- Resultado

1, 2, 1, 4 Todos son positivos = Sistemas estable

## 📚 2. Ejercicio

$$ P(s) = s^{4} + 2s^{3} + 3s^{2} + 4s + 5 $$

- Construcción de la tabla
  
| Fila  | Coeficientes |   |   |
| ----- | ------------ | - | - |
| $s^4$ | 1            | 3 | 5 |
| $s^3$ | 2            | 4 | 0 |



- Calcular tercera fila

$$ S_{3.1} = \frac{2 * 3 - 1 * 4}{2} = 1 $$

$$ S_{3.2} = \frac{2 * 5 - 1 * 0}{2} = 5 $$


| Fila  | Coeficientes |   |   |
| ----- | ------------ | - | - |
| $s^4$ | 1            | 3 | 5 |
| $s^3$ | 2            | 4 | 0 |
| $s^2$ | 1            | 5 | 0 |



- Calcular cuarta fila

| Fila  | Coeficientes |   |   |
| ----- | ------------ | - | - |
| $s^4$ | 1            | 3 | 5 |
| $s^3$ | 2            | 4 | 0 |
| $s^2$ | 1            | 5 | 0 |
| $s^1$ | -6           | 0 | 0 |



- Calcualar última fila

| Fila  | Coeficientes |   |   |
| ----- | ------------ | - | - |
| $s^4$ | 1            | 3 | 5 |
| $s^3$ | 2            | 4 | 0 |
| $s^2$ | 1            | 5 | 0 |
| $s^1$ | -6           | 0 | 0 |
| $s^0$ | 5            | 0 | 0 |



- Resultado

1, 2, 1, -6, 5 Hay un cambio de signo por lo que el sistema es = Inestable

## 7.Diseño de control para que se estable 

![image](https://github.com/user-attachments/assets/63f0e525-1383-4a47-bd59-d322daee2bc3)

Figura 6: Sistema estbale gracias a un control proporcional 

Usamos un controlador porpocional $K_p$, Esto significa que simplemente estamos multiplicado la salida por un valor constante para tratar de controlar el sistema.

Cuando conectamos el comtrolador con la planta en un sistema en lazo cerrado, la funcio de transferencia pasa a:

$$T(s) = \frac{K_p \cdot G(s)}{1 + K_p \cdot G(s)}$$

Lo que nos interesa queda en el poliminio caracteristico, donde haremos la tabla con los coeficientes del poliminio. y gracias a ello en donde aparce la constante de porpocionalidad se pone mayor a 0, con el resultado se puede determinar que resultado de $K_p$ nos funciona para volver el sistema estable.
