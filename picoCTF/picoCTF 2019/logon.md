# PicoCTF 2019 - logon

## Descripción

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? 

## Hints

- Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solución

Iniciamos sesión con cualquier nombre de usuario que no sea **joe**, y cualquier contraseña.
![[logon-1.png]]

Después de iniciar sesión presionamos click derecho y en **Inspeccionar**.
![[logon-2.png]]

Hacemos click en **Application** (dependiendo de tu navegador o idioma la pestaña tendrá otro nombre, yo estoy ocupando Chromium)
![[logon-3.png]]

Hacemos click en la pestaña **Cookies** y podremos ver una cookie con nombre **admin** que tiene de valor **False**.
![[logon-4.png]]

Debemos hacer click derecho sobre esta cookie y seleccionar **Edit "value"**.
![[logon-5.png]]

Escribimos **True**, presionamos la tecla Enter.
![[logon-6.png]]

Si recargamos la página veremos la flag.
![[insp3ct0r-1.png]]

## Flag
`picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}`
