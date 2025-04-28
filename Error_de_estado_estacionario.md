# Error de estado estacionario

## Definicion de error estacionario  

El error estacionario $$e_ss$$ se define como:
$$e_{ss} = \lim_{t \to \infty} \left[ r(t) - y(t) \right]$$

Donde $r(t)$ es la señal de referencia  y $y(t)$ la salida real del sistema en lazo cerrado. Equivalentemente, mediante el teorema del valor final en el dominio de Laplace:
$$e_ss = \lim_{s \to 0} [s*E(s)]$$

Con $E(s)$ siendo la transformada de la funcion de error

## Constante de error estatico y tipo de sistema

-Constante de posicion $K_p = \lim_{s \to 0} G(s)$
- Constante de Velocidad $K_p = \lim_{s \to 0}  s*G(s)$
- Constante de Aceleracion $K_p = \lim_{s \to 0}  s^2*G(s)$

Aqui,$G(s)$ es la funcion de transferencia en lazo abierto con realimenatcion unitaria. El tipo de sistema, es el numero de integradores puros que aparecen en le camino directo del lazo.
