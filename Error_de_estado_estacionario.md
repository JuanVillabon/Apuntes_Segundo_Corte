# Error de estado estacionario

## 1.Definicion de error estacionario  

El error estacionario $$e_ss$$ se define como:
$$e_{ss} = \lim_{t \to \infty} \left[ r(t) - y(t) \right]$$

Donde $r(t)$ es la señal de referencia  y $y(t)$ la salida real del sistema en lazo cerrado. Equivalentemente, mediante el teorema del valor final en el dominio de Laplace:
$$e_ss = \lim_{s \to 0} [s*E(s)]$$

Con $E(s)$ siendo la transformada de la funcion de error

## 2.Constante de error estatico y tipo de sistema

-Constante de posicion $K_p = \lim_{s \to 0} G(s)$
- Constante de Velocidad $K_p = \lim_{s \to 0}  s*G(s)$
- Constante de Aceleracion $K_p = \lim_{s \to 0}  s^2*G(s)$

Aqui, $G(s)$ es la funcion de transferencia en lazo abierto con realimenatcion unitaria. El tipo de sistema, es el numero de integradores puros que aparecen en le camino directo del lazo.

## 3.Calculo del SSE para señaeles estandar 

Para sitemas de lazo unitario, los SSE ante entradas unitarias son:
| Tipo de señal | Constante de error | Fórmula de $e_{ss}$ |
|---------------|--------------------|--------------------------|
| Escalón       | $K_p$          | $e_{ss} = \frac{1}{1 + K_p}$ |
| Rampa         | $K_v$          | $e_{ss} = \frac{1}{K_v}$     |
| Parábola      | $K_a$         | $e_{ss} = \frac{1}{K_a}$      |

Tabla 1. Sistemas de lazo ante diferentes entradas

## 4.Relacion SSE- tipo de sistema

| Sistema | Paso \( (1/s) \) | Rampa \( (1/s^2) \) | Parábola \( (1/s^3) \) |
|---------|------------------|---------------------|------------------------|
| Tipo 0  | $\frac{1}{1 + K_p}$ | $\infty$         | $\infty$               |
| Tipo 1  | 0                   |$\frac{1}{K_v}$   | $\infty$               |
| Tipo 2  |  0                  | 0                | $\frac{1}{K_a}$        |

Tabla 2. Relacion de tipo de sistema a diferentes entradas

## 💡Ejemplo 1

Considera un sistema de lazo unitario con:

$$G(s)= \frac{K}{s+2}$$
 
Que es tipo 0 es decir, no tiene integradores puro. Para un entrada escalon unitario:

$$ K_p = \lim_{s \to 0} \frac{K}{s+2} = \frac{K}{2}$$
$$e_ss = \frac{1}{1+K_p} = \frac{1}{1+\frac{K}{2}}$$

Si desamos $e_ss \leq 0.05$, basta con resolver 

$$\frac{1}{1+\frac{K}{2}} \leq 0.05$$
$$1+\frac{K}{2} \geq 20$$
$$K \geq 38$$

## Ejercicio  1
Analisis de errores  en un sistema tipo 0

Dado $G(s) = \frac{10}{s+2}$

1. $e_ss$ para entrada escalon unitario

$$K_p = \lim_{s \to 0} \frac{10}{s+2} = 5$$

$$e_ss = \frac{1}{1+K_p} = \frac{1}{1+5}= \frac{1}{6}$$

Error de posicon es de $\frac{1}{6}$

2. $e_ss$ para entrada rampa unitario

   $$\lim_{s \to 0} \frac{1}{s(\frac{10}{s+2})} = \infty$$

3. $e_ss para  una entrada parabola unitario

 $$\lim_{s \to 0} \frac{1}{s^2(\frac{10}{s+2})} = \infty$$   

 ## Ejercicio 2
 Diseño de ganancia para especificacion de error
 *Considera $G(s) = \frac{K}{s(s+4)}$ con realimentacion unictaria. Determina el valor minimo de K neceario para que el error estacionario ante una rampa unitaria sea $\leq 0.02$

$$ \lim_{s \to 0} \frac{1}{s(\frac{K}{s(s+4})} \leq 0.02 $$
$$ \frac{4}{K} \leq 0.02$$
$$K \geq 200$$
   
   
