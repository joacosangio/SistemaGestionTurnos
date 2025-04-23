# Principio de Segregación de Interfaces (ISP)

En sistemas mal diseñados, suele pasar que hay interfaces que tienen muchos métodos y a veces se obliga a las clases a definitrr y hacer llamado a métodos que capaz no van a utilizar, generando código de más y forzado.

Para solucionar este problema, el principio de segregación de interfaces (ISP), nos dice que ninguna clase deberia estar forzada a implementar métodos que no usa. Y por eso mismo, en lugar de tener interfaces grandes y genércias que tengan muchos métodos, se deben crear varias interfaces más segmentadas y especificas para la necesidad que tengamos.

## Motivación.

En este sistema de gestión de turnos, teniamos una sola interface de turno, la cual tenia métodos como solicitarTurno, cancelarTurno, modificarTurno y capaz el médico implementaba la interfaz de turno cuando no tenía porque cargar el método de solicitarTurno, es por eso, que se genereraron interfaces más especificas para que el médico no necesite implementar solicitarTurno porque no lo utiliza. De esa manera se respeta el principio de ISP.

## Ejemplo del mundo real

Supongamos que tenemos una licencia de conducir que sirva para manejar todos los vehiculos disponibles y a la hora de sacar la licencia, estemos habilitados a manejar por ejemplo, un helicóptero. Sería inutil además de peligroso. Es por eso, que al querer sacar la licencia te preguntan cual de todas, si vehiculo, moto, colectivo, etc. De esa manera todos tienen una licencia únicamente de lo que van a manejar y en caso de querer manejar otra cosa, se saca la otra licencia.

## Estructura de Clases

