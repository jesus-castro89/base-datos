# El Modelo Entidad-Relación

El modelo entidad-relación (ER) es un modelo conceptual de datos que permite representar la información de un sistema de
información de manera gráfica. Este modelo se basa en la representación de entidades, atributos y relaciones entre
entidades.

## Componentes del modelo ER

El modelo entidad-relación se compone de los siguientes elementos:

- **Entidades**: objetos o conceptos del mundo real que pueden ser identificados y descritos mediante atributos.
- **Atributos**: propiedades o características de las entidades.
- **Relaciones**: asociaciones entre entidades que representan interacciones o dependencias entre ellas.
- **Claves**: atributos o conjuntos de atributos que permiten identificar de forma única a una entidad.
- **Cardinalidades**: indican la cantidad de instancias de una entidad que pueden estar relacionadas con una instancia
  de otra entidad.
- **Participación**: indica si una entidad debe participar o no en una relación.
- **Restricciones de integridad**: reglas que garantizan la consistencia y validez de los datos en la base de datos.
- **Generalización y especialización**: mecanismos para representar la relación de herencia entre entidades.

## Entidades

Las entidades pueden clasificarse en dos tipos: entidades fuertes y entidades débiles.

<deflist collapsible="true">
    <def title="Entidades Fuertes" default-state="collapsed">
      <p>
        Una entidad fuerte es una entidad que puede existir por sí misma, es decir, no depende de otra entidad para
        existir. Por ejemplo, en un sistema de información de una universidad, las entidades fuertes pueden ser 
        Estudiante, Profesor, Curso, etc.
      </p>
      <p>
        Las entidades fuertes se representan gráficamente mediante un rectángulo con el nombre de la entidad en su
        interior.
      </p>
      <img alt="strong_entity" src="strong_entity.png" />
    </def>
    <def title="Entidades Débiles" default-state="collapsed">
      <p>
        Una entidad débil es una entidad que depende de otra entidad para existir. Por ejemplo, en un sistema de
        información de una biblioteca, la entidad Libro puede ser una entidad débil, ya que depende de la entidad
        Autor para existir.
      </p>
      Las entidades débiles se representan gráficamente mediante un rectángulo inscrito en otro.
      <img alt="weak_entity" src="weak_entity.png"/>
    </def>
</deflist>

## Atributos

Los atributos son las propiedades o características de las entidades. Pueden clasificarse como:

<deflist collapsible="true">
    <def title="Atributo Simple o Monovaluado" default-state="collapsed">
      <p>
        Un atributo simple o monovaluado es un atributo que toma un único valor para cada instancia de la entidad a la que
        pertenece. Por ejemplo, el atributo Nombre de la entidad Estudiante.
      </p>
      Los atributos simples se representan gráficamente mediante un óvalo conectado al rectángulo de la entidad.
      <img alt="simple_attribute" src="simple_attribute.png"/>
    </def>
    <def title="Atributo Multivaluado" default-state="collapsed">
      <p>
        Un atributo multivaluado es un atributo que puede tomar varios valores para cada instancia de la
        entidad a la que pertenece. Por ejemplo, el atributo Dirección de la entidad Estudiante.
      </p>
      Los atributos compuestos se representan gráficamente mediante un rectángulo con sub-óvalos conectados al rectángulo
      de la entidad.
      <img alt="composite_attribute" src="multi_attribute.png"/>
    </def>
    <def title="Atributo Clave o Principal" default-state="collapsed">
        <p>
        Un atributo clave es un atributo o conjunto de atributos que permite identificar de forma única a una entidad. Por
        ejemplo, el atributo Matrícula de la entidad Estudiante.
        </p>
        Los atributos clave se representan gráficamente mediante un óvalo con un subrayado conectado al rectángulo de la
        entidad.
        <img alt="key_attribute" src="key_attribute.png"/>
    </def>
    <def title="Atributo Derivado o Calculado">
        <p>
        Un atributo derivado es un atributo cuyo valor se obtiene a partir de otros atributos de la entidad. Por ejemplo, el
        atributo Edad de la entidad Estudiante, que se puede calcular a partir de la fecha de nacimiento.
        </p>
        Los atributos derivados se representan gráficamente mediante un óvalo punteado conectado al rectángulo de la entidad.
        <img alt="derived_attribute" src="derived_attribute.png"/>
    </def>
    <def title="Atributo Compuesto">
        <p>
        Un atributo compuesto es un atributo que se puede descomponer en subatributos más simples. Por ejemplo, el atributo
        Dirección de la entidad Estudiante, que se puede descomponer en Calle, Número, Colonia, etc.
        </p>
        Los atributos compuestos se representan gráficamente mediante un rectángulo con sub-óvalos conectados al rectángulo
        de la entidad.
        <img alt="composite_attribute" src="composite_attribute.png"/>
    </def>
</deflist>

## Relaciones

Las relaciones representan las asociaciones entre entidades y se representa con un rombo conectado a las entidades
relacionadas. Las relaciones pueden clasificarse según su grado de participación y cardinalidad.

<deflist collapsible="true">
    <def title="Grado de Participación" default-state="collapsed">
        <p>
        El grado de participación de una entidad en una relación indica si la entidad debe participar obligatoriamente o
        no en la relación. Puede ser:
        </p>
        <ul>
            <li>Total: la entidad debe participar obligatoriamente en la relación.</li>
            <li>Parcial: la entidad puede participar opcionalmente en la relación.</li>
        </ul>
    </def>
    <def title="Cardinalidad" default-state="collapsed">
        <p>
        La cardinalidad de una relación indica la cantidad de instancias de una entidad que pueden estar relacionadas con
        una instancia de otra entidad. Puede ser:
        </p>
        <ul>
            <li>Uno a Uno (1:1): una instancia de una entidad se relaciona con una única instancia de otra entidad.</li>
            <li>Uno a Muchos (1:N): una instancia de una entidad se relaciona con varias instancias de otra entidad.</li>
            <li>Muchos a Uno (N:1): varias instancias de una entidad se relacionan con una única instancia de otra entidad.</li>
            <li>Muchos a Muchos (N:M): varias instancias de una entidad se relacionan con varias instancias de otra entidad.</li>
        </ul>
    </def>
</deflist>

## Ejemplo de Modelo ER

A continuación, se muestra un ejemplo de un modelo entidad-relación:

![er-example.png](er-example.png)