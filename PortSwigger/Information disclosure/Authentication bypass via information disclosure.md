# PortSwigger - Information disclosure


## Lab: Authentication bypass via information disclosure


## Solución

Navegador: **Firefox**

Primero hacemos click en el botón **My account**.

![](./imagenes/lab4-1.png)

Iniciamos sesión con las credenciales que nos indica la descripción del laboratorio.

![](./imagenes/lab4-2.png)

![](./imagenes/lab4-3.png)

Cuando iniciemos sesión iremos a la ruta `/admin`. Una vez que estemos ahí la página nos indica que solo los usuarios locales tienen permiso de usar las funciones de admin.

![](./imagenes/lab4-4.png)

Abrimos las herramientas de desarrollador.

![](./imagenes/lab4-5.png)

Y nos vamos a la pestaña **Network**.

![](./imagenes/lab4-6.png)

Recargando la página vemos una petición GET con el número de estado 401.

![](./imagenes/lab4-7.png)

Si le hacemos click derecho y luego seleccionamos la opción **Edit and Resend** nos aparecerá una pestaña a la derecha.

![](./imagenes/lab4-8.png)

Cambiamos el método de la petición por el **TRACE**.

![](./imagenes/lab4-9.png)

Y enviamos la petición haciendo click en el botón **Send**.

![](./imagenes/lab4-10.png)

Vemos que nuestra nueva petición tiene de esta el número 200.

![](./imagenes/lab4-11.png)

Le hacemos click a nuestra petición y nos vamos a la pestaña **Response**.

![](./imagenes/lab4-12.png)

Copiamos la cadena en base64 y la pegamos en cualquier decodificador de base64 en internet, yo utilizé Cyberchef.

![](./imagenes/lab4-13.png)

Notamos que se agrega una cabecera nueva a nuestra petición con nuestra dirección IP.

![](./imagenes/lab4-14.png)

Hacemos click derecho sobre nuestra petición anterior y luego seleccionamos la opción **Edit and Resend** nuevamente.

![](./imagenes/lab4-15.png)

En el campo **Request Headers** agregamos la cabecera que vimos anteriormente.

![](./imagenes/lab4-16.png)

Cambiamos nuestra IP por 127.0.0.1 para indicar que nuestra dirección IP es local.

![](./imagenes/lab4-17.png)

Cambiamos el método a GET.

![](./imagenes/lab4-18.png)

Y hacemos click en el botón **Send**.

![](./imagenes/lab4-19.png)

Nuestra petición tiene como estado el número 200.

![](./imagenes/lab4-20.png)

La seleccionamos y vamos a la pestaña **Response**.

![](./imagenes/lab4-21.png)

Bajamos y al final vemos 2 opcione, eliminar el usuario carlos y el usuario wiener.

![](./imagenes/lab4-22.png)

Si pasamos el cursor sobre la palabra **Delete** marcada en azul podemos ver un enlace `/admin/delete?username=carlos`.

![](./imagenes/lab4-23.png)

Agregamos esto a la URL y vemos que la página nuevamente nos pide la cabecera para indicar que somos usuarios locales.

![](./imagenes/lab4-24.png)

En las herramientas de desarrollador vemos la petición con número de estado 401.

![](./imagenes/lab4-25.png)

Le hacemos click derecho y seleccionamos la opción **Edit and Resend**.

![](./imagenes/lab4-26.png)

Agregamos la cabecera anterior.

![](./imagenes/lab4-27.png)

Seleccionamos el botón **Send**.

![](./imagenes/lab4-28.png)

Y resolvemos el laboratorio.

![](./imagenes/lab4-29.png)

