# __Actividad 1__

## Tipos de Kernel y sus diferencias
+ Kernel Monolitico: Es el único responsable de la gestión de la memoria y de los procesos, de la comunicación entre procesos y proporciona funciones de soporte de drivers y hardware.
    + No es modular
    + Mayor Rendimiento que un microkernel
    + Cualquier cambio que se realice, se debe reiniciar el sistema operativo

+ Microkernel: se ha diseñado intencionadamente de un tamaño pequeño para que en caso de fallo no paralice todo el sistema operativo. Para que el funcionamiento sea grande, el microkernel se divide en varios modulos.
    + Los procesos tienen que esperar en una cola para obtener información
    + Se añaden modulos extras para las funcionalidades extras
    + Es mas seguro que un kernel monolitico

+ Kernel Hibrido: Es una combinacion entre el Kernel monolitico y microkernel, por lo cual el kernel grande se hace más compacto y modulable. Otras partes del kernel pueden cargarse dinámicamente.
    + Incluyen código extra con el objetivo de mejorar el rendimiento.
    + Los controladores de dispositivos y las extensiones al sistema operativo se pueden cargar y descargar fácilmente como módulos, sin interrumpir el sistema


Existe un nuevo tipo de kernel el cual se esta implementando, los exonúcleos, también conocidos como sistemas operativos verticalmente estructurados, representan una aproximación radicalmente nueva al diseño de sistemas operativos. La idea subyacente es permitir que el desarrollador tome todas las decisiones relativas al rendimiento del hardware. Los exonúcleos son extremadamente pequeños, ya que limitan expresamente su funcionalidad a la protección y el multiplexado de los recursos. Se llaman así porque toda la funcionalidad deja de estar residente en memoria y pasa a estar fuera, en librerías dinámicas.

## User vs Kernel Mode
| User Mode | Kernel Mode |
| --------- | ----------- |
| Al iniciar una aplicación en modo de usuario, Windows crea un proceso para la aplicación. El proceso proporciona a la aplicación un espacio de direcciones virtuales privado y una tabla de identificadores privados. Dado que el espacio de direcciones virtuales de una aplicación es privado, una aplicación no puede modificar los datos que pertenecen a otra aplicación. Cada aplicación se ejecuta de forma aislada y, si una aplicación se bloquea, el bloqueo se limita a esa aplicación. Otras aplicaciones y el sistema operativo no se ven afectados por el bloqueo. | Todo el código que se ejecuta en modo kernel comparte un único espacio de direcciones virtuales. Por lo tanto, un controlador en modo kernel no está aislado de otros controladores y del propio sistema operativo. Si un controlador en modo kernel escribe accidentalmente en la dirección virtual incorrecta, los datos que pertenecen al sistema operativo u otro controlador podrían verse comprometidos. Si se bloquea un controlador en modo kernel, todo el sistema operativo se bloquea. |
