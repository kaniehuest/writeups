# PortSwigger - SQL injection


## Lab: SQL injection UNION attack, determining the number of columns returned by the query


## Solución

En la página principal hacemos click en alguna opción de búsqueda, yo voy a hacerle click a **Lifestyle**.

![](./imagenes/lab3-1.png)

Luega se agregará a la url un filtro que busca según lo que escogiste, en este caso como escogimos **Lifestyle** nos muestro `filter?=category=Lifestyle`.

![](./imagenes/lab3-2.png)

Al final debemos agregar una query SQL para identificar la cantidad de columnas existen. Primero escribimos `' union select null -- -` y si la página nos devuelve un error entonces seguimos agregando la palabra `null` hasta que se arregle.

![](./imagenes/lab3-3.png)

Con un solo `null` nos devuelve un error, esto significa que existen más de 1 columna.

```sql
' UNION SELECT null -- -
```

![](./imagenes/lab3-4.png)

Con 2 `null` también nos devuelve un error, entonces debemos agregar más `null`.

```sql
' UNION SELECT null,null -- -
```

![](./imagenes/lab3-5.png)

Si agregamos 3 `null` el laboratorio se resuelve porque existen 3 columnas.

```sql
' UNION SELECT null,null,null -- -
```

![](./imagenes/lab3-6.png)