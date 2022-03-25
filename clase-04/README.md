# Gráficos con SVG

### Clase 04 → 28/03/2022

En esta clase se abre la segunda etapa del Optativo, donde dependeremos más de lo que se presente aquí, en el README.md. El énfasis de las clases será más práctico.

A través de la práctica partiremos explorando **SVG (Scalable Vector Graphics)**.

**SVG es un dialecto, muy parecido al lenguaje HTML. Tiene [sus propios elementos](https://developer.mozilla.org/es/docs/Web/SVG/Element#elementos_svg_por_categor%C3%ADas) descritos por `<etiquetas></etiquetas>`**. Estos elementos, cuando refieren a gráficos, son descripciones basadas en posiciones dentro de un plano cuya coordenadas 0,0 se encuentran en su esquina superior izquierda.

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

Un SVG completo puede contener una o varias formas, simples o complejas, por lo que puede tener muchas líneas o pocas. El que sigue es un ejemplo de pocas líneas, se trata de un [contenedor octagonal de **Guemil** Icons for Emergency](https://www.guemil.info/81_contain_octagon_v15/):

```
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
<title>81_Contain_octagon_v15</title>
<path d="M30.76,94.7,5.36,69.29A1.9,1.9,0,0,1,4.83,68V32a1.9,1.9,0,0,1,.53-1.25L30.76,5.3A2,2,0,0,1,32,4.78H68a2,2,0,0,1,1.26.52l25.4,25.41A1.9,1.9,0,0,1,95.17,32V68a1.9,1.9,0,0,1-.53,1.25L69.24,94.7a2,2,0,0,1-1.26.52H32A2,2,0,0,1,30.76,94.7Z"></path>
</svg>
```
Noten que el ejemplo comienza y termina con `svg`. Noten también que contiene una única forma, que es un trazado de varios puntos.

Un SVG como el recién presentado puede:

- inscrustarse en el cuerpo del documento HTML, anunciándose con sus etiquetas `<svg></svg>`; 
- vincularse como si se tratara de un objeto `<object type="image/svg+xml" data="…"></object>`; o 
- vincularse como si se tratara de una imagen `<img src="…">`.

Los puntos suspensivos ("…") ocupan el lugar de la ruta al archivo independiente con extensión `svg`.

Para poder verlo funcionar, podemos partir incrustando el SVG en un HTML:

```
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
    <title>¡Hola SVG!</title>
  </head>
  <body>
    <div class="container">
      <div class="row">
        <div class="col-md-7 mx-auto">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
            <title>81_Contain_octagon_v15</title>
            <path d="M30.76,94.7,5.36,69.29A1.9,1.9,0,0,1,4.83,68V32a1.9,1.9,0,0,1,.53-1.25L30.76,5.3A2,2,0,0,1,32,4.78H68a2,2,0,0,1,1.26.52l25.4,25.41A1.9,1.9,0,0,1,95.17,32V68a1.9,1.9,0,0,1-.53,1.25L69.24,94.7a2,2,0,0,1-1.26.52H32A2,2,0,0,1,30.76,94.7Z"></path>
          </svg>
        </div>
      </div>
    </div>
  </body>
</html>
```

Luego podríamos tomar lo que hay entre etiquetas `<svg>…</svg>`, incluyéndolas, para llevarlas a un nuevo documento que podemos guardar con la extensión `.svg`. Y podríamos vincularlo al documento `.html` como objeto y como imagen.

- - - - - - - - 

#### EJERCICIO

Pasemos a práctica implementando tres gráficos:

1. Gráfico no figurativo, con [RAWGraphs](https://app.rawgraphs.io/).

2. Gráfico figurativo con [Adobe Illustrator](https://www.adobe.com/la/products/illustrator.html) o [Inkscape](https://inkscape.org/es/), partiendo desde algún gráfico que podrían tomar de https://visualpharm.com/ o https://www.guemil.info/icons/

3. Gráfico figurativo que utilice dos capas, una rasterizada y otra vectorizada.

**Los tres gráficos que ustedes implementen deben referir a un único asunto, el que tendrán que desplegar aprovechando [los archivos compartidos en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-04/) de repositorio.**

1. El gráfico no figurativo debe ser incluido en la página como si se tratara de un objeto. 

2. El gráfico figurativo debe ser incluido en la página como si se tratara de una imagen. 

3. El código del SVG del gráficos de dos capas debe incrustarse directamente en el documento HTML.

- - - - - - - - 

#### TAREA

Revisar este artículo (en inglés): https://css-tricks.com/using-svg/

- - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-03) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-05) 
