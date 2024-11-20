# Atributos de las columnas

## Introducción

Los atributos de las columnas son las propiedades que definen el tipo de datos y las restricciones que se aplican a los
valores de una columna en una tabla de una base de datos relacional. Estos atributos permiten definir las
características de los datos que se pueden almacenar en una columna, lo que ayuda a garantizar la integridad y
consistencia de los datos en la base de datos.

## Primary Key

El atributo `PRIMARY KEY` se utiliza para identificar de forma única cada registro en una tabla. Esto significa que el
valor de la clave primaria no se puede repetir en la tabla y que cada registro debe tener un valor único en la columna
de la clave primaria. La clave primaria se utiliza para garantizar la integridad y consistencia de los datos en la base
de datos.

Por ejemplo, si una tabla `Clientes` tiene una columna `ID` con el atributo `PRIMARY KEY`, significa que cada cliente
debe tener un ID único en la tabla, es decir, no se permiten valores duplicados en la columna `ID`.

## Auto Increment

El atributo `AUTO_INCREMENT` se utiliza para generar automáticamente valores numéricos secuenciales para una columna en
una tabla. Esto significa que cada vez que se inserta un nuevo registro en la tabla, el valor de la columna con el
atributo `AUTO_INCREMENT` se incrementa automáticamente en una unidad. Este atributo es útil para generar
identificadores únicos para los registros de una tabla.

Por ejemplo, si una tabla `Productos` tiene una columna `ID` con el atributo `AUTO_INCREMENT`, significa que cada
producto de la tabla tendrá un ID único y secuencial, es decir, el valor de la columna `ID` se incrementará
automáticamente cada vez que se inserte un nuevo producto en la tabla.

## Not Null

El atributo `NOT NULL` se utiliza para garantizar que una columna no contenga valores nulos. Esto significa que todos
los registros de la tabla deben tener un valor válido en la columna, lo que ayuda a evitar problemas de inconsistencia
y errores en la base de datos.

Por ejemplo, si una columna `Nombre` de la tabla `Clientes` tiene el atributo `NOT NULL`, significa que todos los
registros de la tabla deben tener un valor válido en la columna `Nombre`, es decir, no se permiten valores nulos en
esta columna.

## Unique

El atributo `UNIQUE` se utiliza para garantizar que los valores de una columna sean únicos en la tabla. Esto significa
que no se permiten valores duplicados en la columna, lo que ayuda a evitar la inserción de datos duplicados y a
mantener la integridad de los datos en la base de datos.

Por ejemplo, si una columna `Correo` de la tabla `Usuarios` tiene el atributo `UNIQUE`, significa que todos los
valores de la columna `Correo` deben ser únicos en la tabla, es decir, no se permiten valores duplicados en esta
columna.

## Default

El atributo `DEFAULT` se utiliza para asignar un valor por defecto a una columna si no se específica un valor al
insertar un nuevo registro en la tabla. Esto significa que si no se proporciona un valor para la columna en la
instrucción `INSERT`, se utilizará el valor por defecto especificado en el atributo `DEFAULT`.

Por ejemplo, si una columna `FechaCreacion` de la tabla `Usuarios` tiene el atributo `DEFAULT CURRENT_TIMESTAMP`,
significa que si no se especifica una fecha de creación al insertar un nuevo usuario en la tabla, se utilizará la
fecha y hora actuales como valor por defecto en la columna `FechaCreacion`.

## Zero Fill

El atributo `ZEROFILL` se utiliza para rellenar con ceros los valores numéricos de una columna hasta alcanzar la
longitud máxima especificada. Esto significa que si un valor numérico es menor que la longitud máxima de la columna,
se rellenará con ceros a la izquierda para completar la longitud máxima.

Por ejemplo, si una columna `Codigo` de la tabla `Productos` tiene el atributo `INT(5) ZEROFILL`, significa que si el
valor del código es `123`, se mostrará como `00123` en la tabla, es decir, se rellenará con ceros a la izquierda
hasta alcanzar la longitud máxima de 5 dígitos.

## Unsigned

El atributo `UNSIGNED` se utiliza para especificar que una columna solo puede contener valores positivos o cero. Esto
significa que los valores negativos no son válidos para la columna con el atributo `UNSIGNED`, lo que ayuda a
garantizar la integridad de los datos en la base de datos.

Por ejemplo, si una columna `Edad` de la tabla `Usuarios` tiene el atributo `TINYINT UNSIGNED`, significa que la
columna solo puede contener valores enteros positivos entre 0 y 255, es decir, no se permiten valores negativos en
esta columna.

## Conclusiones

Los atributos de las columnas son propiedades que definen el comportamiento y las restricciones de los datos en una
tabla de una base de datos relacional. Estos atributos son fundamentales para garantizar la integridad y consistencia
de los datos en la base de datos, lo que ayuda a prevenir problemas de inconsistencia y errores en la manipulación de
los datos. Al utilizar los atributos adecuados en las columnas de una tabla, se puede asegurar que los datos sean
válidos, coherentes y fiables, lo que facilita su almacenamiento, consulta y manipulación en la base de datos.