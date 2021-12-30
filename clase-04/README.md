# Gráficos con SVG

### Clase 04 → 28/03/2022

En esta clase se abre la segunda etapa del Optativo, donde dependeremos más de lo que se presente aquí, en el README.md. El énfasis de las clases será más práctico.

A través de la práctica partiremos explorando **SVG (Scalable Vector Graphics)**.

**SVG es un dialecto, muy parecido al lenguaje HTML**. Tiene elementos descritos por `<etiqueta atributo="…"></etiqueta>`. Estos elementos son descripciones basadas en posiciones dentro de un plano cuya coordenadas 0,0 se encuentran en su esquina superior izquierda.

En los gráficos vectoriales podemos encontrarnos con lineas rectas, líneas quebradas, círculos, elipses, rectángulos, polígonos simples y trazados complejos, formas que se describen, respectivamente, como sigue:

```
<line x1="0" y1="0" x2="200" y2="200" />

<polyline points="20,20 40,25 60,40 80,120 120,140 200,180" />

<circle cx="50" cy="50" r="40" />

<ellipse cx="50" cy="50" rx="30" ry="50" />

<rect width="50" height="50" />

<polygon points="200,10 250,190 160,210" />

<path d="M150 0 L75 200 L225 200 Z" />
```

Un SVG puede inscrustarse en el cuerpo del documento HTML entre etiquetas `<svg></svg>` o también vincularse en el cuerpo del documento HTML como si se tratara de un objeto `<object type="image/svg+xml" data="…"></object>` o una imagen `<img src="…">`.

- - - - - - - - 

#### EJERCICIO

Pasemos a práctica implementando tres gráficos:

1. Gráfico no figurativo, con [RAWGraphs](https://app.rawgraphs.io/).

2. Gráfico figurativo con [Adobe Illustrator](https://www.adobe.com/la/products/illustrator.html) o [Inkscape](https://inkscape.org/es/).

3. Gráfico mixto que utilice en un capa un gráfico figurativo rasterizado y en otra un gráfico no figurativo vectorizado.

**Los tres gráficos que ustedes implementen deben referir a un único asunto, el que tendrán que desplegar aprovechando [los archivos compartidos en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-04/) de repositorio.**

1. El gráfico no figurativo debe ser incluido en la página como si se tratara de un objeto. 

2. El gráfico figurativo debe ser incluido en la página como si se tratara de una imagen. 

3. El código del SVG del gráfico mixto debe incrustarse directamente en el documento HTML.

- - - - - - - - 

#### TAREA

Revisar este artículo (en inglés): https://css-tricks.com/using-svg/

- - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-03) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-05) 
