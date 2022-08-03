# PicoCTF2022 - SQLiLite


## Descripción

Can you login to this website?


## Hints

- `admin` is the user you want to login as.


## Solución

La página principal es un panel de login al que hay que iniciar sesión a través de una SQLi.

![](./imagenes/sqlilite-1.png)

Primero intentamos iniciar sesión como admin y cualquier contraseña.

![](./imagenes/sqlilite-2.png)

Nos dice que no hemos iniciado sesión y nos muestra la query SQL que se ejecuta. Esto nos sirve para que podamos crear nuestra inyección más facilmente.

![](./imagenes/sqlilite-3.png)

Intentamos colocar una SQLi básica que comenta todo lo que sige después de la comilla.

```SQL
admin' -- -
```

![](./imagenes/sqlilite-4.png)

La página nos dice que iniciamos sesión correctamente pero que la flag no está a plena vista.

![](./imagenes/sqlilite-5.png)

Para eso solo debemos ver el códifo fuente presionando `CTRL + u`, y podemos ver la flag.

![](./imagenes/sqlilite-6.png)


## Flag

`picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}`