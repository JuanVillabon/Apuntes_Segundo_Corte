# Estabilidad

## ¿Qué es la estabilidad?

La estabilidad es una propiedad fundamental que indica si un sistema de control se mantiene controlado o responde de manera predecible ante una perturbación o un cambio en la entrada.
Un sistema es estable si, ante cualquier entrada acotada (limitada), su salida también permanece acotada y, además, si no hay entrada, el sistema tiende a volver a un estado de equilibrio.

### Clasificación de estabilidad

  1. Estable: La salida se mantiene limitada y tiende a un valor fijo con el tiempo.
  2. Inestable: La salida crece sin límite ante una pequeña perturbación.
  3. Marginalmente estable: La salida ni crece sin límite ni se reduce a cero, sino que oscila permanentemente (como en un sistema no amortiguado).

## Teorema del valor final

Es una ecuacion bastante util en el analisis de sistemas y en la teoria dde control, donde nos indica cual es el valor final en el estado estacionario del sistema.

Cuando un sistema dinamico que se encuentra representado por nuna ecucion diferencial, llega al estado estacionario cuando el tiempo va para infinito, quiere decir qur los cambios en el sistema se vuelven nulos.

$$\lim_{s \to 0} \left[ sF(s) - f(0) \right]$$
$$\lim_{t \to \infty }[f(t)]$$

Una condicion es que el sistema debe ser estable. Si el sistema no es estable, el teorema del valor final no es estable
