# PortSwigger - OS command injection


## Lab: Blind OS command injection with time delays


## Solución

Navegador: **Firefox**

Primero hacemos click en el botón **Submit feedback**.

![](./imagenes/lab2-1.png)

Abrimos las herramientas de desarrollador y vamos a la pestaña **Network**.

![](./imagenes/lab2-2.png)

Rellenamos el formulario y hacemos click en el botón **Submit feedback**.

![](./imagenes/lab2-3.png)

Vemos que se realiza una petición por el método POST que editaremos haciendo click derecho y en **Edit and Resend**.

![](./imagenes/lab2-4.png)

Vemos que se abre una ventana la derecha con el nombre **New Request**.

![](./imagenes/lab2-5.png)

Después de nuestro email inyectamos nuestro comando `||sleep 10||`.

![](./imagenes/lab2-6.png)

Luego hacemos click en el botón **Send**.

![](./imagenes/lab2-7.png)

Vemos que nuestra petición se realizó correctamente, podemos comprobarlo haciendole click a la petición y yendo a la pestaña **Timings** vemos que se demoró 10 segundos.

![](./imagenes/lab2-8.png)

Y resolvemos el laboratorio sin el uso de Burpsuite.

![](./imagenes/lab2-9.png)

