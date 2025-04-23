# Principio de Sustitución de Liskov (LSP)

En programación orientada a objetos, puede suceder el error de que una subclase no se comporte como su clase padre, causando que el sistema se rompa o funcione de manera erronea.

Para solucionar este problema, el principio de sustitución de Liskov, nos dice que una subclase debería poder sustituir a su clase padre y que el programa siga funcionando sin problemas. En resúmen, si tengo una clasePadre y una subClase, según este principio, yo podria en alguna instancia del programa que se utilice la clasePadre, remplazarla por la subClase y que el programa siga funcionando.

## Motivación

El problema que enfrentaba este sistema de gestión de turnos, era que desde un principio se habia creado y diseñado todos los usuarios bajo una clase padre llamada "usuario" y esa clase padre instanciaba distintos tipos de usuarios (objetos) como "recepcionista", "medico", "paciente", etc. Esto traia un problema y era que por obvias razones, el usuario del médico y del paciente no están habilitados a las mismas cosas. Entonces, habia que estar modificando la clase padre todo el tiempo y se rompian cosas o se violaba este principio de Liskov al no poder remplazar una subClase como "recepcionista" por la clase padre "usuario" sin que se rompa nada.

Para resolver este problema, se pensó de una manera distinta y se crearon clases aparte para el médico, paciente, recepcionista, etc. Y de esta manera, se respeta el principio de Liskov ya que cada uno está definido y hace lo que tiene que hacer.

## Ejemplo del mundo real

Imaginá que en un bar te dan un vaso de vidrio para tu bebida. Ese vaso se puede reemplazar por un vaso de plástico, y todo va bien. Pero si lo reemplazan por un colador, técnicamente sigue siendo un “recipiente” para tomar una bebida, pero ya no cumple con la función esperada.

Eso rompe el principio de sustitución: el objeto hijo (colador) no puede reemplazar sin problema al padre (vaso).
