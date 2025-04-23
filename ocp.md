# Principio de Abierto/Cerrado (OCP)

Un problema común en sistemas mal diseñados, es que cuando se necesita agregar funcionalidades nuevas, modificamos el código existente y terminamos rompiendo algo que ya funcionaba.

Para solucionar ese problema, el principio de Abierto/Cerrado (OCP) en SOLID, nos dice que el software debe estar abierto para extensión, pero cerrado para modificación. Es decir, deberías poder agregar nuevas funcionalidades sin cambiar el código ya escrito, usando abstracciones como interfaces o clases base. De esta manera no rompemos nada de lo que ya funciona, simplemente agregamos funcionalidades. 


## Motivación

En este sistema de gestión de turnos, sucedia que el envio de notificaciones por ejemplo, tenia canales configurados como correo, telefono o mensaje. Y si queriamos agregar otro método de envio o modificar los existentes, teniamos que tocar código que ya funcionaba y se terminaba rompiendo algo en el envio, los médicos no recibian las alertas e iban a los turnos cancelados, los pacientes no recibian la modificacion de los turnos e iban horas antes del turno pensando que era el horario correcto y otra gran cantidad de problemas del estilo.

El OCP nos ayuda a solucionar esto de manera que creamos una interface de envio de notificaciones y a su vez, dentro de esa interface vemos el envio de mensajes, el envio de mails, el enviode correos, etc. Entonces, si en un futuro se quiere agregar una funcionalidad de aviso por llamada, simplemente se agrega la funcionalidad y no es necesario ir a tocar y modificar los demás canales o métodos de envío. 

## Ejemplo del mundo real

Imaginémosnos un tren el cual fue diseñado con locomotora y vagones todos iguales y únicos en su tipo. Si tuviesemos que agregar un vagón extra para transportar carbón, tendriamos que modificar más partes del trén debido a que no va a encastrar y otros problemas. En cambio, si diseñamos una locomotora a la cual se le pueda encastrar cualquier vagón, podriamos tener un tren que transporte, madera, personas, carbón, etc. Y es cuestión de agregar más funcionalidades (en este caso vagones) y no es necesario modificar las demás existentes.

## Estructura de Clases

