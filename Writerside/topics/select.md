# La Sentencia SELECT

En MySQL y otros sistemas de gestión de bases de datos, la sentencia `SELECT` es una de las más utilizadas y poderosas
para recuperar información de una base de datos. La sentencia `SELECT` permite seleccionar datos de una o más tablas,
filtrarlos, ordenarlos y agruparlos según sea necesario.

## Sintaxis Básica

La sintaxis básica de la sentencia `SELECT` es la siguiente:

```sql
SELECT column1, column2, ..., columnN FROM table_name;
```

Donde:

- `column1, column2, ..., columnN` son los nombres de las columnas que se desean seleccionar.
- `table_name` es el nombre de la tabla de la cual se desean seleccionar los datos.
- `SELECT` es la palabra clave que indica que se desea seleccionar datos.
- `FROM` es la palabra clave que indica de qué tabla se desean seleccionar los datos.
- `;` es el delimitador que indica el final de la sentencia.

## `DISTINCT`

La cláusula `DISTINCT` se utiliza para eliminar los duplicados de los resultados de una consulta. Por ejemplo, si se
desea seleccionar los nombres únicos de los estudiantes de una tabla, se puede utilizar `DISTINCT` de la siguiente
manera:

```sql
SELECT DISTINCT column_name FROM table_name;
```

## Cláusula `ORDER BY`

La cláusula `ORDER BY` se utiliza para ordenar los resultados de una consulta en función de una o más columnas. Por
ejemplo, si se desea ordenar los resultados de una consulta por el nombre de los estudiantes en orden alfabético
ascendente, se puede utilizar `ORDER BY` de la siguiente manera:

```sql
SELECT column1, column2, ... FROM table_name ORDER BY column_name [ASC|DESC];
```

Donde:

* `ASC` ordena los resultados en orden ascendente (predeterminado).
* `DESC` ordena los resultados en orden descendente.
* `column_name` es el nombre de la columna por la cual se desea ordenar los resultados.
* `ORDER BY` es la cláusula que indica que se desea ordenar los resultados.

> **Nota:** Si no se especifica `ASC` o `DESC`, el orden predeterminado es ascendente.

> **Nota:** Se puede ordenar por múltiples columnas separándolas por comas. Tomando en cuenta que el orden de las
> columnas en la cláusula `ORDER BY` afecta el orden de los resultados.

## Cláusula `LIMIT`

La cláusula `LIMIT` se utiliza para limitar el número de filas que se devuelven en una consulta. Por ejemplo, si se
desea seleccionar solo los primeros 10 registros de una tabla, se puede utilizar `LIMIT` de la siguiente manera:

```sql
SELECT column1, column2, ... FROM table_name LIMIT 10;
```

Donde:

* `10` es el número de filas que se desean seleccionar.
* `LIMIT` es la cláusula que indica que se desea limitar el número de filas.

La cláusula `LIMIT` es útil para paginar los resultados de una consulta, ya que permite seleccionar un número
específico de filas a la vez.

Así mismo puede ser utilizada para seleccionar un rango de filas, especificando el número de fila desde donde se
desea comenzar y el número de filas a seleccionar:

```sql
SELECT column1, column2, ... FROM table_name LIMIT 5, 10;
```

Donde:

* `5` es el número de fila desde donde se desea comenzar.
* `10` es el número de filas que se desean seleccionar.
* `LIMIT` es la cláusula que indica que se desea limitar el número de filas.

> **Nota:** El primer registro tiene el índice 0.

## Orden de las Cláusulas

El orden de las cláusulas en una sentencia `SELECT` es importante. La secuencia correcta de las cláusulas es la
siguiente:

1. `SELECT`
2. `FROM`
3. `WHERE`
4. `GROUP BY`
5. `HAVING`
6. `ORDER BY`
7. `LIMIT`

Aunque no todas las cláusulas son necesarias en una consulta, es importante respetar el orden para evitar errores.

En otras palabras, la estructura de una sentencia `SELECT` es la siguiente:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
GROUP BY column1, column2, ...
HAVING condition
ORDER BY column1, column2, ...
LIMIT number;
```

## Ejemplos

### Seleccionar Todas las Columnas de una Tabla

Para seleccionar todas las columnas de una tabla, se puede utilizar el carácter `*` en lugar de los nombres de las
columnas:

```sql
SELECT * FROM table_name;
```

### Seleccionar Columnas Específicas de una Tabla

Para seleccionar columnas específicas de una tabla, se pueden listar los nombres de las columnas separados por comas:

```sql
SELECT column1, column2 FROM table_name;
```