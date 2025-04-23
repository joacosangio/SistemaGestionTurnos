# Principio de Inversión de Dependencias (DIP)

A veces en los sitemas, hay clases de alto nivel y muy importantes que depnden o están un "escalon" más abajo de importancia que clases muy especificas y pequeñas. Esto hace que la trazabilidad de problemas sea más dificultosa, que las pruebas sean más dificiles de hacer p que haya acoplamiento.

Para solucionar este problema, el principio de inversión de dependencias nos dice que se invierte la dirección de las dependencias, haciendo el sistema más flexible y desacoplado.

* Las clases de alto nivel no deben depender de clases de bajo nivel
* Ambas deben depender de abstracciones (interfaces)
* Las abstracciones no deben depender de los detalles.


## Motivación

Un problema que tenia el sistema de gestion ded turnos, era que por ejemplo, la recepcionista usaba una clase interna calendario directamente para consultar turnos, estába acoplado al detalle. Por eso, para solucionar este problema, se creó una interfaz llamada consultadorDeCalendario la cual, utiliza consultarTurno. De esta manera se invierten las direcciones de las dependencias.

## Ejemplo del mundo real

Un ejemplo del mundo real, podria ser un adaptador universal, el cual se le puede enchufar todo tipo de cables. En este caso, la pared no sabe si estamos enchuifando un USB-C, un cable power, una lámpara, lo que sea. En este caso el adaptador sería la interfaz y todo lo que se le conceste serían el resto de implementaciones.

## Estructura de Clases

![image](https://github.com/user-attachments/assets/085dcd61-6c3d-4def-b9a6-95d26964dc9d)

[Drive](https://drive.google.com/file/d/1XBA-tG04-2ZhstLgoKXtJT0dKFS1moFq/view?usp=sharing)
