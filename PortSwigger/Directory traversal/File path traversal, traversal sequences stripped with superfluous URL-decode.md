# PortSwigger - Directory traversal


## Lab: File path traversal, traversal sequences stripped with superfluous URL-decode


## Solución

Primero hacemos click derecho sobre una imágen y la abrimos en una pestaña nueva.

![](./imagenes/lab4-1.png)

![](./imagenes/lab4-2.png)

Luego interceptamos las peticiones en Burpsuite haciendo click en el botón **Intercept is off** para que cambie a color azul.

![](./imagenes/lab4-3.png)

![](./imagenes/lab4-4.png)

Luego vamos a la pestaña del navegador donde está la imágen y recargamos la página.

![](./imagenes/lab4-5.png)

Vemos que interceptamos la petición y la enviamos a la pestaña **Repeater** presionando los botones `CTRL + r`.

![](./imagenes/lab4-6.png)

Cambiamos el nombre de la imágen por nuestro payload `..%252F..%252F..%252Fetc/passwd` y enviamos la petición.  

![](./imagenes/lab4-7.png)

Vemos el archivo en pestaña **Response**.

![](./imagenes/lab4-8.png)

Volvemos a la pestaña **Proxy** en Burpsuite y hacemos click en el botón **Intercept is on** para dejar de interceptar las peticiones.

![](./imagenes/lab4-9.png)

![](./imagenes/lab4-10.png)

Volvemos al navegador y resolvemos el laboratorio.

![](./imagenes/lab4-11.png)


