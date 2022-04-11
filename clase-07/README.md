# Infografía digital: HTML, SVG y CSS

### Clase 07 → 18/04/2022

Ya hemos revisado:
 
- **SVG**: Un dialecto, muy parecido a HTML, tanto que podría verse así: `<etiqueta atributo="…"></etiqueta>`. Pero estos elementos marcados no son los contenidos en un hipertexto. Estos elementos son las **formas** en un gráfico vectorial; un gráfico que puede inscrustarse en el cuerpo del documento HTML entre etiquetas `<svg></svg>` o también vincularse en el cuerpo del documento HTML como si se tratara de un objeto `<object type="image/svg+xml" data="…"></object>` o una imagen `<img src="…">`.

- **HTML**: Un lenguaje descriptivo que podemos reconocer por sus **elementos** demarcados con `<etiqueta atributo="…"></etiqueta>`.

- **CSS**: Un lenguaje descriptivo que podemos reconocer por sus **reglas** que se estructuran con `selector{propiedad:valor;}`. Estas reglas las podemos encontrar incrustadas en la cabeza del documento HTML, entre etiquetas `<style></style>`, o bien podemos encontrarlas en una hoja de estilo independiente, que se vincula en la cabeza del documento HTML, mediante `<link rel="stylesheet" href="…" />`.

- **JavaScript**: Un lenguaje de programación con el que las páginas web se hacen interactivas mediante el control de cada navegador web y su Modelo de Objetos de Documento (DOM; Document Object Model).

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

Si tenemos un programa de JavaScript con varios datos, podríamos crear en SVG varios círculos, cada uno con un radio determinado por los mismos datos.

Con estos lenguajes, trabajando el conjunto, se pueden hacer cosas mucho más complejas que círculos. Podemos hacer trabajos como en versiones pasadas de este OPR:

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

**En los 12 trabajos vinculados, los estudiantes usaron HTML, CSS y JavaScript, apoyándose en [Bootstrap](https://getbootstrap.com/).** También usaron SVG, pero Bootstrap no se relaciona con tal dialecto (lo mismo pasa con las gráfica en formato JPG, PNG y GIF que pudieron encontrar en los trabajos).

- - - - - - - 

#### Bootstrap

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
                <div class="col-12 my-3">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 200">
                        <rect x="10" y="10" width="480" height="180" fill="#BABABA"/>
                    </svg>
                </div>
                <div class="col-11 col-sm-10 col-md-9 col-lg-8 col-xl-7 col-xxl-6 mx-auto">
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In a dictum elit. Duis suscipit dui et velit egestas ultricies. In porttitor rutrum quam at tincidunt. Praesent tristique nulla nec est finibus, ullamcorper lacinia lectus sollicitudin. Aliquam vel pretium massa. Nulla facilisi. Pellentesque vitae sem est. Maecenas cursus eros dui. Curabitur vehicula suscipit urna. Mauris consectetur tortor at quam luctus, quis sagittis ante cursus. Maecenas bibendum auctor faucibus.</p>
                </div>
            </div>
        </div>
    </body>
</html>
```

El código completo lo podríamos copiar y pegar en un documento creado en su editor de código fuente, documento al que podemos llamar `ejeplo-1.html`.

Creando otro documento, que podemos llamar `ejemplo-2.html`, pongamos a prueba la [propiedad display de Bootstrap](https://getbootstrap.com/docs/5.1/utilities/display/), con ella podemos complementar la fluidez de un SVG:

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
                <div class="col-12 my-3">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 500" class="d-md-none">
                        <rect x="10" y="10" width="180" height="480" fill="#BABABA"/>
                    </svg>
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 500 200" class="d-none d-md-block">
                        <rect x="10" y="10" width="480" height="180" fill="#BABABA"/>
                    </svg>
                </div>
                <div class="col-11 col-sm-10 col-md-9 col-lg-8 col-xl-7 col-xxl-6 mx-auto">
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. In a dictum elit. Duis suscipit dui et velit egestas ultricies. In porttitor rutrum quam at tincidunt. Praesent tristique nulla nec est finibus, ullamcorper lacinia lectus sollicitudin. Aliquam vel pretium massa. Nulla facilisi. Pellentesque vitae sem est. Maecenas cursus eros dui. Curabitur vehicula suscipit urna. Mauris consectetur tortor at quam luctus, quis sagittis ante cursus. Maecenas bibendum auctor faucibus.</p>
                </div>
            </div>
        </div>
    </body>
</html>
```

En el primer SVG tenemos el atributo `class="d-md-none"`, que es una clase que impide que se despliegue desde pantallas medianas (768px). En el segundo SVG tenemos el atributo `class="d-none d-md-block"` con el que se impide su despliegue (`d-none`) a menos que el tamaño de la pantalla ya sea mediano (`d-md-block`).

**Cada gráfica en SVG se adapta, de manera líquida (se ajusta al tamaño gracias al atributo viewBox). Y el par de gráficas ofrece una solución *responsiva* (se muestra una u otra según el tamaño de la pantalla)**.

- - - - - - - 

#### EJERCICIO

[**En el ejercicio mostraremos 5 pasos en un proceso. Cada paso tendrá su gráfica y una breve descripción textual**](https://profesorfaco.github.io/dno075-2022-1/clase-07/). 

Cada gráfica puede ser descargada desde:

- https://www.guemil.info/icons/
- https://visualpharm.com/
- https://www.svgrepo.com/
- https://openmoji.org/library/
- https://icons.getbootstrap.com/

Recuerden revisar los atributos que definen el tamaño de cada SVG descargado; que sí tenga su `viewBox`, que no tenga `height` ni `width`.

Sólo necesitaremos una opción para cada gráfica. Lo "responsive" será el lugar texto: En pantallas grandes se moverá de izquierda a derecha de cada gráfica, pero en pantallas chicas estará siempre debajo de cada gráfica.

Para que no se desarme tanto código, convendría vincular a cada SVG como `<object type="image/svg+xml" data="…"></object>`


- - - - - - - 

#### TAREA

Revisar la página web JavaScript Para Gatos :cat:  

https://jsparagatos.com/


- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-09) 
