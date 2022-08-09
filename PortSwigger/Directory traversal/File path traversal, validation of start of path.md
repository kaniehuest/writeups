# PortSwigger - Directory traversal


## Lab: File path traversal, validation of start of path


## Solución

Primero hacemos click derecho sobre una imagen y la abrimos en una pestaña nueva.

![](./imagenes/lab5-1.png)

![](./imagenes/lab5-2.png)

Luego vamos a Burpsuite y hacemos clikc en el botón **Intercept is off** para interceptar las peticiones.

![](./imagenes/lab5-3.png)

![](./imagenes/lab5-4.png)

Vamos a la página donde está la foto y recargamos.

![](./imagenes/lab5-5.png)

Interceptamos la petición y la enviamos a la pestaña **Repeater** presionando las teclas `CTRL + r`.

![](./imagenes/lab5-6.png)

En la pestaña repeater cambiamos la ruta de la imagen por `/var/www/images/../../../etc/passwd` y hacemos click en el botón **Send**.

![](./imagenes/lab5-7.png)

Vemos en la pestaña **Response** el contendio del archivo `/etc/passwd`.

![](./imagenes/lab5-8.png)

Volvemos a la pestaña **Proxy** y hacemos click en el botón **Intercept is on** para dejar de interceptar las peticiones.

![](./imagenes/lab5-9.png)

![](./imagenes/lab5-10.png)

Volvemos al navegador y resolvemos el laboratorio.

![](./imagenes/lab5-11.png)
