# Algebra Relacional

El álgebra relacional es un lenguaje formal que se utiliza para definir operaciones sobre relaciones. Estas operaciones
son fundamentales para el manejo y la manipulación de bases de datos relacionales. El álgebra relacional se basa en
conjuntos y operaciones de conjuntos, lo que permite realizar consultas y transformaciones sobre los datos de forma
eficiente y precisa.

## Operaciones Básicas

El álgebra relacional define varias operaciones básicas que se utilizan para manipular relaciones. Algunas de las
operaciones más comunes son:

### Selección (σ)

La operación de selección (σ) permite filtrar las filas de una relación que cumplen una condición específica. Por
ejemplo, la selección de los estudiantes con una calificación mayor a 70 en un examen se puede expresar
como:

```tex
σ_{(Calificación > 70)}(Estudiantes)
```

### Proyección (π)

La operación de proyección (π) permite seleccionar las columnas de una relación que se desean mostrar. Por ejemplo, la
proyección de los nombres y apellidos de los estudiantes se puede expresar como:

```tex
π_{(Nombre, Apellido)}(Estudiantes)
```

### Unión (∪)

La operación de unión (∪) permite combinar dos relaciones que tienen la misma estructura en una sola relación. Por
ejemplo, la unión de las relaciones de estudiantes de dos cursos diferentes se puede expresar como:

```tex
EstudiantesCurso1 ∪ EstudiantesCurso2
```

### Diferencia (-)

La operación de diferencia (-) permite obtener las filas que están en una relación pero no en otra. Por ejemplo, la
diferencia entre los estudiantes de un curso y los estudiantes de otro curso se puede expresar como:

```tex
EstudiantesCurso1 - EstudiantesCurso2
```

### Producto Cartesiano (×)

La operación de producto cartesiano (×) permite combinar todas las filas de una relación con todas las filas de otra
relación. Por ejemplo, el producto cartesiano de los estudiantes y los cursos se puede expresar como:

```tex
Estudiantes × Cursos
```

## Derivadas

Las operaciones básicas del álgebra relacional se pueden combinar para formar operaciones más complejas. Algunas de las
operaciones derivadas más comunes son:

### Intersección (∩)

La operación de intersección (∩) permite obtener las filas que están en ambas relaciones. Por ejemplo, la intersección
entre los estudiantes de un curso y los estudiantes de otro curso se puede expresar como:

```tex
EstudiantesCurso1 ∩ EstudiantesCurso2 = EstudiantesCurso1 - (EstudiantesCurso1 - EstudiantesCurso2)
```

### Agrupamiento (Γ)

La operación de agrupamiento (Γ) permite agrupar las filas de una relación en base a un criterio específico y aplicar
una función de agregación sobre cada grupo. Por ejemplo, el agrupamiento de los estudiantes por curso y la suma de las
calificaciones se puede expresar como:

```tex
Γ_{(Curso), SUM(Calificación)}(Estudiantes)
```

Las funciones de agregación más comunes son:

* SUM: suma
* AVG: promedio
* COUNT: conteo
* MAX: máximo
* MIN: mínimo

### Ordenamiento (τ)

La operación de ordenamiento (τ) permite ordenar las filas de una relación con base a uno o más atributos. Por ejemplo,
el ordenamiento de los estudiantes por calificación descendente se puede expresar como:

```tex
τ_{(Calificación DESC)}(Estudiantes)
```

### Join (⨝)

La operación de join (⨝) permite combinar dos relaciones en base a una condición de igualdad entre los valores de una
columna. Por ejemplo, el join de los estudiantes y los cursos en base al código del curso se puede expresar como:

```tex
Estudiantes ⨝_{(Estudiantes.Curso = Cursos.Código)} Cursos
```

### Left Outer Join (⟕)

La operación de left outer join (⨝<sub>L</sub>) permite combinar dos relaciones con base en una condición de igualdad
entre
los valores de una columna, manteniendo todas las filas de la relación de la izquierda. Por ejemplo, el left outer join
de los estudiantes y los cursos se puede expresar como:

```tex
Estudiantes ⟕_{ (Estudiantes.Curso = Cursos.Código)} Cursos
```

### Right Outer Join (⟖)
La operación de right outer join (⨝<sub>R</sub>) permite combinar dos relaciones con base en una condición de igualdad
entre los valores de una columna, manteniendo todas las filas de la relación de la derecha. Por ejemplo, el right outer
join de los estudiantes y los cursos se puede expresar como:

```tex
Estudiantes ⟖_{(Estudiantes.Curso = Cursos.Código)} Cursos
```

## Conclusiones

El álgebra relacional es una herramienta poderosa para el manejo de bases de datos relacionales. Permite expresar de
forma clara y concisa las operaciones que se desean realizar sobre los datos, lo que facilita su manipulación y
transformación. Conocer las operaciones básicas y derivadas del álgebra relacional es fundamental para el diseño y la
optimización de consultas en bases de datos relacionales.