# PicoCTF2019 - client-side-again


## Descripción

Can you break into this super secure portal? 


## Hints

What is obfuscation?


## Solución

Hacemos click derecho y seleccionamos **Inspeccionar**.

![](./imagenes/client-side-again-1.png)

Luego nos vamos a la pestaña **Sources**.

![](./imagenes/client-side-again-2.png)

Si no nos aparece nada debemos recargar la página.

![](./imagenes/client-side-again-3.png)

Se ve que está ofuscado, por lo tanto hacemos click en **Pretty print**.

![](./imagenes/client-side-again-4.png)

Y podemos notar un array con la flag dividida en distintas partes.

![](./imagenes/client-side-again-5.png)


## Flag

`picoCTF{not_this_again_337115}`