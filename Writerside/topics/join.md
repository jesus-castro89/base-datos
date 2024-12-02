# La Sentencia JOIN

En MySQL, la sentencia `JOIN` se utiliza para combinar filas de dos o más tablas en función de una relación entre ellas.
La relación se establece mediante una columna común que existe en ambas tablas.

Para entender cómo funciona la sentencia `JOIN`, es importante conocer los conceptos básicos de las relaciones entre
tablas en una base de datos relacional. En una base de datos relacional, las tablas se pueden relacionar entre sí
mediante
claves primarias y claves foráneas.

Para efectos de los siguientes ejemplos, consideremos dos tablas: `clientes` y `pedidos`. La tabla `clientes` contiene
información sobre los clientes, como su `id_cliente`, `nombre` y `email`. La tabla `pedidos` contiene información sobre
los pedidos realizados por los clientes, como su `id_pedido`, `id_cliente` y `producto`.

### Ejemplo de Tabla `clientes`

| id_cliente | nombre  | email            |
|------------|---------|------------------|
| 1          | Juan    | juan@algo.com    |
| 2          | María   | maria@algo.com   |
| 3          | Pedro   | pedo@algo.com    |
| 4          | Ana     | ana@algo.com     |
| 5          | Daniela | daniela@algo.com |

### Ejemplo de Tabla `pedidos`

| id_pedido | id_cliente | producto  |
|-----------|------------|-----------|
| 1         | 1          | TV        |
| 2         | 2          | Laptop    |
| 3         | 1          | Teléfono  |
| 4         | 3          | Tablet    |
| 5         | 4          | Cámara    |
| 6         | 1          | Impresora |
| 7         | 2          | Monitor   |
| 8         | 3          | Teclado   |

## Tipos de JOIN

En MySQL, existen varios tipos de `JOIN` que se pueden utilizar para combinar filas de tablas. Algunos de los tipos de
`JOIN` más comunes son:

### `INNER JOIN`

El `INNER JOIN` devuelve las filas que tienen valores coincidentes en ambas tablas. Es decir, solo devuelve las filas
que tienen una relación en ambas tablas.

Por ejemplo, para combinar las tablas `clientes` y `pedidos` en función del `id_cliente`, se puede utilizar la siguiente
consulta:

```sql
SELECT clientes.nombre, pedidos.producto
FROM clientes
INNER JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
```

Resultado:

| nombre | producto  |
|--------|-----------|
| Juan   | TV        |
| María  | Laptop    |
| Juan   | Teléfono  |
| Pedro  | Tablet    |
| Ana    | Cámara    |
| Juan   | Impresora |
| María  | Monitor   |
| Pedro  | Teclado   |

### `LEFT JOIN`

El `LEFT JOIN` devuelve todas las filas de la tabla izquierda (`clientes`), junto con las filas de la tabla derecha
(`pedidos`) que tienen valores coincidentes en ambas tablas. Si no hay valores coincidentes en la tabla derecha, se
devuelven `NULL`.

Por ejemplo, para combinar las tablas `clientes` y `pedidos` utilizando un `LEFT JOIN`, se puede utilizar la siguiente
consulta:

```sql
SELECT clientes.nombre, pedidos.producto
FROM clientes
LEFT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
```

Resultado:

| nombre  | producto  |
|---------|-----------|
| Juan    | TV        |
| María   | Laptop    |
| Juan    | Teléfono  |
| Pedro   | Tablet    |
| Ana     | Cámara    |
| Juan    | Impresora |
| María   | Monitor   |
| Pedro   | Teclado   |
| Daniela | NULL      |

### `RIGHT JOIN`

El `RIGHT JOIN` devuelve todas las filas de la tabla derecha (`pedidos`), junto con las filas de la tabla izquierda
(`clientes`) que tienen valores coincidentes en ambas tablas. Si no hay valores coincidentes en la tabla izquierda, se
devuelven `NULL`.

Por ejemplo, para combinar las tablas `clientes` y `pedidos` utilizando un `RIGHT JOIN`, se puede utilizar la siguiente
consulta:

```sql
SELECT clientes.nombre, pedidos.producto
FROM clientes
RIGHT JOIN pedidos ON clientes.id_cliente = pedidos.id_cliente;
```

Resultado:

| nombre  | producto  |
|---------|-----------|
| Juan    | TV        |
| María   | Laptop    |
| Juan    | Teléfono  |
| Pedro   | Tablet    |
| Ana     | Cámara    |
| Juan    | Impresora |
| María   | Monitor   |
| Pedro   | Teclado   |
| Daniela | NULL      |

## Conclusión

La sentencia `JOIN` en MySQL es una herramienta poderosa para combinar filas de tablas en función de una relación entre
ellas. Los diferentes tipos de `JOIN` permiten seleccionar las filas que cumplen ciertas condiciones y obtener
resultados
personalizados en función de las necesidades del usuario. Es importante comprender cómo funcionan los `JOIN` y cuándo
utilizar cada tipo para obtener los resultados deseados en una consulta SQL.

