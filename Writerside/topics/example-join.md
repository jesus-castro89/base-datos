# Ejemplo de uso de JOIN en MySQL

Tomemos como ejemplo las siguientes tablas:

## Tablas `Autor`

| id_autor | nombre  | nacionalidad |
|----------|---------|--------------|
| 1        | Juan    | Mexicana     |
| 2        | María   | Española     |
| 3        | Pedro   | Colombiana   |
| 4        | Ana     | Argentina    |
| 5        | Daniela | Peruana      |
| 6        | Carlos  | Chilena      |
| 7        | Laura   | Venezolana   |
| 8        | José    | Ecuatoriana  |

## Tabla `Libro`

| id_libro | id_autor | titulo                          | genero | costo |
|----------|----------|---------------------------------|--------|-------|
| 1        | 1        | Cien años de soledad            | Novela | 100   |
| 2        | 6        | Don Quijote de la Mancha        | Novela | 150   |
| 3        | 3        | Crónica de una muerte anunciada | Novela | 220   |
| 4        | 4        | Ficciones                       | Cuento | 325   |
| 5        | 8        | La ciudad y los perros          | Novela | 450   |
| 6        | 6        | Rayuela                         | Novela | 365   |
| 7        | 5        | Los pasos perdidos              | Novela | 287   |
| 8        | 8        | El Aleph                        | Cuento | 198   |

## Tabla `Editorial`

| id_editorial | nombre               | pais           |
|--------------|----------------------|----------------|
| 1            | Alfaguara            | España         |
| 2            | Planeta              | Argentina      |
| 3            | Norma                | Colombia       |
| 4            | Anagrama             | España         |
| 5            | Tusquets             | España         |
| 6            | Seix Barral          | España         |
| 7            | Random House         | Estados Unidos |
| 8            | Penguin Random House | Reino Unido    |

## Tabla `Libro_Editorial`

| id_libro | id_editorial |
|----------|--------------|
| 1        | 8            |
| 2        | 4            |
| 3        | 3            |
| 4        | 4            |
| 5        | 4            |
| 6        | 5            |
| 7        | 6            |
| 8        | 3            |

### Número de libros por autor

Para calcular el promedio de libros por autor, se puede utilizar la siguiente consulta:

```sql
SELECT autor.nombre, COUNT(libro.id_libro) AS libros
FROM autor
INNER JOIN libro ON autor.id_autor = libro.id_autor
GROUP BY autor.nombre;
```

Resultado:

| nombre  | libros |
|---------|--------|
| Juan    | 1      |
| María   | 2      |
| Pedro   | 1      |
| Ana     | 1      |
| Daniela | 1      |
| Carlos  | 2      |

En este caso, se obtiene el promedio de libros por autor contando el número de libros que cada autor ha escrito y
agrupando por el nombre del autor. Tomando en cuenta que hay autores que han escrito más de un libro, se puede observar
que el promedio de libros por autor varía. Por ejemplo, María y Carlos tienen un promedio de 2 libros por autor,
mientras que Juan, Pedro, Ana y Daniela tienen un promedio de 1 libro por autor.

Así mismo podemos notar que existen autores que no han escrito ningún libro, por lo que no aparecen en el resultado de
la consulta. Pero si se desea incluir a todos los autores, se puede utilizar un `LEFT JOIN` en lugar de un `INNER JOIN`:

```sql
SELECT autor.nombre, COUNT(libro.id_libro) AS libros
FROM autor
LEFT JOIN libro ON autor.id_autor = libro.id_autor
GROUP BY autor.nombre;
```

Resultado:

| nombre  | libros |
|---------|--------|
| Juan    | 1      |
| María   | 2      |
| Pedro   | 1      |
| Ana     | 1      |
| Daniela | 1      |
| Carlos  | 2      |
| Laura   | 0      |
| José    | 0      |

En este caso, se incluyen todos los autores en el resultado, incluso aquellos que no han escrito ningún libro. Los
autores que no han escrito ningún libro tienen un valor de `0` en la columna `libros`.

> **Nota:** En la consulta anterior se utiliza la función `COUNT()` para contar el número de libros por autor. La
> función `COUNT()` cuenta el número de filas que cumplen con la condición especificada, en este caso, el número de
> libros escritos por cada autor.

### Promedio de costo de libros por editorial

Para calcular el promedio de costo de los libros por editorial, se puede utilizar la siguiente consulta:

```sql
SELECT editorial.nombre, AVG(libro.costo) AS promedio_costo
FROM editorial
INNER JOIN libro_editorial ON editorial.id_editorial = libro_editorial.id_editorial
INNER JOIN libro ON libro_editorial.id_libro = libro.id_libro
GROUP BY editorial.nombre;
```

Resultado:

| nombre               | promedio_costo |
|----------------------|----------------|
| Anagrama             | 261.5          |
| Norma                | 272.5          |
| Penguin Random House | 324            |
| Planeta              | 325            |
| Seix Barral          | 365            |
| Tusquets             | 287            |

En este caso, se obtiene el promedio de costo de los libros por editorial, calculando el promedio de los costos de los
libros de cada editorial y agrupando por el nombre de la editorial. Se utilizan dos `INNER JOIN` para combinar las
tablas `editorial`, `libro_editorial` y `libro` en función de las claves primarias y foráneas correspondientes.

Sin embargo, si se desea incluir todas las editoriales, incluso aquellas que no tienen libros asociados, se puede
utilizar un `LEFT JOIN` en lugar de un `INNER JOIN`:

```sql
SELECT editorial.nombre, AVG(libro.costo) AS promedio_costo
FROM editorial
LEFT JOIN libro_editorial ON editorial.id_editorial = libro_editorial.id_editorial
LEFT JOIN libro ON libro_editorial.id_libro = libro.id_libro
GROUP BY editorial.nombre;
```

Resultado:

| nombre               | promedio_costo |
|----------------------|----------------|
| Alfaguara            | NULL           |
| Anagrama             | 261.5          |
| Norma                | 272.5          |
| Penguin Random House | 324            |
| Planeta              | 325            |
| Seix Barral          | 365            |
| Tusquets             | 287            |
| Random House         | NULL           |
