# Infografía digital: HTML, SVG y CSS

### Clase 07 → 18/04/2022

Ya hemos revisado:
 
- **[HTML](https://github.com/profesorfaco/dno075-2021-2/wiki/HTML)** es un lenguaje descriptivo que podemos reconocer por sus **elementos** demarcados con `<etiqueta atributo="…"></etiqueta>`.

- **[CSS](https://github.com/profesorfaco/dno075-2021-2/wiki/CSS)** es un lenguaje descriptivo que podemos reconocer por sus **reglas** que se estructuran con `selector{propiedad:valor;}`. Estas reglas las podemos encontrar incrustadas en la cabeza del documento HTML, entre etiquetas `<style></style>`, o bien podemos encontrarlas en una hoja de estilo independiente, que se vincula en la cabeza del documento HTML, mediante `<link rel="stylesheet" href="…" />`.

- **[SVG](https://github.com/profesorfaco/dno075-2021-2/wiki/SVG)** es un dialecto, muy parecido a HTML, tanto que podría verse así: `<etiqueta atributo="…"></etiqueta>`. Pero estos elementos marcados no son los contenidos en un hipertexto. Estos elementos son las **formas** en un gráfico vectorial; un gráfico que puede inscrustarse en el cuerpo del documento HTML entre etiquetas `<svg></svg>` o también vincularse en el cuerpo del documento HTML como si se tratara de un objeto `<object type="image/svg+xml" data="…"></object>` o una imagen `<img src="…">`.

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

- - - - - - - - - - - -

**Existen marcos de trabajo de código abierto que nos pueden ayudar a avanzar más rápido en la construcción de una infografía digital desde relaciones predefinidas de HTML y CSS**. Por su popularidad, corresponde mencionar a:

- [Bootstrap](https://getbootstrap.com/): *The world’s most popular front-end open source toolkit, featuring Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful JavaScript plugins.*

- [Foundations](https://get.foundation/): *The most advanced responsive front-end framework in the world* 

- [Semantic UI](https://semantic-ui.com/): *A development framework that helps create beautiful, responsive layouts using human-friendly HTML*

Hemos trabajado todas clases con [Bootstrap](https://getbootstrap.com/) y esta no será la excepción.

La clave para sacarle un poco más de provecho a [Bootstrap](https://getbootstrap.com/) es relacionarnos con su lógica de clases que se basa en la idea de 12 columnas (`col`) en las que se puede dividir una fila (`row`) que se va ajustando dentro de un contenedor (`container`), una lógica con la que podemos hacer páginas web responsivas.

Digamos que en un contenedor (`container`) quiero dividir la fila (`row`) en dos partes del mismo ancho, para que una se muestre al lado de la otra. Para lograrlo debo tomar 6 y 6 columnas (`col`). Dentro del cuerpo del documento HTML, esto se vería así:

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

La indicación es que desde mediano (a mayor tamaño), tome 6 y 6 columnas. Por defecto, en un tamaño menor se tomarán las 12.

- - - - - - - 

Cuando utilizamos [Bootstrap](https://getbootstrap.com/) nos aprovechamos de [una hoja de estilos CSS](https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.css) que pesa originalmente más de 200 KB (aunque lo común es usar la versión *minified*, que pesa cerca de 160 KB)

Se trata de una hoja de estilo relativamente pesada, que contiene muchísimas definiciones que podríamos llegar a ocupar. Pero, a veces, terminamos utilizando muy pocas. Por ello, si al publicar una infografía digital necesitamos hacer más rápida su carga, podríamo reducir el peso de la hoja de estilos CSS de Boostrap con alguna de las alternativas propuestas en este artículo: https://css-tricks.com/how-do-you-remove-unused-css-from-a-site/

La hoja de estilo de [Bootstrap](https://getbootstrap.com/) también puede complementarse con reglas entre etiquetas `<style></style>`, o en una segunda hoja de estilos independiente, vinculada mediante `<link rel="stylesheet" href="…" />`. 

La primera opción, de incluir nuestras reglas entre `<style></style>` la hemos usado en las clases anteriores, con lo que la cabeza del `index.html` se ve más o menos así:

```
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!-- Primero vinculamos Bootstrap CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KyZXEAg3QhqLMpG8r+8fhAXLRk2vvoC2f3B09zVXn8CA5QIVfZOJ3BCsw2P0p/We" crossorigin="anonymous">
<!-- Luego incrustamos el CSS complementario -->
<style>
header p { text-align: justify; }
header p.lead { line-height: 1.6; }
.card, .card-img-top { border: none; border-radius: 0 0; }
</style>
<title>Escribo acá el título que se muestra en la pestaña del navegador</title>
</head>
```

Pero usando la segunda opción, de una hoja de estilo independiente a la que podríamos llamar `style.css`, la cabeza del `index.html` se vería así:

```
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!-- Primero vinculamos Bootstrap CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KyZXEAg3QhqLMpG8r+8fhAXLRk2vvoC2f3B09zVXn8CA5QIVfZOJ3BCsw2P0p/We" crossorigin="anonymous">
<!-- Luego vinculamos el CSS complementario -->
<link href="style.css" rel="stylesheet">
<title>Escribo acá el título que se muestra en la pestaña del navegador</title>
</head>
```

- - - - - - - 

#### Ejercicio

Lo que queda pendiente es revisar más a fondo al tercero en el trío HTML, CSS y SVG. Para hacerlo, nos aprovecharemos de https://www.guemil.info/icons/

Si revisan la página donde se despliega cada *icon* de manera independiente, encontrarán un botón que les permite descargarlo como SVG. 

Es necesario que descarguen 5 pictogramas que les permitan informar de algo en 5 partes o pasos, [basándose en el documento HTML compartido en esta carpeta de repositorio](https://profesorfaco.github.io/dno075-2022-1/clase-04/).

Completen la información con título y texto introductorio, además de los textos que acompañarán a cada SVG. E intenten resolver dos desafíos:

- Cambiar la manera en que se vinculan los SVG, que no sea como imágenes sino como objetos `<object type="image/svg+xml" data="…"></object>`

- Agreguen una regla de estilo CSS que afecte el `fill` de los `path` en todos los SVG vinculados como objetos. 


- - - - - - - 

#### Tarea

Revisar la página web JavaScript Para Gatos :cat:  

https://jsparagatos.com/


- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-08) 
