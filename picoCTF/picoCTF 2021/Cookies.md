# PicoCTF2021 - Cookies


## Descripción

Who doesn't love cookies? Try to figure out the best one. 


## Solución

Este challenge es bastante malo, basicamente es aumentar el valor de la cookie hasta llegar a un cierto número.

Abrimos las herramientas de desarrollador, nos vamos a la pestaña de **Storage** y editamos el **Value** de la cookie

![](./imagenes/cookies-1.png)

Por ejemplo, editamos al valor a **1** y luego recargamos la página.

![](./imagenes/cookies-2.png)

Notamos que a medida que aumentamos el valor, el mensaje va cambiando.

![](./imagenes/cookies-3.png)

Si cambiamos el valor al número 18 veremos la flag.

![](./imagenes/cookies-4.png)


## Flag

``picoCTF{3v3ry1_l0v3s_c00k135_064663be}``