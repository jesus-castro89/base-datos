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

| ID_Estudiante | ID_Curso |
|---------------|----------|
| 1             | 101      |
| 1             | 103      |
| 2             | 102      |
| 3             | 104      |
| 4             | 101      |
| 5             | 102      |
| 5             | 103      |

### Operaciones

#### Proyección

La proyección de los nombres de los estudiantes inscritos en algún curso se puede expresar como:

```tex
π_{(Nombre)}(Estudiantes ⨝ Inscripciones)
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

#### Unión

La unión de los estudiantes de Informática y los estudiantes de Matemáticas se puede expresar como:

```tex
Estudiantes_{(Carrera = 'Informática')} ∪ Estudiantes_{(Carrera = 'Matemáticas')}
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
