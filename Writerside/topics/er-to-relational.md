# De modelo Entidad-Relación a Modelo Relacional

## Introducción

El modelo Entidad-Relación (ER) es un modelo de datos que se utiliza para representar la estructura y las relaciones de
una base de datos de forma visual y sencilla. Este modelo se basa en la representación de entidades y sus atributos, así
como en las relaciones entre las entidades, lo que permite diseñar y comprender la estructura de la base de datos de
manera intuitiva.

Por otro lado, el modelo Relacional es un modelo de datos que se utiliza para representar la información en forma de
tablas o relaciones. Este modelo se basa en la teoría de conjuntos y álgebra relacional, lo que permite realizar
consultas y operaciones sobre los datos de forma eficiente y precisa. El modelo relacional se compone de varios
elementos básicos, como tablas, filas, columnas, claves y restricciones, que son fundamentales para su comprensión y
uso.

En este artículo, exploraremos el proceso de transformación de un modelo Entidad-Relación a un modelo Relacional.
Veremos cómo se pueden representar las entidades, atributos y relaciones del modelo ER en tablas del modelo relacional,
así como las claves y restricciones que se aplican a los datos. Este proceso es fundamental para la implementación de
bases de datos relacionales y permite garantizar la integridad y consistencia de los datos en la base de datos.

## Ejemplo de transformación

Para realizar la transformación de un modelo Entidad-Relación a un modelo Relacional, utilizaremos un ejemplo sencillo
que consta de tres entidades: `Estudiante`, `Profesor`, `Curso` y `Inscripción`. Cada una de estas entidades tiene sus
atributos y relaciones, que representaremos en el modelo ER y luego transformaremos al modelo relacional.

A continuación, presentamos el modelo Entidad-Relación de nuestro ejemplo:

![er-to-relational.png](..%2Fimages%2Fer-to-relational.png){display=block}

## Pasos para la transformación

El proceso de transformación de un modelo Entidad-Relación a un modelo Relacional consta de varios pasos que nos
permiten representar las entidades, atributos y relaciones del modelo ER en tablas del modelo relacional. A
continuación, describimos los pasos que seguiremos en este proceso:

1. Identificar las entidades fuertes.
2. Crear una tabla para cada entidad fuerte.
3. Identificar los atributos de cada entidad.
4. Crear una columna para cada atributos primario.
5. Crear una columna para cada atributo simple.
6. En caso de atributos compuestos, se deberá decidir si crear el compuesto o descomponerlo.
7. En caso de atributos multivaluados, se deberá crear una tabla adicional.
    * La nueva tabla contendrá una columna para el atributo multivaluado y una columna para la clave primaria de la
      entidad.
    * Por buenas prácticas, se recomienda crear una clave primaria del tipo `entidad_id` en la nueva tabla. Por ejemplo,
      si la entidad es `Email`, la clave primaria de la nueva tabla sería `email_id`.
    * Se creará una relación uno a muchos entre la entidad y la nueva tabla.
8. Crear una tabla para cada entidad débil y seguir del 4 al 7.
9. Identificar las relaciones entre las entidades.
10. En el caso de relaciones uno a uno, se deberá decidir si se crea una tabla adicional o si se agrega la clave foránea
    en una de las tablas. Se recomienda agregar la clave foránea en la tabla que tenga la cardinalidad máxima.
11. En el caso de relaciones uno a muchos, se deberá agregar la clave foránea en la tabla que tenga la cardinalidad
    máxima.
12. En el caso de relaciones muchos a muchos, se deberá crear una tabla adicional que contenga las claves primarias de
    ambas entidades. Además, se deberá agregar una clave primaria adicional a la tabla que contenga las claves primarias
    de ambas entidades.
    * El nombre de la tabla adicional se puede formar con los nombres de las entidades relacionadas, en orden alfabético
      y separados por un guion bajo. Por ejemplo, si las entidades son `Estudiante` y `Curso`, el nombre de la tabla
      adicional sería `Curso_Estudiante`.
    * La clave primaria adicional se puede formar con los nombres de las entidades relacionadas, en orden alfabético y
      separados por un guion bajo. Por ejemplo, si las entidades son `Estudiante` y `Curso`, la clave primaria adicional
      sería `curso_estudiante_id`.
13. Agregar las claves foráneas en las tablas correspondientes.
    * Para este paso usaremos la representación de pata de gallo (`crow's foot`) para indicar la cardinalidad de la
      relación.
14. Seleccionar y agregar el tipo de dato adecuado para cada columna.
15. Agregar las restricciones necesarias para garantizar la integridad y consistencia de los datos.
    * En estos casos solo contaremos con las restricciones: UNIQUE, NOT NULL, AUTO_INCREMENT y PRIMARY KEY.

## Nuestra herramienta de transformación

Para facilitar el proceso de transformación de un modelo Entidad-Relación a un modelo Relacional, emplearemos la
herramienta en línea ERD Editor. Esta herramienta nos permitirá diseñar las entidades, atributos y relaciones del modelo
ER, así como exportar el modelo relacional en formato SQL.

Puedes encontrar esta herramienta en el siguiente enlace: [ERD Editor](https://erd-editor.com/)

### Creando el modelo Entidad-Relación

Para comenzar, crearemos el modelo Entidad-Relación de nuestro ejemplo utilizando la herramienta ERD Editor. Crearemos
un nuevo esquema.

![erd-schema.png](..%2Fimages%2Ferd-schema.png){display=block}

Recuerda agregar un nombre descriptivo a tu esquema para identificarlo fácilmente.

![schema-name.png](..%2Fimages%2Fschema-name.png){display=block}

### Creando las tablas del modelo relacional

Para crear las tablas daremos clic derecho en el área de trabajo y seleccionaremos la opción `Add Table`. Aunque podemos
presionar la combinación de teclas `Alt + N`.

> **Nota**: En este punto, solo crearemos las tablas correspondientes a las entidades fuertes. Las tablas de las
> entidades débiles y las tablas adicionales para las relaciones muchos a muchos las crearemos posteriormente.

> **Nota**: Deberemos habilitar las opciones de `View` > `Unique` y `View` > `Auto Increment` para poder agregar estas
> restricciones a las columnas. Para esto daremos clic derecho en el área de trabajo y seleccionaremos la opción `View`.
> Luego, seleccionaremos las opciones `Unique` y `Auto Increment`.

![view-unique.png](..%2Fimages%2Fview-unique.png){display=block}

### Creando las columnas de las tablas

Para agregar las columnas a una tabla, seleccionaremos la tabla y daremos clic en el icono `+`. Otra opción es presionar
la combinación de teclas `Alt + Enter`.

![add-column.png](..%2Fimages%2Fadd-column.png){display=block}

### Agregando las claves primarias

Para seleccionar una columna como clave primaria, primero seleccionaremos la columna y luego daremos clic derecho sobre
ella. Seleccionaremos la opción `Primary Key`. Otra opción es presionar la combinación de teclas `Alt + K`.

![primary-key.png](..%2Fimages%2Fprimary-key.png){display=block}

### Agregando las claves foráneas

Para agregar una clave foránea, daremos clic derecho en un espacio vacío del área de trabajo y seleccionaremos la opción
`Relationship`. Y seleccionaremos el tipo de relación que deseamos agregar.

Seleccionamos la tabla de origen y la tabla de destino. En este estricto orden.

![relationship.png](..%2Fimages%2Frelationship.png){display=block}

> **Nota**: Puedes usar los atajos `Ctrl + Alt + N` donde `N` es el número de la relación que deseas agregar. Por
> ejemplo, `Ctrl + Alt + 1` para una relación con terminal de mínimo 0 y máximo 1.

### El resultado final

Una vez que hayamos completado la creación de las tablas y las relaciones, nuestro modelo relacional se verá de la
siguiente manera:

![relational-model.png](..%2Fimages%2Frelational-model.png){display=block}

## Conclusión

La transformación de un modelo Entidad-Relación a un modelo Relacional es un proceso fundamental en el diseño e
implementación de bases de datos relacionales. Este proceso nos permite representar de manera clara y estructurada las
entidades, atributos y relaciones del modelo ER en tablas del modelo relacional, lo que facilita la gestión y consulta
de los datos en la base de datos.

Al seguir los pasos descritos en este artículo y utilizar herramientas como ERD Editor, podemos realizar la
transformación de manera eficiente y precisa, lo que nos permitirá garantizar la integridad y consistencia de los datos
en la base de datos. Conocer y aplicar los conceptos y técnicas de diseño de bases de datos relacionales es fundamental
para el desarrollo de sistemas de información robustos y eficientes.

Por lo tanto, la transformación de un modelo Entidad-Relación a un modelo Relacional es un proceso clave en el diseño de
bases de datos relacionales y nos permite representar de manera clara y estructurada la información de un sistema de
información, lo que facilita su implementación y gestión.