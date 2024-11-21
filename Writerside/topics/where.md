# Clausula WHERE

La cláusula WHERE se utiliza para filtrar registros en una consulta SQL. La cláusula WHERE se utiliza para extraer solo
los registros que cumplen una condición específica.

## Sintaxis

La sintaxis básica de la cláusula WHERE es la siguiente:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Donde:

* `column1, column2, ...`: Las columnas que se desean seleccionar en la consulta.
* `table_name`: El nombre de la tabla de la que se desean extraer los registros.
* `condition`: La condición que deben cumplir los registros para ser seleccionados.
* `SELECT`: La instrucción que se utiliza para seleccionar columnas de una tabla.
* `FROM`: La instrucción que se utiliza para especificar la tabla de la que se desean extraer los registros.
* `WHERE`: La cláusula que se utiliza para filtrar los registros que cumplen una condición específica.

### Operadores de Comparación

En la cláusula WHERE se pueden utilizar varios operadores de comparación para evaluar las condiciones. Algunos de los
operadores de comparación más comunes son:

| Operador    | Descripción     |
|-------------|-----------------|
| `=`         | Igual a         |
| `!=` o `<>` | Diferente de    |
| `>`         | Mayor que       |
| `<`         | Menor que       |
| `>=`        | Mayor o igual a |
| `<=`        | Menor o igual a |

### Operadores Lógicos

Además de los operadores de comparación, en la cláusula WHERE se pueden utilizar operadores lógicos para combinar
condiciones. Algunos de los operadores lógicos más comunes son:

| Operador | Descripción |
|----------|-------------|
| `AND`    | Y lógico    |
| `OR`     | O lógico    |
| `NOT`    | Negación    |

### La función BETWEEN

La función `BETWEEN` se utiliza para seleccionar valores dentro de un rango específico. La sintaxis de la función
`BETWEEN` es la siguiente:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
``` 

Donde:

* `column1, column2, ...`: Las columnas que se desean seleccionar en la consulta.
* `table_name`: El nombre de la tabla de la que se desean extraer los registros.
* `column_name`: El nombre de la columna en la que se desea aplicar la condición.
* `value1`: El valor mínimo del rango.
* `value2`: El valor máximo del rango.
* `SELECT`: La instrucción que se utiliza para seleccionar columnas de una tabla.
* `FROM`: La instrucción que se utiliza para especificar la tabla de la que se desean extraer los registros.
* `WHERE`: La cláusula que se utiliza para filtrar los registros que cumplen una condición específica.
* `BETWEEN`: La función que se utiliza para seleccionar valores dentro de un rango específico.

> **Nota:** La función `BETWEEN` incluye los valores límite del rango en los resultados de la consulta.

> **Nota:** La función `BETWEEN` es equivalente a la siguiente condición:
`column_name >= value1 AND column_name <= value2`. Y por consiguiente es valida para diversos tipos de datos.