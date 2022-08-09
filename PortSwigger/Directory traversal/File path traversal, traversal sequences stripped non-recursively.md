# PortSwigger - Directory traversal


## Lab: File path traversal, traversal sequences stripped non-recursively


## Solución

Primera hacemos click derecho sobre una imágen y la abrimos en una pestaña nueva.

![](./imagenes/lab3-1.png)

![](./imagenes/lab3-2.png)

En Burpsuite vamos a la pestaña **Proxy** e interceptamos las peticiones haccienndo click en el botón **Intercept is off**, si se pone de color azul estará interceptando.

![](./imagenes/lab3-3.png)

![](./imagenes/lab3-4.png)

Vamos a la imagen y recargamos la página.

![](./imagenes/lab3-5.png)

Vemos que interceptamos la petición y la enviamos a la pestaaña **Repeater** presionando los botones `CTRL + R`.

![](./imagenes/lab3-6.png)

Vamos a la pestaña **Repeater** y reemplazamos el nombre de la imágen.

El filtro de la página solo borra dos puntos y una barra. Entonces, si escribimos `....//` la página borrará dos puntos y una barra dejando el payload así:`../`.

Nuestro payload final es: `....//....//....//etc/passwd`.

Lo pegamos y hacemos click en el botón **Send**.

![](./imagenes/lab3-7.png)

Vemos que en la respuesta está el `/etc/passwd`.

![](./imagenes/lab3-8.png)

Volvemos a la pestaña **Proxy**  y para dejar de interceptar el tráfico hacemos click en **Intercept is on**.

![](./imagenes/lab3-9.png)

![](./imagenes/lab3-10.png)

Volvemos a la página y resolvemos el laboratorio.

![](./imagenes/lab3-11.png)

