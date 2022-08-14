# PortSwigger - OS command injection


## Lab: OS command injection, simple case


## Solución

Navegador: **Firefox**

Primero hacemos click en el botón **View details** de cualquier producto.

![](./imagenes/lab1-1.png)

Luego abrimos las herramientas de desarrollador y nos vamos a la pestaña **Network**.

![](./imagenes/lab1-2.png)

Hacemos click en el botón **Check stock**.

![](./imagenes/lab1-3.png)

Y vemos una petición que se realiza con el método POST que podemos editar si hacemos click derecho y hacemos click en la opción **Edit and resend**.

![](./imagenes/lab1-4.png)

Se abrirá un nuevo panel para editar la petición.

![](./imagenes/lab1-5.png)

 Nosotros agregaremos `;whoami` al final del **Request body**.

![](./imagenes/lab1-6.png)

Y presionaremos el botón **Send**.

![](./imagenes/lab1-7.png)

Vemos que nuestra nueva petición tiene de estado el número 200 y eso significa que todo se realizó correctamente.

![](./imagenes/lab1-8.png)

Hacemos click en nuestra petición y vamos a la pestaña **Response** para ver el resultado de nuestro comando inyectado.

![](./imagenes/lab1-9.png)

Y con esto resolvemos el laboratorio sin el uso de Burpsuite.

![](./imagenes/lab1-10.png)


