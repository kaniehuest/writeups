# PortSwigger - OS command injection


## Lab: Blind OS command injection with output redirection


## Solución

Navegador: **Firefox**

Primero hacemos click en el botón **Submit feedback**.

![](./imagenes/lab3-1.png)

Abrimos las herramientas de desarrollador y vamos a la pestaña **Network**.

![](./imagenes/lab3-2.png)

Rellenamos el formulario y hacemos click en **Submit feedback**.

![](./imagenes/lab3-3.png)

Vemos que se realiza una petición con el método POST que podemos editar haciendo click derecho y en **Edit and Resend**.

![](./imagenes/lab3-4.png)

Observamos una nueva pestaña a la derecha llamada **New Request**.

![](./imagenes/lab3-5.png)

Inyectamos nuestro payload al final de nuestro correo electrónico `||whoami > hola.txt||`. Este payload ejecuta el comando **whoami** y redirige el output a un archivo que llamaremos **hola.txt**.

![](./imagenes/lab3-6.png)

Hacemos click en el botón **Send**.

![](./imagenes/lab3-7.png)

Vemos que nuestra petición tiene de estado el número 200, por lo tanto todo se realizó correctamente.

![](./imagenes/lab3-8.png)

Volvemos a la página principal del reto y abrimos una imagen en una pestaña nueva.

![](./imagenes/lab3-9.png)

Nos fijamos que en la url se está entregando el nombre de un archivo, así que, en lugar de **65.jpg** escribiremos el nombre del archivo en el que escribimos el output del comando.

![](./imagenes/lab3-10.png)
Yo le puse **hola.txt** al archivo, por lo tanto escribiré hola.txt y vemos el resultado del comando **whoami**.

![](./imagenes/lab3-11.png)

Y resolvemos el laboratorio sin necesidad de Burpsuite.

![](./imagenes/lab3-12.png)

