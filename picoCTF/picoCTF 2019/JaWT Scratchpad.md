# PicoCTF2019 - JaWT Scratchpad


## Descripción

Check the admin scratchpad! 


## Hints

- What is that cookie?
- Have you heard of JWT?


## Solución

Primero iniciamos sesión con cualquier nombre, en mi caso escribí **hola**.

![](./imagenes/jawt-scratchpad-1.png)

Y podemos ver un scratchpad, pero nada más.

![](./imagenes/jawt-scratchpad-2.png)

La propia página nos da pistas. 

Primero, el nombre de la aplicación es JaWT, si juntamos las letras mayúsculas nos queda JWT que son las siglas de Json Web Token. Romper un JWT es muy común en CTFs. 

Segundo, nos marca el nombre **John**. John es una herramienta para realizar ataques de fuerza bruta, entonces es seguro que tendremos que encontrar el secreto del JWT con este método, y luego crear un JWT para hacernos pasar por el usuario **admin**.

![](./imagenes/jawt-scratchpad-3.png)

Si inspeccionamos la página y vamos a la pestaña **Storage**, veremos el valor del jwt.

![](./imagenes/jawt-scratchpad-4.png)

Copiamos el valor del jwt, nos vamos a [jwt.io][https://jwt.io/] y pegamos el valor de nuestro jwt en el campo **Encoded**.

![](./imagenes/jawt-scratchpad-5.png)

Podemos ver 2 cosas importantes, el algoritmo y el usuario. Con el algoritmo podemos decirle a john el formato que debe usar para realizar su ataque, y si encontramos el secreto podremos cambiar el nombre de usuario a **admin**.

![](./imagenes/jawt-scratchpad-6.png)

Primero guardaremos el valor de nuestro jwt en un archivo llamado **jwt.txt**.

```bash
$ echo -n "el_valor_del_jwt" > jwt.txt
```

![](./imagenes/jawt-scratchpad-7.png)

Y después ejecutaremos john para que realize su ataque de fuerza bruta, especificándole el nombre de nuestro archivo, el nombre del diccionario, y el formato HMAC-SHA256 porque anteriormente vimos que está ocupando el algoritmo **HS256**.

```bash
$ john jwt.txt --wordlist="el_diccionario_que_utilizarás" --format=HMAC-SHA256 
```

![](./imagenes/jawt-scratchpad-8.png)

Vemos que el secreto es `ilovepico`.

![](./imagenes/jawt-scratchpad-9.png)

Colocamos este secreto en la pestaña **VERIFY SIGNATURE**.

![](./imagenes/jawt-scratchpad-10.png)

Y ahora podemos cambiar nuestro nombre de usuario a **admin**.

![](./imagenes/jawt-scratchpad-11.png)

Copiamos todo lo que está en la pestaña **Encoded**, vamos a la página del reto y borramos el campo **Value**.

![](./imagenes/jawt-scratchpad-14.png)

Ahora pegamos lo que anteriormente copiamos.

![](./imagenes/jawt-scratchpad-12.png)

Finalmente recargamos la página y podemos ver la flag.

![](./imagenes/jawt-scratchpad-13.png)


## Flag

`picoCTF{jawt_was_just_what_you_thought_f859ab2f}`