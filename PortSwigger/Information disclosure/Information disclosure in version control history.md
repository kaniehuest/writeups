# PortSwigger - Information disclosure


## Lab: Information disclosure in version control history


## Solución

Primero vamos a la console y ejecutamos el siguiente comando para copiar toda la carpeta `.git` a nuestro escritorio.

```bash
wget -r linkdellaboratorio
```

![](./imagenes/lab5-1.png)

Cuando termine de descargar entramos a la carpeta.

```bash
cd nombredelacarpeta
```

![](./imagenes/lab5-2.png)

Entramos a la carpeta `.git`.

```bash
cd .git
```

![](./imagenes/lab5-3.png)

Ejecutamos el siguiente comando  para ver los commits.

```bash
git log
```

Podemos notar que en el mensaje del commit nos indica que se ha eliminado la contraseña de admin en un archivo config.

![](./imagenes/lab5-4.png)

Ejecutamos el siguiente comando para visualizar los cambios que se realizar en el último commit.

```bash
git show hashdelcommit
```

![](./imagenes/lab5-5.png)

Observamos que se eliminó la contraseña de admin y se reemplazó por **env('ADMIN_PASSWORD')**.

![](./imagenes/lab5-6.png)

Vamos a la página web del reto y hacemos click en el botón **My account**.

![](./imagenes/lab5-7.png)

Ingresamos el usuario administrador y la contraseña que obtuvimos en el commit.

![](./imagenes/lab5-8.png)

Si todo salió correctamente inicamos sesión como administrador.

![](./imagenes/lab5-10.png)

Hacemos click en el botón **Admin panel**.

![](./imagenes/lab5-11.png)

Eliminamos al usuario carlos.

![](./imagenes/lab5-12.png)

Y terminamos el laboratorio.

![](./imagenes/lab5-13.png)

