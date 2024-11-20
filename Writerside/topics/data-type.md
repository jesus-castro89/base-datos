# Tipos de Datos en SQL

## Introducción

Los tipos de datos en SQL son una parte fundamental de la definición de tablas y columnas en una base de datos
relacional. Los tipos de datos permiten especificar el formato y la estructura de los datos que se pueden almacenar en
una columna, lo que ayuda a garantizar la integridad y consistencia de los datos en la base de datos. En SQL, los tipos
de datos se dividen en varios grupos, como tipos de datos numéricos, de cadena, de fecha y hora, lógicos, binarios,
entre otros.

En este artículo, exploraremos los tipos de datos más comunes en SQL y veremos cómo se utilizan para definir las
columnas de una tabla en una base de datos relacional. Veremos ejemplos de cómo se definen los tipos de datos en SQL y
cómo se pueden aplicar restricciones y propiedades a las columnas para garantizar la integridad de los datos.

## Tipos de Datos Numéricos

Los tipos de datos numéricos en SQL se utilizan para almacenar valores numéricos, como enteros, decimales y números
reales. Algunos de los tipos de datos numéricos más comunes son:

| Tipo de Dato | Descripción                                 |
|--------------|---------------------------------------------|
| `INT`        | Entero                                      |
| `FLOAT`      | Número de punto flotante                    |
| `DOUBLE`     | Número de punto flotante de doble precisión |
| `DECIMAL`    | Número decimal (Se almacena como texto)     |

> **Nota:** Los tipos de datos numéricos en SQL pueden variar según el sistema de gestión de bases de datos (SGBD) que
> se esté utilizando. Es importante consultar la documentación del SGBD para conocer los tipos de datos específicos que
> se admiten.

> **Nota:** Los tipos de datos numéricos y algunos otros requieren del uso de paréntesis para especificar la longitud o
> precisión del dato. Por ejemplo, `INT(10)` específica un entero con una longitud máxima de 10 dígitos, mientras que
> `DECIMAL(5,2)` específica un número decimal con 5 dígitos en total y 2 decimales.

## Tipos de Datos de Cadena

Los tipos de datos de cadena en SQL se utilizan para almacenar valores de texto, como nombres, direcciones,
descripciones, entre otros. Algunos de los tipos de datos de cadena más comunes son:

| Tipo de Dato | Descripción                         |
|--------------|-------------------------------------|
| `CHAR`       | Cadena de longitud fija             |
| `VARCHAR`    | Cadena de longitud variable         |
| `TEXT`       | Cadena de longitud variable (larga) |

> **Nota:** Los tipos de datos de cadena en SQL pueden variar según el SGBD que se esté utilizando. Es importante
> consultar la documentación del SGBD para conocer los tipos de datos específicos que se admiten.

> **Nota:** Los tipos de datos de cadena requieren del uso de paréntesis para especificar la longitud máxima de la
> cadena. Por ejemplo, `CHAR(50)` específica una cadena de longitud fija de 50 caracteres, mientras que `VARCHAR(255)`
> específica una cadena de longitud variable con una longitud máxima de 255 caracteres.

## Tipos de Datos de Fecha y Hora

Los tipos de datos de fecha y hora en SQL se utilizan para almacenar valores de fecha, hora o fecha y hora. Algunos de
los tipos de datos de fecha y hora más comunes son:

| Tipo de Dato | Descripción                        |
|--------------|------------------------------------|
| `DATE`       | Fecha (YYYY-MM-DD)                 |
| `TIME`       | Hora (HH:MM:SS)                    |
| `DATETIME`   | Fecha y hora (YYYY-MM-DD HH:MM:SS) |
| `TIMESTAMP`  | Marca de tiempo (UNIX timestamp)   |

> **Nota:** Los tipos de datos de fecha y hora en SQL pueden variar según el SGBD que se esté utilizando. Es importante
> consultar la documentación del SGBD para conocer los tipos de datos específicos que se admiten.

## Tipos de Datos Lógicos

Los tipos de datos lógicos en SQL se utilizan para almacenar valores booleanos, es decir, valores de verdad o falsedad.
Algunos de los tipos de datos lógicos más comunes son:

| Tipo de Dato | Descripción    |
|--------------|----------------|
| `BOOLEAN`    | Booleano       |
| `BIT`        | Bit            |
| `TINYINT`    | Entero pequeño |

> **Nota:** Los tipos de datos lógicos en SQL pueden variar según el SGBD que se esté utilizando. Es importante
> consultar la documentación del SGBD para conocer los tipos de datos específicos que se admiten.

Para mayor información sobre los tipos de datos en MySQL puedes consultar
la [documentación oficial](https://dev.mysql.com/doc/refman/8.0/en/data-types.html).

## Conclusiones

Los tipos de datos en SQL son una parte esencial de la definición de tablas y columnas en una base de datos relacional.
Los tipos de datos permiten especificar el formato y la estructura de los datos que se pueden almacenar en una columna,
lo que ayuda a garantizar la integridad y consistencia de los datos en la base de datos. Es importante seleccionar el
tipo de dato adecuado para cada columna en función de los datos que se van a almacenar y de las operaciones que se van a
realizar sobre ellos. Además, es importante aplicar restricciones y propiedades a las columnas para garantizar la
integridad de los datos y evitar problemas de inconsistencia y errores en la base de datos.