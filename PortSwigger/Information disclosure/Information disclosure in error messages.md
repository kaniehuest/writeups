# PortSwigger - Information disclosure


## Lab: Information disclosure in error messages


## Solución

Primero hacemos click en **View details**.

![](./imagenes/lab1-1.png)

Vemos que el id en la url es un número.

![](./imagenes/lab1-2.png)

Lo ponemos entre comillas esperando que el servidor lo interprete como una string y falle.

![](./imagenes/lab1-3.png)

Lo enviamos y efectivamente el servidor lo interpreta como string y falla.

![](./imagenes/lab1-4.png)

Vemos al final la versión de Apache que necesitamos para terminar el laboratorio.

![](./imagenes/lab1-5.png)

Volvemos a la página principal del laboratorio y hacemos click en **Submit solution**.

![](./imagenes/lab1-6.png)

Ingresamos nuestra respuesta y hacemos click en **OK**.

![](./imagenes/lab1-7.png)

Y resolvemos el laboratorio.

![](./imagenes/lab1-8.png)

