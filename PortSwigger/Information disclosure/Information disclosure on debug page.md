# PortSwigger - Information disclosure


## Lab: Information disclosure on debug page


## Solución

Primero abrimos el código fuente de la página en otra pestaña presionando `CTRL + u`.

![](./imagenes/lab2-1.png)

Vemos el código fuente y buscamos algo raro.

![](./imagenes/lab2-2.png)

Al final de la página vemos un comentario con la dirección de un archivo php.

![](./imagenes/lab2-3.png)

Pegamos la dirección en la url y vamos al archivo.

![](./imagenes/lab2-4.png)

Como el archivo es muy largo presionamos `CTRL + f` y escribimos `SECRET_KEY` porque es lo que necesitamos para resolver el laboratorio.

![](./imagenes/lab2-5.png)

Volvemos a la página principal y hacemos click en el botón **Submit solution**.

![](./imagenes/lab2-6.png)

Pegamos el valor del **SECRET_KEY** y hacemos click en el botón **OK**.

![](./imagenes/lab2-7.png)

Y resolvemos el laboratorio.

![](./imagenes/lab2-8.png)