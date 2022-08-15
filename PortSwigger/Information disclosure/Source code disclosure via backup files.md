# PortSwigger - Information disclosure


## Lab: Source code disclosure via backup files


## Solución

Primero vamos al archivo `robots.txt` agregandolo en la url.

![](./imagenes/lab3-1.png)

Cuando accedemos vemos un archivo `/backup` al que podemos acceder.

![](./imagenes/lab3-2.png)

Cuando vamos al archivo **backup** observamos un archivo `.bak`.

![](./imagenes/lab3-3.png)

La hacemos click.

![](./imagenes/lab3-4.png)

Vemos el contenido de un archivo.

![](./imagenes/lab3-5.png)

Si revisamos bien vemos que se realiza una conexión hacia una base de datos postgresql y se observa la contraseña.

![](./imagenes/lab3-6.png)

Volvemos al inicio y hacemos click en el botón **Submit solution**.

![](./imagenes/lab3-7.png)

Ingresamos la contraseña.

![](./imagenes/lab3-8.png)

Y resolvemos el laboratorio.

![](./imagenes/lab3-9.png)

