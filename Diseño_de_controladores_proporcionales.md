# Diseño de controladores proporcionales
## ¿Como controlar estos sistemas?

Para poder controlar estos sistemas sed debe saber que queremos lograr con la variable que se quire controlar, Comparar la varaiable que se quiere contolar con el valor deseado de las misma, a partir de resultado de la comparacion se toma una decision.

## Componentes de un sistema de control

![image](https://github.com/user-attachments/assets/039b3340-8b24-4759-9d4d-a6ec7b7cde26)

- Comparador: Compara la señal de referencia (setpoint) con la salida medida del sistema (señal real).

- Controlador: Recibe el error del comparador y calcula la señal de control basada en este error. En un controlador proporcional, la salida es directamente proporcional al error.

- Actuador: Recibe la señal de control del controlador y la convierte en una acción física que afecta al sistema. El actuador puede ser un motor, una válvula, una bomba, etc.

- Planta: Es el sistema o proceso que se desea controlar. Es el objeto de control, como un motor, un horno, un sistema de transporte, etc.

- Sensor: Mide la salida del sistema (también conocida como variable controlada). Esta señal es enviada al comparador para ser comparada con la referencia.

- Retroalimentación: La retroalimentación es la señal que se envía de vuelta desde el sensor al comparador y controlador. Esto permite al sistema ajustar su comportamiento en función de la diferencia entre la salida real y la referencia.

## Lazo Cerrado

Los sistemas de control de lazo cerrado son ampliamente utilizados en la variedad de industrias para regular y controlar procesos automatizados. Tambien es conocido como sistema de control realimentacion, utiliza una señal de retroalimentacion para comparar el resusltado deseado con el resultado actual y ajustar el proceso en consecuencia, permitiendo una mayor precision y estabilidad en comparacion con los sistemas de lazo abierto.

![image](https://github.com/user-attachments/assets/f11fee7a-452d-4064-b02e-3d4649f418d0)

Este valor deseado se conoce como el Setpoint y sera el unico valor modificado en el sistema. La funcion de transferencia es esencial para analizar como se comporta el sistema ante diferentes entradas y perturbaciones. Para una comparacion profunda de como se determina y utiliza la funcin de transferencia en sistema de control.

- Ventajas:

1. Estabilidad: Ayuda a mantener el sistema estable incluso ante perturbaciones o cambios en las condiciones del proceso.

2. Precisión: Permite que el sistema se acerque más a la referencia deseada.

3. Compensación de errores: La retroalimentación reduce el error en el sistema.

- Desventajas:

1. Sobresalto: El sistema puede experimentar picos o oscilaciones en la salida si el controlador no está bien sintonizado.

2. Desempeño limitado con controladores proporcionales: Un controlador proporcional puede no eliminar el error completamente en sistemas de lazo cerrado (a menos que se agregue integral o derivativo).

## Control ON-OFF

Este tipo de controlador, tambien llamado Todo o Nada, usa un algoritmo simple para solamente revisa la variable del proceso esta por encima o por debajo de un setpoint determinado.

En terminos practico, la variable manipuladad o la señal de control cambia entre totalmente ON o totalmente OFF, sin estados intermedios. Este tipo de accionamiento provoca un control muy impreciso de la variable de proceso.

![image](https://github.com/user-attachments/assets/b771b5ff-596a-41df-b832-618541fda12c)

Si el error es mayor que un umbral predefinido, el sistema se activa (ON). Si el error es menor que otro umbral (generalmente más pequeño), el sistema se desactiva (OFF).
Típicamente en sistemas con un comportamiento binario, como control de temperatura en hornos o calentadores, Puede generar oscilaciones o inestabilidad debido al cambio abrupto entre los estados ON y OFF, y el sistema no puede mantener un valor de referencia preciso.

## Controlador proporcional

Es la forma mas simple de control continuo que se puede utilizar en un sistema de lazo cerrado que corrigue el error entre una señal deseada y la señal real, aplicando una accion proporcional a ese error.

Un controlador proporcional es un dispositivo que ajusta su salida en proporción directa al error presente en el sistema.
El error e(t) es la diferencia entre el valor deseado (referencia o setpoint) y el valor actual medido de la salida del sistema.

![image](https://github.com/user-attachments/assets/5460f7ee-3094-479a-9e3d-fa7e9cb0b11e)

- Se representa de la siguiente manera:

$$ u(t) = K_{p} * e(t) $$

Donde:

- $u(t)$ = Salida del controlador
- $K_{p}$ = Ganancia proporcional
- $e(t)$ = Referencia $r(t)$ - Salida medida $y(t)$

- Funcion: El controlador proporcional busca reducir el error de manera rápida, pero no siempre puede eliminarlo completamente. Normalmente queda un pequeño error permanente llamado error en estado estacionario.

  1. Si el error es grande, el controlador aplica una acción de control fuerte.
  2. Si el error es pequeño, la acción de control es suave.
  3. Si no hay error, la acción de control también es cero (idealmente).
 
- Efecto de $K_{p}$
  1. Ganancia baja: respuesta lenta y error grande.
  2. Ganancia alta: respuesta rápida, pero puede causar sobresalto, oscilaciones o incluso inestabilidad si es muy alta.
 
## Función de trasnferecia de un sistema de lazo cerrado

![image](https://github.com/user-attachments/assets/c464c871-ed22-40b1-8d6f-11062373f03e)

1. $E = R - y$
2. $U = EC$
3. $y = UG$
4. $\frac{U}{C} = R - y$
5. $\frac{\frac{y}{G}}{C} = R - y$
6. $y = GC(R - y)$
7. $y + GCy = GCR$
8. $y(1 + GC) = GCR$

- Resultado Final:

$$ \frac{y}{R} = \frac{GC}{(1 + GC)} $$

### Ejemplo 

  1. Lazo Abierto

$$ G(s) = \frac{0,25}{s + 2} $$

$$ G(s) = \frac{\frac{0,25}{2}}{\frac{s}{2} + 1} $$

A. $K$ = 0,125
B. $T$ = $\frac{1}{2} Seg$ = 0,5 Seg

- Entonces:
- $t_{s} = 4 * 0,5 Seg$ = 2 Seg

  2. Lazo Cerrado

$$ G(s) = \frac{0,25}{s + 2} $$

$$ G_{0}(s) = \frac{K_{p}G(s)}{1 + K_{p}G(s)} $$

$$ = \frac{K_{p}\frac{0,25}{s + 2}}{1 + K_{p}\frac{0,25}{s + 2}} $$

$$ G_{0}(s) = \frac{y}{R} = \frac{0,25K_{p}}{s + 2 + 0,25K_{p}} $$


 
