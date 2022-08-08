# PortSwigger - Directory traversal


## Lab:  File path traversal, simple case


## Solución

Primero hacemos click derecho y abrimos la imagen en una nueva pestaña.

![](./imagenes/lab1-1.png)

Notamos en la url que se muestra un parametro que necesito un nombre de archivo.

![](./imagenes/lab1-2.png)

Si vamos a Burpsuite e interceptamos la petición.

![](./imagenes/lab1-3.png)

![](./imagenes/lab1-4.png)

Y recargamos la página.

![](./imagenes/lab1-5.png)

Vemos la peticón y la enviamos a la pestaña **Repeater** presionando `CTRL + R`.

![](./imagenes/lab1-6.png)

![](./imagenes/lab1-7.png)

Cuando estemos en la pestaña **Repeater** modificamos el valor del parámetro `filename` por `../../../etc/passwd` y hacemos click en el botón**Send**.

![](./imagenes/lab1-8.png)

Observamos en la pestaña **Response** el archivo **/etc/passwd**.

![](./imagenes/lab1-9.png)

Vamos de nuevo a la pestaña **Proxy** y hacemos click en **Intercept is on** para que quede en **Intercept is off** y así dejemos de interceptar la petición.

![](./imagenes/lab1-10.png)

Volvemos a la página y resolvemos el laboratorio.

![](./imagenes/lab1-11.png)