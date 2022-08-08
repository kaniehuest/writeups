# PortSwigger - Directory traversal


## Lab: File path traversal, traversal sequences blocked with absolute path bypass


## Solución

Primero haces click derecho sobre una imágen y luego la abres en una pestaña nueva.

![](./imagenes/lab2-1.png)

Puedes notar un parámetro que necesita como valor el nombre de un archivo.

![](./imagenes/lab2-2.png)

Te vas a Burpsuite y haces click en **Intercept is off** para empezar a interceptar la petición.

![](./imagenes/lab2-3.png)

![](./imagenes/lab2-4.png)

Luego te vas al navegador y recargas la página.

![](./imagenes/lab2-5.png)

Interceptas la petción y la envías a la pestaña **Repeater** presionando las teclas `CTRL + R`.

![](./imagenes/lab2-6.png)

En la pestaña **Repeater** modificas el valor del parámetro por `/etc/passwd` y apretas el botón **Send**.

![](./imagenes/lab2-7.png)

Y puedes ver la respuesta de la petción a la derecha que muestra el contenido del `/etc/passwd`.

![](./imagenes/lab2-8.png)

Dejas de interceptar la petición en la pestaña **Proxy** haciendo click en el botón **Intercept is on**.

![](./imagenes/lab2-9.png)

![](./imagenes/lab2-10.png)

Vuelves al navegador y terminas el laboratorio.

![](./imagenes/lab2-11.png)

