# Gráficos con SVG

### Clase 04 → 28/03/2022

En esta clase se abre la segunda etapa del Optativo, donde dependeremos más de lo que se presente aquí, en GitHub y no tanto lo que se presente en una clase lectiva. Con esto el énfasis de las clases se hace más práctico. 

El material de consulta principal:

- Cairo, A. (2011). El arte funcional. Infografía y visualización de información. Alamut.

Y el material complementario:

- Boehm, G. (2020). ¿Más allá del lenguaje? Apuntes sobre la lógica de las imágenes. En: Ana García Varas (Ed.) Filosofía de la imagen (pp.87-106). Ediciones Universidad Salamanca.

A tal manterial corresponde agregar todo lo que sigue sobre **SVG (Scalable Vector Graphics)**. 

**SVG es un dialecto, muy parecido al lenguaje HTML**. Tiene elementos descritos por `<etiqueta atributo="…"></etiqueta>`. Estos elementos son descripciones de gráficos vectoriales.

Entre los gráficos vectoriales podemos encontrarnos con lineas rectas, líneas quebradas, círculos, elipses, rectángulos, polígonos simples y trazados complejos, formas que serán descritas con los atributos correspondientes a su geometría:

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

Para aplicar lo aprendido, implementaremos tres gráficos:

1. Gráfico no figurativo, con [RAWGraphs](https://app.rawgraphs.io/).

2. Gráfico figurativo con [Adobe Illustrator](https://www.adobe.com/la/products/illustrator.html) o [Inkscape](https://inkscape.org/es/).

3. Gráfico mixto que utilice en un capa un gráfico figurativo rasterizado y en otra un gráfico no figurativo vectorizado.

- - - - - - - - 

#### TAREA



- - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-03) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-05) 
