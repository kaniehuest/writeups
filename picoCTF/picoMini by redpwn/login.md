# PicoMini by redpwn - login


## Descripción

My dog-sitter's brother made this website but I can't get in; can you help?


## Solución

Primero abremos las herramientas de desarrollador y vamos a la pestaña **Debugger**, luego hacemos click en el archivo **index.js** y podemos ver el contenido.

![](./imagenes/login-1.png)

Hacemos click en el botón con símbolos de llaves **{}**.

![](./imagenes/login-2.png)

Y vemos el archivo index.js más legible. Leyendo un poco vemos que el final está comparando una string con el input de usuario y contraseña.

Si te parece extraña esta comparación puedes leer este artículo sobre los [operadores condicionales ternarios](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Conditional_Operator). Basicamente es un **loop if** pero en una sola línea.

![](./imagenes/login-3.png)

Usuario: `YWRtaW4` 
Contraseña: `cGljb0NURns1M3J2M3JfNTNydjNyXzUzcnYzcl81M3J2M3JfNTNydjNyfQ`

Si copias y pegas esto en los campos del login te dará error, porque estas cadenas están codificadas en **base64**. Si las decodificamos tendremos el siguiente resultado:

Usuario: `admin`
Contraseña: `picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}`


## Flag

`picoCTF{53rv3r_53rv3r_53rv3r_53rv3r_53rv3r}`