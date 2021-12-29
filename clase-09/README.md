# Infografía digital: HTML, SVG, CSS y JavaScript

### Clase 09 → 09/05/2022

**Hemos revisado tres lenguajes y un dialecto. Entre los tres lenguajes, uno es de programación. Los demás lenguajes, y el dialecto, son de descripción. Los cuatro, trabajando en conjunto, nos permiten desarrollar infografías digitales.**

La próxima semana tendremos una evaluación individual, y a la siguiente comenzaremos un trabajo grupal que iría por misma línea de las versiones anteriores del curso.

A continuación, pueden encontrar vínculo a 3 trabajos de cada versión pasada de este OPR:

VULNERABILIDADES Y DESASTRES SOCIONATURALES EN CHILE:

- https://infodigitalgrupo.github.io/infografia-final/
- https://fallasanramon-infografiadigital.github.io/entrega_final/
- https://infografia-digital.github.io/rinihuazo-final/

FAUNA ENDÉMICA DE CHILE:

- https://arana-pollito.github.io/Implementacion/
- https://aves-de-juan-fernandez.github.io/Picaflor-Entrega-Final/
- https://zorrodechiloe-infodigital.github.io/Zorro_de_Chiloe/

CONFLICTOS SOCIOAMBIENTALES:

- https://personas-de-sacrificio.github.io/examen/
- https://paltorcas.github.io/examen/
- https://litidos.github.io/Examen/

A los trabajos recién vinculados, podemos agregar algunos trabajos de estudiantes del diplomado de infografía en Diseño UC, versión 2021-2022.

- https://siamang-infografia.github.io/final/
- https://hipopotamo-pigmeo.github.io/final/
- https://orangutan-borneo-uc.github.io/final/

**En los 12 trabajos vinculados, los estudiantes usaron HTML, SVG, CSS y JavaScript, apoyándose en Bootstrap.**

Así como [Foundations](https://get.foundation/) y [Semantic UI](https://semantic-ui.com/), **[Bootstrap](https://getbootstrap.com/) es un marco de trabajo  que simplifica la creación de páginas responsivas**; escogemos Bootstrap por su popularidad y constante desarrollo.

Para sacarle un mejor provecho a [Bootstrap](https://getbootstrap.com/), lo primero es relacionarse con la lógica de las 12 columnas (`col`) en las que se puede dividir una fila (`row`) que se va ajustando dentro de un contenedor (`container`), porque esta es la lógica con la que [Bootstrap](https://getbootstrap.com/) se adapta a distintos tamaños de pantalla.

Digamos que en este contenedor (`container`) quiero dividir la fila (`row`) en dos partes del mismo ancho, para que una se muestre al lado de la otra. Para lograrlo debo tomar 6 y 6 columnas (`col`). Dentro del cuerpo del documento HTML, esto se vería así:

```
<div class="container">
    <div class="row">
        <div class="col-6">Primera división</div>
        <div class="col-6">Segunda división</div>
    </div>
</div>
```

Ahora, quiero hacer la misma división pero sólo desde una pantalla mediana ([mayor a 768px de ancho](https://getbootstrap.com/docs/5.0/layout/breakpoints/#available-breakpoints)). En las pantallas que tengan un ancho menor, ambas divisiones ocuparán todo el ancho, poniéndose la segunda debajo de la primera:

```
<div class="container">
    <div class="row">
        <div class="col-md-6">Primera división</div>
        <div class="col-md-6">Segunda división</div>
    </div>
</div>
```

Cambiemos de ejemplo, considerando que Robert Bringhurst (2008) escribe:

> La cantidad que se considera satisfactoria como longitud de línea para una página de una sola columna compuesta en una fuente con remates va entre 45 u 75 caracteres. La línea de 66 caracteres (contando tanto las letras como los espacios en blanco) se considera ideal. Para un trabajo de varias columnas, 40 a 50 caracteres es un buen promedio.

Podríamos necesitar una imagen a todo lo ancho de la fila dentro del contenedor, y bajo ella un párrafo centrado que utilice menos columnas en la medida que éstas se ensanchan junto a la pantalla, así mantener una anchura de párrafo cómoda a la lectura. El código del documento completo debería verse así:

```
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous" />
        <title>Hola mundo</title>
    </head>
    <body>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <img src="https://picsum.photos/1600/900?grayscale" class="w-100 my-4" alt="esta es una imagen random" />
                </div>
                <div class="col-11 col-sm-10 col-md-9 col-lg-8 col-xl-7 col-xxl-6 mx-auto">
                    <p>
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla in molestie felis, eget egestas lacus. Etiam orci magna, dignissim at dolor eu, finibus molestie mi. Suspendisse fringilla sem magna, eget pharetra orci
                        faucibus sit amet.
                    </p>
                </div>
            </div>
        </div>
    </body>
</html>
```

En cada ejercicio desarrollado nos hemos aprovechado de esta misma lógica, sin prestarle tanta atención.

- - - - - - - - - - - - -


###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-07) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-10) 
