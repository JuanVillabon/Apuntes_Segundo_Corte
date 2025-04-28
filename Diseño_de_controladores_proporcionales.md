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
