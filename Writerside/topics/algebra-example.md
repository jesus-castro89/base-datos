# Ejemplo de aplicación de álgebra relacional

El álgebra relacional es un lenguaje formal para manipular relaciones en una base de datos. Permite realizar operaciones
como proyección, selección, unión, intersección, diferencia, producto cartesiano y división, entre otras.

Supongamos que tenemos las siguientes relaciones en una base de datos de una universidad:

## Estudiantes

| ID | Nombre | Carrera     |
|----|--------|-------------|
| 1  | Juan   | Informática |
| 2  | María  | Matemáticas |
| 3  | Pedro  | Física      |
| 4  | Ana    | Informática |
| 5  | Luis   | Matemáticas |

## Cursos

| ID  | Nombre         | Créditos |
|-----|----------------|----------|
| 101 | Álgebra Lineal | 4        |
| 102 | Cálculo I      | 5        |
| 103 | Programación   | 6        |
| 104 | Física I       | 4        |

## Inscripciones

| ID_Inscripción | ID_Curso | ID_Estudiante |
|----------------|----------|---------------|
| 1              | 101      | 1             |
| 1              | 103      | 3             |
| 2              | 102      | 5             |
| 3              | 104      | 2             |
| 4              | 101      | 4             |
| 5              | 102      | 1             |
| 5              | 103      | 3             |

### Operaciones

#### Proyección

La proyección de los nombres de los estudiantes inscritos en algún curso se puede expresar como:

```tex
π_{Nombre}(Estudiantes)
```

Resultado:

| Nombre |
|--------|
| Juan   |
| María  |
| Pedro  |

#### Selección

La selección de los cursos con más de 4 créditos se puede expresar como:

```tex
σ_{(Créditos > 4)}(Cursos)
```

Resultado:

| ID  | Nombre       | Créditos |
|-----|--------------|----------|
| 102 | Cálculo I    | 5        |
| 103 | Programación | 6        |

Las operaciones de selección y proyección se pueden combinar para obtener los nombres de los estudiantes inscritos en
cursos con más de 4 créditos:

```tex
π_{Nombre}(Estudiantes ⨝ Inscripciones ⨝_{(ID_Curso = ID)} σ_{(Créditos > 4)}(Cursos))
```

Así mismo las condiciones de selección pueden usar las operaciones de comparación:

* `=`: Igual a
* `≠`: Diferente de
* `>`: Mayor que
* `<`: Menor que
* `>=`: Mayor
* `<=`: Menor o igual

Y también pueden unirse más de dos condiciones con los operadores lógicos `∧` (Conjunción o Y) y `∨` (Disyunción ó O).

```tex
π_{nombre}(σ_{(carrera='Matemáticas' ∨ carrera='Física')}(Estudiante))
```

#### Unión

La unión de los estudiantes de Informática y los estudiantes de Matemáticas se puede expresar como:

```tex
σ_{(carrera='Matemáticas')}(Estudiante) ∪ σ_{(carrera='Informática')}(Estudiante)
```

Resultado:

| ID | Nombre | Carrera     |
|----|--------|-------------|
| 1  | Juan   | Informática |
| 4  | Ana    | Informática |
| 2  | María  | Matemáticas |
| 5  | Luis   | Matemáticas |

#### Join

El join de los estudiantes inscritos en algún curso con los cursos se puede expresar como:

```tex
Estudiantes ⨝_{(ID = ID_Estudiante)} Inscripciones ⨝_{(ID_Curso = ID)} Cursos
```

Resultado:

| ID | Nombre | Carrera     | ID_Estudiante | ID_Curso | Nombre         | Créditos |
|----|--------|-------------|---------------|----------|----------------|----------|
| 1  | Juan   | Informática | 1             | 101      | Álgebra Lineal | 4        |    
| 1  | Juan   | Informática | 1             | 103      | Programación   | 6        |
| 2  | María  | Matemáticas | 2             | 102      | Cálculo I      | 5        |
| 3  | Pedro  | Física      | 3             | 104      | Física I       | 4        |
| 4  | Ana    | Informática | 4             | 101      | Álgebra Lineal | 4        |
| 5  | Luis   | Matemáticas | 5             | 102      | Cálculo I      | 5        |
| 5  | Luis   | Matemáticas | 5             | 103      | Programación   | 6        |

#### Intersección

La intersección entre los estudiantes de Informática y los estudiantes de Matemáticas se puede expresar como:

```tex
Estudiantes_{(Carrera = 'Informática')} ∩ Estudiantes_{(Carrera = 'Matemáticas')}
```

Resultado:

| ID | Nombre | Carrera     |
|----|--------|-------------|
| 1  | Juan   | Informática |
| 4  | Ana    | Informática |
| 2  | María  | Matemáticas |
| 5  | Luis   | Matemáticas |

#### Diferencia

La diferencia entre los estudiantes de Informática y los estudiantes de Matemáticas se puede expresar como:

```tex
Estudiantes_{(Carrera = 'Informática')} - Estudiantes_{(Carrera = 'Matemáticas')}
```

Resultado:

| ID | Nombre | Carrera |
|----|--------|---------|
| 3  | Pedro  | Física  |

#### Producto Cartesiano

El producto cartesiano entre los estudiantes y los cursos se puede expresar como:

```tex
Estudiantes × Cursos
```

Resultado:

| ID | Nombre | Carrera     | ID  | Nombre         | Créditos |
|----|--------|-------------|-----|----------------|----------|
| 1  | Juan   | Informática | 101 | Álgebra Lineal | 4        |
| 1  | Juan   | Informática | 102 | Cálculo I      | 5        |
| 1  | Juan   | Informática | 103 | Programación   | 6        |
| 1  | Juan   | Informática | 104 | Física I       | 4        |
| 2  | María  | Matemáticas | 101 | Álgebra Lineal | 4        |
| 2  | María  | Matemáticas | 102 | Cálculo I      | 5        |
| 2  | María  | Matemáticas | 103 | Programación   | 6        |
| 2  | María  | Matemáticas | 104 | Física I       | 4        |
| 3  | Pedro  | Física      | 101 | Álgebra Lineal | 4        |
| 3  | Pedro  | Física      | 102 | Cálculo I      | 5        |
| 3  | Pedro  | Física      | 103 | Programación   | 6        |

## Conclusiones