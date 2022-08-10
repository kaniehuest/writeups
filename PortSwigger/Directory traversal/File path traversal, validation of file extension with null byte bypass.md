# PortSwigger - Directory traversal


## Lab: File path traversal, validation of file extension with null byte bypass


## Solución

Hacemos click derecho sobre una imagen y la abrimos en una pestaña nueva.

![](./imagenes/lab6-1.png)

![](./imagenes/lab6-2.png)

Luego vamos a Burpsuite e interceptamos las peticiones haciendo click en el botón **Intercept is off** para que se ponga de color azul.

![](./imagenes/lab6-3.png)

![](./imagenes/lab6-4.png)

Ahora vamos a la pestaña en el navegador donde está la foto y recargamos.

![](./imagenes/lab6-5.png)

Vemos que interceptamos la petición y la enviamos a la pestaña **Repeater** haciendo click derecho y **Send to repeater** o presionando los botones `CTRL + r`.

![](./imagenes/lab6-6.png)

Vamos a la pestaña **Repeater** y modificamos el valor de `filename` por `../../../etc/passwd%00.png`.

![](./imagenes/lab6-7.png)

Vemos el contenido del archivo en la pestaña **Response**.

![](./imagenes/lab6-8.png)

Volvemos a la pestaña **Proxy** y hacemos click en el botón **Intercept is on** para dejar de interceptar las peticiones.

![](./imagenes/lab6-9.png)

![](./imagenes/lab6-10.png)

Volvemos al navegador y resolvemos el laboratorio.

![](./imagenes/lab6-11.png)

