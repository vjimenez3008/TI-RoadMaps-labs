capa 7: **aplicación**

Es la mas cercana al usuario final, inicia la comunicacion entre el usuario y las aplicaciones con las que interactua personalmente, en esta capa los datos se traducen de la sintaxis a la que se convirtió en algo que el usuario puede leer.  ejemplo de esto un navegador web o una aplicacion de correo electronico.  Esta capa tambien puede identificar socios de comunicacion , verificar que recursos estan disponibles y asegurarse de que la comunicacion este sincronizada correctamente.

**capa 6:  Presentación

La capa de presentación se encarga de preparar los datos para la capa de aplicación. Los dos dispositivos que se comunican pueden utilizar diferentes metodos de codificacion de sus datos. por lo tanto, la capa 6 convierte los datos entrantes en algo que se puede leer en la capa de aplicacion . esto incluye cifrar y descifrar datos. 
Esta capa tambien comprime los datos que provienen de la capa de aplicacion antes de enviarlos a la capa 5 , la de sesion. 

capa 5: **sesión**

La capa de sesion maneja la apertura y cierre de las comunicaciones de red entre dos dispositivos que interactuan.  La sesion se refiere al tiempo entre la apertura y el cierre de la interaccion. 

**capa 4:  transporte***

La capa de transporte maneja la comunicación de extremo a extremo entre los dispositivos que interactúan entre sí. La gestión de la comunicación implica tomar los datos en la capa de sesión y dividirlos en partes denominadas segmentos. La capa de transporte en el dispositivo que recibe la comunicación maneja el reensamblaje de los segmentos en datos que es consumible por la capa de sesión.

Además, la capa de transporte se encarga de administrar el flujo y cualquier mensaje de error necesario que deba enviarse en caso de que algo salga mal. Para administrar el flujo de datos, la capa de transporte se asegura de que no se envíe tan rápido que el dispositivo del receptor no pueda manejarlo. Para controlar errores, la capa de transporte verifica si los datos transmitidos se hicieron por completo. Si no lo es, esta capa solicitará una retransmisión.

La capa 4 es donde funcionan los números de puerto del protocolo de control de transmicion TCP y del protocolo de datagrama de usuario UDP Las direcciones de protocolo de Internet (IP) operan en la capa 3, la capa de red. TCP, UDP e IP son protocolos que facilitan la forma en que se envían y reciben los datos.


**Capa 3:  red**

La capa de red facilita la transferencia de datos cuando dos redes se comunican entre sí. Si dos dispositivos de comunicación utilizan la misma red, entonces no hay necesidad de la capa de red. La capa de red divide los segmentos que provienen de la capa de transporte. Estos se denominan paquetes. La división de los segmentos en paquetes ocurre en el dispositivo del remitente y se vuelven a ensamblar en el dispositivo receptor.

La capa de red también funciona como una herramienta de eficiencia. Descubre la ruta física óptima necesaria para llevar los datos a su destino. Esta función se denomina “enrutamiento”.


**Capa 2:  enlace de datos**

La capa de enlace de datos es como la capa de red, excepto que la capa de enlace de datos facilita la transferencia de datos entre dos dispositivos que utilizan la misma red. En la capa de enlace de datos, los paquetes se dividen en piezas denominadas marcos. De manera similar a la capa de red, la capa de enlace de datos maneja el control de flujo y error. La capa de transporte es diferente en que solo administra el flujo de datos y errores cuando dos redes se comunican entre sí.

Dentro de la capa de enlace de datos, tiene dos subcapas, las capas de control de acceso a medios (MAC) y control de enlace lógico (LLC). La mayoría de los switches realizan sus tareas en la capa 2. En algunos casos, los switches funcionan en la capa 3 porque facilitan la comunicación entre dos redes o redes virtuales de área local (VLAN). Esto debe suceder en la capa 3 porque, en estas situaciones, los datos deben enrutarse, que es una tarea de capa 3.

**Capa 1: Fisica**

La capa física implica el equipo físico que transfiere datos, como conmutadores y cables. En esta capa, los datos se convierten en cadenas de 1 en 1 y 0 en 0. En la capa física, los dispositivos tienen que acordar un método para distinguir los 1 de los 0, lo que permite que los datos digitales sean interpretados adecuadamente por cada dispositivo.

La capa física incluye una variedad de componentes, como cables, la frecuencia de radio utilizada para transmitir datos, Wi-Fi y las otras estructuras físicas para transmitir datos, como pines, voltajes necesarios y tipos de puertos.


![[Pasted image 20250901223958.png]]