# Infografía digital: HTML, SVG y CSS

### Clase 07 → 18/04/2022

Ya hemos revisado:
 
- **SVG**: Un dialecto, muy parecido a HTML, tanto que podría verse así: `<etiqueta atributo="…"></etiqueta>`. Pero estos elementos marcados no son los contenidos en un hipertexto. Estos elementos son las **formas** en un gráfico vectorial; un gráfico que puede inscrustarse en el cuerpo del documento HTML entre etiquetas `<svg></svg>` o también vincularse en el cuerpo del documento HTML como si se tratara de un objeto `<object type="image/svg+xml" data="…"></object>` o una imagen `<img src="…">`.

- **HTML**: Un lenguaje descriptivo que podemos reconocer por sus **elementos** demarcados con `<etiqueta atributo="…"></etiqueta>`.

- **CSS**: Un lenguaje descriptivo que podemos reconocer por sus **reglas** que se estructuran con `selector{propiedad:valor;}`. Estas reglas las podemos encontrar incrustadas en la cabeza del documento HTML, entre etiquetas `<style></style>`, o bien podemos encontrarlas en una hoja de estilo independiente, que se vincula en la cabeza del documento HTML, mediante `<link rel="stylesheet" href="…" />`.


Los dos lenguajes (HTML y CSS) y el dialecto (SVG) se pueden combinar para obtener, por ejemplo, una página con fondo rojo que contenga un SVG que, a su vez, contenga un círculo negro al centro:

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>Muy simple</title>
        <style>
            body {
                background: red;
            }
        </style>
    </head>
    <body>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 100"><circle cx="100" cy="50" r="25" /></svg>
    </body>
</html>
```

Pero se pueden hacer cosas mucho más complejas, como los trabajos realizados en versiones pasadas de este OPR:

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

**En los 12 trabajos vinculados, los estudiantes usaron HTML, SVG y CSS, apoyándose en [Bootstrap](https://getbootstrap.com/).**

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

En cada ejercicio desarrollado hasta esta clase, nos hemos aprovechado de esta misma lógica, sin prestarle tanta atención.

- - - - - - - 

#### EJERCICIO

Lo que queda pendiente es revisar más a fondo al tercero en el trío HTML, CSS y SVG. Para hacerlo, nos aprovecharemos de https://www.guemil.info/icons/

Si revisan la página donde se despliega cada *icon* de manera independiente, encontrarán un botón que les permite descargarlo como SVG. 

**Es necesario que descarguen 5 pictogramas que les permitan informar de algo en 5 partes o pasos, [basándose en el documento HTML compartido en esta carpeta de repositorio](https://profesorfaco.github.io/dno075-2022-1/clase-07/)**.

Completen la información con título y texto introductorio, además de los textos que acompañarán a cada SVG. E intenten resolver dos desafíos:

- Cambiar la manera en que se vinculan los SVG, que no sea como imágenes sino como objetos `<object type="image/svg+xml" data="…"></object>`

- Agreguen una regla de estilo CSS que afecte el `fill` de los `path` en todos los SVG vinculados como objetos. 


- - - - - - - 

#### TAREA

Revisar la página web JavaScript Para Gatos :cat:  

https://jsparagatos.com/


- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-09) 
