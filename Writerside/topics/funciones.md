# Funciones útiles en MySQL

MySQL es un sistema de gestión de bases de datos que ofrece una amplia variedad de funciones para realizar operaciones
sobre los datos almacenados en las tablas. Estas funciones permiten realizar cálculos, manipulaciones de cadenas, fechas
y otros tipos de datos, así como realizar operaciones matemáticas y lógicas.

En este artículo, exploraremos algunas de las funciones más útiles de MySQL y cómo utilizarlas en consultas SQL.

## Funciones de existencia

Las funciones de existencia en MySQL permiten verificar si un valor o una condición existe en una tabla o en una
consulta.

### `IS NULL` y `IS NOT NULL`

Las funciones `IS NULL` y `IS NOT NULL` se utilizan para verificar si un valor es nulo o no nulo, respectivamente. Por
ejemplo, para seleccionar los clientes que no tienen un número de teléfono registrado, se puede utilizar la siguiente
consulta:

```sql
SELECT *
FROM clientes
WHERE telefono IS NULL;
```

### IN y NOT IN

Las funciones `IN` y `NOT IN` se utilizan para verificar si un valor está presente o no en un conjunto de valores. Por
ejemplo, para seleccionar los clientes que son de los estados "CA" o "NY", se puede utilizar la siguiente consulta:

```sql
SELECT *
FROM clientes
WHERE estado IN ('CA', 'NY');
```

## Funciones de Fecha y Hora

Las funciones de fecha y hora en MySQL permiten realizar operaciones sobre valores de fecha y hora, como obtener la
fecha actual, sumar o restar días, meses o años, extraer partes de una fecha, entre otras. Algunas de las funciones de
fecha y hora más comunes son:

### `NOW()`

La función `NOW()` devuelve la fecha y hora actuales del sistema en formato `YYYY-MM-DD HH:MM:SS`. Por ejemplo, para
obtener la fecha y hora actual en una consulta, se puede utilizar la siguiente consulta:

```sql
SELECT NOW() AS fecha_actual;
```

### `DATE_ADD()` y `DATE_SUB()`

Las funciones `DATE_ADD()` y `DATE_SUB()` permiten sumar o restar días, meses o años a una fecha. Por ejemplo, para
obtener la fecha actual más 7 días, se puede utilizar la siguiente consulta:

```sql
SELECT DATE_ADD(NOW(), INTERVAL 7 DAY) AS fecha_futura;
```

### `YEAR()`, `MONTH()`, `DAY()`

Las funciones `YEAR()`, `MONTH()` y `DAY()` permiten extraer el año, mes y día de una fecha, respectivamente. Por
ejemplo, para obtener el año de nacimiento de un cliente, se puede utilizar la siguiente consulta:

```sql
SELECT YEAR(fecha_nacimiento) AS año_nacimiento
FROM clientes;
```

## Funciones de Cadenas

Las funciones de cadenas en MySQL permiten realizar operaciones sobre cadenas de texto, como concatenar, buscar,
reemplazar, convertir mayúsculas y minúsculas, entre otras. Algunas de las funciones de cadenas más comunes son:

### `CONCAT()`

La función `CONCAT()` permite concatenar dos o más cadenas de texto en una sola cadena. Por ejemplo, para concatenar el
nombre y el apellido de un cliente en una sola columna, se puede utilizar la siguiente consulta:

```sql
SELECT CONCAT(nombre, ' ', apellido) AS nombre_completo
FROM clientes;
```

Resultado:

| nombre_completo |
|-----------------|
| Juan Pérez      |
| María López     |
| Pedro Gómez     |

### `UPPER()` y `LOWER()`

Las funciones `UPPER()` y `LOWER()` permiten convertir una cadena de texto a mayúsculas y minúsculas, respectivamente.
Por ejemplo, para convertir el nombre de un cliente a mayúsculas, se puede utilizar la siguiente consulta:

```sql
SELECT UPPER(nombre) AS nombre_mayusculas
FROM clientes;
```

Resultado:

| nombre_mayusculas |
|-------------------|
| JUAN              |
| MARÍA             |
| PEDRO             |

```sql
SELECT LOWER(nombre) AS nombre_minusculas
FROM clientes;
```

Resultado:

| nombre_minusculas |
|-------------------|
| juan              |
| maría             |
| pedro             |

### `SUBSTRING()`

La función `SUBSTRING()` permite extraer una subcadena de una cadena de texto. Por ejemplo, para extraer los primeros
tres caracteres del nombre de un cliente, se puede utilizar la siguiente consulta:

```sql
SELECT SUBSTRING(nombre, 1, 3) AS nombre_corto
FROM clientes;
```

Resultado:

| nombre_corto |
|--------------|
| Jua          |
| Mar          |
| Ped          |

> **Nota:** La función `SUBSTRING()` recibe tres parámetros: la cadena de texto, la posición inicial y la longitud de
> la subcadena a extraer.

> **Nota:** En MySQL, la posición inicial de una cadena de texto comienza en 1.

> **Nota:** Estas funciones pueden usarse en combinación con otras funciones y operadores para realizar operaciones más
> complejas sobre las cadenas de texto. Por ejemplo, LOWER(SUBSTRING(nombre, 1, 3)).

## Funciones Numéricas

Las funciones numéricas en MySQL permiten realizar operaciones matemáticas sobre valores numéricos, como sumas, restas,
multiplicaciones, divisiones, redondeos, entre otras. Algunas de las funciones numéricas más comunes son:

### `ROUND()`

La función `ROUND()` permite redondear un valor numérico a un número específico de decimales. Por ejemplo, para
redondear el precio de un producto a dos decimales, se puede utilizar la siguiente consulta:

```sql
SELECT ROUND(precio, 2) AS precio_redondeado
FROM productos;
```

Resultado:

| precio_redondeado |
|-------------------|
| 10.51             |
| 15.76             |
| 20.10             |

> **Nota:** La función `ROUND()` puede recibir un solo parámetro, en cuyo caso redondea al entero más cercano, o dos
> parámetros, el segundo indica la cantidad de decimales a redondear.

### `TRUNCATE()`

La función `TRUNCATE()` permite truncar un valor numérico a un número específico de decimales. A diferencia de
`ROUND()`, `TRUNCATE()` simplemente elimina los decimales adicionales en lugar de redondear el valor. Por ejemplo, para
truncar el precio de un producto a dos decimales, se puede utilizar la siguiente consulta:

```sql
SELECT TRUNCATE(precio, 2) AS precio_truncado
FROM productos;
```

Resultado:

| precio_truncado |
|-----------------|
| 10.50           |
| 15.75           |
| 20.05           |