# La sentencia LIKE

La sentencia `LIKE` en MySQL se utiliza para buscar un patrón específico en una columna de una tabla. Es útil cuando se
desea buscar registros que contengan una cadena de texto específica o que cumplan con un patrón determinado.

La sintaxis básica de la sentencia `LIKE` es la siguiente:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE pattern;
```

Donde:

* `column1, column2, ...`: Las columnas que se desean seleccionar en la consulta.
* `table_name`: El nombre de la tabla de la que se desean extraer los registros.
* `column_name`: El nombre de la columna en la que se desea buscar el patrón.
* `pattern`: El patrón que se desea buscar en la columna. Puede contener caracteres comodín para representar cualquier
  cadena de texto.

## Caracteres comodín

En la sentencia `LIKE` se pueden utilizar dos caracteres comodín para representar cualquier cadena de texto:

| Carácter | Descripción                               |
|----------|-------------------------------------------|
| `%`      | Representa cero, uno o varios caracteres. |
| `_`      | Representa un solo carácter.              |

## Patrones de búsqueda

A continuación se presentan algunos ejemplos de patrones de búsqueda que se pueden utilizar con la sentencia `LIKE`:

| Patrón   | Descripción                                                    |
|----------|----------------------------------------------------------------|
| `abc%`   | Busca cualquier cadena que comience con `abc`.                 |
| `%xyz`   | Busca cualquier cadena que termine con `xyz`.                  |
| `%\def%` | Busca cualquier cadena que contenga `def`.                     |
| `_bc`    | Busca cualquier cadena que tenga un carácter `b`               |
| `a_c`    | Busca cualquier cadena que tenga un carácter `a`               |
| `a%b`    | Busca cualquier cadena que comience con `a` y  termine con `b` |

> **Nota:** Es importante tener en cuenta que el uso de la sentencia `LIKE` es sensible a mayúsculas y minúsculas. Por
> ejemplo, `LIKE 'abc'` no es lo mismo que `LIKE 'ABC'`. Y que el uso de los caracteres comodín puede afectar el
> rendimiento de la consulta, especialmente si se utilizan al principio del patrón de búsqueda.

> **Nota:** La sentencia `LIKE` también se puede combinar con los operadores lógicos `AND` y `OR` para realizar
> búsquedas más complejas. Por ejemplo, `WHERE column_name LIKE 'abc%' AND column_name LIKE '%xyz'`.

> **Nota:** La sentencia `LIKE` también se puede utilizar en combinación con la función `CONCAT()` para buscar patrones
> en múltiples columnas o concatenar columnas antes de aplicar el patrón de búsqueda.


