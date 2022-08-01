# PicoCTF2022 - Power Cookie


## Descripción

Go to this website and see what you can discover.


## Hints

- Do you know how to modify cookies?


## Solución

Primero hacemos click en el botón **Continue as guest**.

![](./imagenes/power-cookie-1.png)

Luego abrimos las herramientas de desarrollador.

![](./imagenes/power-cookie-2.png)

Después nos vamos a la pestaña **Storage** y podemos ver una cookie con nombre **isAdmin** y de valor **0**.

![](./imagenes/power-cookie-3.png)

Editamos el valor de la cookie para que sea **1**.

![](./imagenes/power-cookie-4.png)

Recargamos la página y podemos ver la flag.

![](./imagenes/power-cookie-5.png)

## Flag

`picoCTF{gr4d3_A_c00k13_65fd1e1a}`