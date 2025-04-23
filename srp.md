# Principio de Responsabilidad Única (SRP)

En sistemas mal diseñados, suele pasar que hay clases que tienen muchas responsabilidades asignadas y eso dificulta la modificacion y escalabilidad ordenada del código.

Para solucionar este problema, el principio de responsabilidad única (SRP) es el primer principio de SOLID. Este principio nos dice que una clase en un sistema, debe tener un solo propósito para cambiar, es decir, que debe tener una única responsabilidad. Por ejemplo, si nosotros tenemos una clase que cada vez que hay un cambio en el sistema o en algún método, tenemos que andar toqueteandola o modificandola y se rompe algo que no deberia romperse, significa que estámos violando este principio.

Es por esto que si seccionamos o separamos responsabilidades (como indica este principio) estariamos solucionando este problema. Porque el código y las responsabilidades se vuelven más fáciles de entender y modificar sin que otras partes se vean afectadas.

###


## Motivación

Un problema que enfrentaba este sistema de gestión de turnos, es que por ejemplo, habia una clase "Recepcionista" , la cual tenia muchas responsabilidades asociadas al mismo tiempo (asignar turnos, modificar turnos, cancelar turnos, imprimir comprobantes, etc.). Entonces, si por algún motivo cambia el método de asignar turnos, vamos a tener que tocar la clase "Recepcionista" aunque la lógica de imprimir comprobantes siga igual. Y esto mismo rompe el SRP porque un cambio afecta a otro sin que este último haya cambiado.

También, separar responsabilidades como la autenticación del usuario y la gestión de turnos, mejorando la mantenibilidad y liberando al Paciente u otros usuarios de tantas responsabilidades.

El SRP nos ayuda a solucionar esto, separando las responsabilidades en clases únicas para que se puedan modificar de manera individual sin romper nada. Por ejemplo, separamos en asignadorDeTurnos, modificadorDeTurnos, canceladorDeTurnos, etc

## Ejemplo del mundo real

Supongamos que en una empresa tenemos a un empleado al cual le asignaron durante el día limpiar, controlar la caja, atender a los clientes y delegar las tareas a los demás empleados. Si un día cambia la manera de atender a los clientes, el resto de procesos se va a entorpezer porque el empleado debera aprender la nueva manera, acostrumbrarse, practicar, etc. Si aplicamos el SRP en este ejemplo, la empresa deberia contratar a un gerente que delegue las tareas, a un empleado de caja que controle la caja, un empleado de atención al cliente que atienda a los clientes y por último un empleado de limpieza que se encargue de limpiar. De esta manera, se dividen las responsabilidades y no se ven afectados otros procesos que no tienen nada que ver.

## Estructura de clases

Se muestra imágen del problema resuelto y un ejemplo de como se seccionan las clases correctamente para respetar este principio SOLID

![image](https://github.com/user-attachments/assets/3839871f-248d-4315-8d8a-53e5515314ef)

Adjunto Drive para que se pueda ampliar la imágen

[Drive](https://drive.google.com/file/d/1Walh2JiimeOjuTtxmsKoA82QyhBIcv7p/view?usp=sharing)

