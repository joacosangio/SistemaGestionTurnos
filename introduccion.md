# Anexo - Introducción al Diseño Orientado a Objetos

El diseño orientado a objetos, es un paradigma de programación que se caracteriza por organizar como se desarrolla un software en entidades llamadas objetos. Estos objetos tienen atributos y métodos. los atributos de los objetos, vendrian a ser las carácteristicas que tiene. Y los métodos, las funcionalidades que tiene el objeto. Por ejemplo, podemos pensar a un alumno como un objeto. Este objeto alumno, tendrá atriubutos como "nombre", "apellido", "email" y "DNI". Y sus métodos serían, "registrarse", "iniciar sesión", "editar perfil", etc. En resumen, cuando enfrentamos un problema que requiere un software basado en la programación orientada a objetos (POO), descomponemos el problema en distintos objetos y clases para modelarlo de manera eficiente.

Este paradima es importante, ya que, permite modelar de manera ordenada y fomenta la reutilización de código gracias a sus clases y objetos.

Otro concepto importantisimo en el diseño orientado a objetos, son las clases. Estas vendrian a ser una plantilla o molde de los objetos y cuando creamos o instanciamos los objetos, heredan los atributos y métodos que definimos en estas clases. Es decir, yo tengo una clase llamada "usuario", de la cual, se instancian distintos objetos como pueden ser, "alumnos" y "profesores". Estos objetos comparten algunos atributos y métodos, pero también pueden tener otros propios.

En el diseño orientado a objetos tenemos 4 principios fundamentales que lo caracterizan:

* **Abstracción:** La abstracción es la manera de modelar los elementos esenciales de un sistema. Esto se hace definiendo distintos objetos y clases en base de lo que necesita el software. Por ejemplo, si necesitamos crear un sistema de gestión de turnos, necesitamos abstraernos del problema, y comenzar a definir los posibles objetos. Como podrian ser, un "turno", "paciente" y "médico". Ese proceso se conoce como abstracción.
* **Encapsulación:** Muchas veces, no necesitamos que el usuario conozca o interactue con toda la información (atributos y métodos) de un objeto, es por eso que se protege o restringe el acceso a cierta información. Por ejemplo, en un motor de un auto, el usuario no interactua con los pistones o las válvulas, si no, que todo eso se encapsula y simplemente interactua con el mediante el pedal del acelerador.
* **Herencia:** Este concepto hace referencia, a que cuando instanciamos objetos de una clase, los objetos heredan ciertos atributos pero también pueden tener propios. Por ejemplo, podemos tener una clase "vehiculo", la cual tiene atributos predeterminados como "nombre", "marca", "modelo", etc. Luego, instanciamos objetos de esa clase que heredarían esos atributos pero pueden tener otros como "potencia" y "kilometraje".
* **Polimorfismo:** El polimorfismo es la capacidad o caracteristica de los objetos en este paradigma, de reaccionar de manera distinta a un mismo mensaje, a pesar de tener distintos atributos o métodos. Por ejemplo, en una plataforma puedo enviar un mensaje a los usuarios, pero responderán de manera distinta dependiendo de si son "alumno" o "profesor".

***

## Requisitos iniciales del sistema

Los principales requisitos para que el sistema funcione son los siguientes:

1. Gestionar los turnos, permitiendo que se puedan agendar citas, cancelarlas, modificarlas, aceptarlas, rechazarlas y todo lo necesario relacionado a los turnos. Esto haciendo referencia al problema que está teniendo el centro de salud en cuanto a la perdida de las citas agendadas.
2. Que haya notificaciones de los turnos, tanto en pacientes como en profesionales de la salud. Esto haciendo referencia a que hay pacientes que no reciben la confirmación de su turno o que los médicos no reciben notificaciones de cancelación o aceptación.
3. Que haya un calendario o historial de turnos para que los médicos no tengan asignado más de un paciente en un mismo horario. Esto haciendo referencia a que a veces los médicos tienen más turnos de los que pueden atender o más de un paciente en el mismo horario.
4. Que la información tanto de los pacientes como de los médicos esté protegida y que no cualquiera pueda acceder a esa información.
5. Que se pueda registrar tanto a los usuarios (con sus atributos correspondientes) como a los médicos (con sus atributos correspondientes). Todo esto para poder saber la disponibilidad de los médicos, área de especialidad, etc y para consultar el historial de turnos de los pacientes u otros datos de relevancia.
6. Se necesita que los turnos sean descriptivos, es decir, que tengan un motivo y observación si hiciera falta.

***

## Casos de uso

A continuación, se detallan 5 casos de uso para este proyecto

1. Caso de uso 1
   * **Nombre de la condición:** Registrar paciente.
   * **Actor(es) involucrado(s):** Una persona que quiera utilizar el sistema y deba crear un usuario para hacerlo.
   * **Descripción breve:** Permite que el usuario se registre en el software, concediendole un usuario el cual puede utilizar para agendar sus citas, ver sus turnos y utilizar el software en general.
   * **Flujo principal de eventos:**
      1. El usuario ingresa a la plataforma.
      2. El usuario comienza el proceso de registro de usuario.
      3. El usuario completa toda la información que se le pide.
      4. Se le notifica al usuario que su usuario ha sido creado con exito.
   * **Precondiciones:**
      1. El usuario no debe estar registrado previamente.
      2. El usuario debe proporcionar la información obligatoria para que se realice el proceso correctamente (Username, Password e información de contacto).
   * **Postcondiciones:**
      1. Se crea el usuario en la base de datos.
      2. Se habilita el usuario en la plataforma para que se le puedan asignar turnos y otras acciones.
    
2. Caso de uso 2
   * **Nombre de la condición:** Asignar turno.
   * **Actor(es) involucrado(s):** Paciente o recepcionista.
   * **Descripción breve:** Permite que el paciente o el/la recepcionista asigne un turno con un profesional de la salud del establecimiento que esté disponible para una consulta.
   * **Flujo principal de eventos:**
      1. El paciente o recepcionista ingresa a la plataforma.
      2. Selecciona la opción de asignar nuevo turno.
      3. Se ingresan los datos del paciente.
      4. Se selecciona la especialidad o profesional de la salud.
      5. Se muestran los horarios disponibles del médico.
      6. Se selecciona el horario y se confirma la operación.
      7. Se envia una notificación al usuario y al médico.
   * **Precondiciones:**
      1. El usuario debe estar registrado previamente.
      2. El médico debe tener su usuario registrado en el sistema.
      3. El médico debe tener su agenda actualizada.
   * **Postcondiciones:**
      1. Se genera el turno en la base de datos.
      2. Se bloquea la agenda del médico en el horario del turno.
      3. Se notifica al cliente y al médico.
    
3. Caso de uso 3
   * **Nombre de la condición:** Modificar turno
   * **Actor(es) involucrado(s):** Recepcionista.
   * **Descripción breve:** Permite que el/la recepcionista modifique un turno previamente creado y asignado
   * **Flujo principal de eventos:**
      1. El o la recepcionista ingresa al software.
      2. Busca en el sistema el turno correspondiente.
      3. Verifica que la modificacioón no genere inconvenientes en el calendario del médico.
      4. Se realiza la modificación y se guarda en el sistema.
      5. Le llega la notificación al médico y al paciente de que se modificó el turno.
   * **Precondiciones:**
      1. Debe haber un turno registrado en el sistema.
      2. El turno debe estar asignado al usuario y al médico.
      3. Debe ser realizado por alguien autorizado a modificar los turnos.
   * **Postcondiciones:**
      1. Se modifica el turno en la base de datos.
      2. Se alerta al paciente y al médico que la información del turno fue modificada.
    
4. Caso de uso 4
   * **Nombre de la condición:** Cancelación de turno
   * **Actor(es) involucrado(s):** Recepcionista o paciente.
   * **Descripción breve:** Permite que el/la recepcionista o el usuario cancele un turno previamente creado y asignado
   * **Flujo principal de eventos:**
      1. El paciente o El o la recepcionista ingresa al software.
      2. Se accede al turno.
      3. Se cancela el turno añadiendo el motivo de la cancelación.
      4. El sistema modifica la agenda del médico eliminando el turno para que vuelva a estar disponible esa franja horaria.
      5. Se notifica al paciente y al médico que el turno fue cancelado.
   * **Precondiciones:**
      1. Debe haber un turno registrado en el sistema.
      2. El turno debe estar asignado al usuario y al médico.
      3. Debe ser realizado por alguien autorizado a cancelar los turnos.
   * **Postcondiciones:**
      1. Se elimina el turno de la base de datos, dejando como cancelado.
      2. Se alerta al paciente y al médico que el turno fue cancelado.
      3. Se libera el espacio en la agenda del médico.
      4. Queda la cancelación del turno en el historial del paciente.
    
5. Caso de uso 5
   * **Nombre de la condición:** Envio de notificaciones.
   * **Actor(es) involucrado(s):** Sistema.
   * **Descripción breve:** El sistema envia notificaciones a médicos y pacientes cuando un turno es confirmado, cancelado o modificado.
   * **Flujo principal de eventos:**
      1. Se crea, cancela o modifica un turno en el sistema.
      2. Se detecta que cambio fue el que se realizó.
      3. Se genera una notificación con toda la información que corresponda.
      4. Se envia la notificación al paciente y médico correspondiente.
   * **Precondiciones:**
      1. Debe haber un turno registrado en el sistema.
      2. El médico y paciente deben tener configurado un método de notificaciones valido (Email, telefono, etc.)
      3. El turno registrado en el sistema debe sufrir un cambio que requiera de notificación.
   * **Postcondiciones:**
      1. Se modifica la información del turno en el sistmea.
      2. Queda un registro de que ese turno fue modificado.
      3. Llega una notificacioón al paciente o médico.
      4. Se genera un aviso de que el médico y paciente fueron notificados.

***
## Boceto

A continuación, se muestra un boceto de algunas clases que podrian ser esenciales para el sistema, junto con sus atributos y algunos métodos que podrian tener los objetos.

![image](https://github.com/user-attachments/assets/6ba8547e-5666-42dd-9025-c5b79c42ea93)


Adjunto Drive con las imagenes para poder ampliar.
* [Drive](https://drive.google.com/file/d/1855H9sDamhv-nnz4ALVaMp17omGNvwZX/view?usp=drive_link)

***
