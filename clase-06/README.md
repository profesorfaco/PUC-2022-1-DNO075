# Gráficos con SVG, CSS y JavaScript

### Clase 06 → 11/04/2022

**JavaScript es un lenguaje de programación con el que las páginas web se hacen interactivas mediante el control de cada navegador web y su Modelo de Objetos de Documento ([DOM; Document Object Model](https://es.wikipedia.org/wiki/Document_Object_Model))**: Con JavaScript se controla, a través de pequeños programas (o *scripts*), la "comprensión de lectura" del navegador web. Por este motivo pueden haber diferencias entre **ver código fuente** e [**inspeccionar elementos**](https://support.hostinger.es/es/articles/2333029-como-inspeccionar-los-elementos-del-sitio-web).

Dominar JavaScript, o cualquier lenguaje de programación, toma más tiempo de estudio y práctica del que puede tomarnos dominar un lenguaje o un dialecto de descripción. Esto no solo aplica a diseñadores, también aplica a programadores; por esta razón, es común que expertos en programación usen *libraries* y *frameworks*, pero nunca *plugins*:

- una *library* ofrece ingredientes seleccionados y preparados para que "cocines" un plato específico con el menor esfuerzo posible. 

- un *framework* es una cocina dispuesta para que prepares un tipo de comida específica, con eficacia y eficiencia (una cocina de restaurant que ofrece sushi es distinta de una de restaurant de pastas o parrilladas).

- un *plugin* es un truco ciego: *No sé qué ni cómo lo hice. Pero creo que es comestible* ¡No es recomendable usarlos!

Estiremos la metáfora de la cocina: Si no sabemos hervir agua ni diferenciar sal de azúcar, difícilmente podemos sacar provecho de cualquier ayuda para cocinar.

Por eso vamos a partir con un pequeño programa (o *script*), que debes copiar y pegar [en la consola de JavaScript](https://wise.com/es/help/articles/2954851/como-abrir-la-consola-de-tu-navegador) de tu navegador:

```
var retinal = ["size","value","texture","color","orientation","shape"];
retinal.sort();
retinal.forEach(element => console.log(element));
```

En las tres línea del pequeño programa (o *script*) tenemos: 

1. Una declaración de variable de nombre `retina`, que se inicia conteniendo un arreglo (*array*) con 6 cadenas (*string*) de caracteres entre comillas.

2. Una reorganización alfabética del arreglo contenido por la variable de nombre `retina`, mediante el [método `sort()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

3. Con el [método `forEach()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) se repite un *log* en la consola **para cada** cadena (*string*) en el arreglo (*array*) ya ordenado alfabéticamente.

**Si vinculamos lo recién dicho con lo presentado en las clases recién pasada, ya podríamos preguntarnos: ¿Es posible vincular datos a elementos dentro de un SVG? ¡Si, es posible!**

Veamos como es posible, sin alejarnos del pequeño programa (o *script*) escrito más arriba. Copiemos y peguemos lo que sigue en un nuevo documento creado en un editor de código fuente. Una vez pegado allí, guardemos el documento como `ejemplo-1.html`

```
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>¡Guárdalo como HTML!</title>
    </head>
    <body>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 200">
            <g id="aqui"></g>
        </svg>
        <script>
            var retinal = ["size", "value", "texture", "color", "orientation", "shape"];
            retinal.sort();
            retinal.forEach(function (r, n) {
                document.querySelector("#aqui").innerHTML += '<text x="50" y="' + 20 * (n + 1) + '">' + r + "</text>";
            });
        </script>
    </body>
</html>
```

Si revisan el `ejemplo-1.html` en su navegador, verán cada cadena de caracteres del arreglo dentro de un `<text></text>` de SVG. Todos ellos están, a su vez, dentro del grupo de identidad `aqui` (`<g id="aqui"></g>`). 

Esto es algo que también pueden ver al [**inspeccionar elementos**](https://support.hostinger.es/es/articles/2333029-como-inspeccionar-los-elementos-del-sitio-web). Pero no lo encontrarás al "Ver el código fuente", porque JavaScript no modifica lo escrito por el programador, sino la "comprensión de lectura" que tiene el navegador web para lo que lee.


Demos un paso más creando un nuevo documento al que llamaremos `ejemplo-2.html`. Allí peguemos el siguiente código:

```
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>¡Guárdalo como HTML!</title>
    </head>
    <body>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 250">
            <g id="aqui"></g>
        </svg>
        <script>
            var personajes = [
                { nombre: "Marge", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/marge.svg" },
                { nombre: "Homer", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/homer.svg" },
                { nombre: "Bart", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/bart.svg" },
                { nombre: "Lisa", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/lisa.svg" },
                { nombre: "Maggie", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/maggie.svg" }
            ];
            personajes.forEach((p, n) => {
                document.getElementById("aqui").innerHTML += '<image width="200" height="200" x="'+ n * 200+'" y ="10" href="'+p.imagen+'"></image><text width="200" height="50" x="'+ ((n * 200) + 100) +'" y ="240" text-anchor="middle" font-size="2em">'+ p.nombre +'</text>';
            });
        </script>
    </body>
</html>
```

En el `ejemplo-1.html` tenemos una variable de nombre `retinal` en la que guardamos un arreglo, siendo cada elemento del arreglo una cadena de caracteres. En el `ejemplo-2.html` también tenemos una variable en la que guardamos un arreglo, pero cada elemento del arreglo en `personajes` es un objeto donde los índices son `nombre` e `imagen`, y lo que guarda cada índice es una cadena de caracteres.

Podrán notar otras diferencias entre los ejemplos 1 y 2: 

- `retinal.forEach(function (r, n) {…});` hace lo mismo que `personajes.forEach((p, n) => {…});`
- `document.querySelector("#aqui")` hace lo mismo que `document.getElementById("aqui")`

En este caso estamos trabajando con un lenguaje de programación, distinto de un lenguaje o un dialecto de descripción. Lo descriptivo y lo programático es estrictos. Pero lo descriptivo es más conservador cuando lo programático tiende a evolucionar frecuentemente: Se proponen y estandarizan maneras más eficientes de "hacer".

También podrían preguntarse: ¿Puedo mezclar ambos ejemplo para hacer un `ejemplo-3.html`, donde tenga un listado de palabras y también a los Simpsons? La respuesta es sí. Para hacerlo deben cuidarse de la repetición de identidades, porque una identidad sólo se usa una vez dentro de una página:

```
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>¡Guárdalo como HTML!</title>
    </head>
    <body>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 200">
            <g id="aca"></g>
        </svg>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 250">
            <g id="alla"></g>
        </svg>
        <script>
            var retinal = ["size", "value", "texture", "color", "orientation", "shape"];
            retinal.sort();
            retinal.forEach(function (r, n) {
                document.querySelector("#aca").innerHTML += '<text x="50" y="' + 20 * (n + 1) + '">' + r + "</text>";
            });
             var personajes = [
                { nombre: "Marge", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/marge.svg" },
                { nombre: "Homer", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/homer.svg" },
                { nombre: "Bart", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/bart.svg" },
                { nombre: "Lisa", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/lisa.svg" },
                { nombre: "Maggie", imagen: "https://raw.githubusercontent.com/profesorfaco/dno075-2022-1/main/clase-06/img/maggie.svg" }
            ];
            personajes.forEach((p, n) => {
                document.getElementById("alla").innerHTML += '<image width="200" height="200" x="'+ n * 200+'" y ="10" href="'+p.imagen+'"></image><text width="200" height="50" x="'+ ((n * 200) + 100) +'" y ="240" text-anchor="middle" font-size="2em">'+ p.nombre +'</text>';
            });
        </script>
    </body>
</html>
```

- - - - - - - 

#### EJERCICIO

**Hay un documento [compartido en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-06/) de repositorio: Un `index.html` que contiene un arreglo con datos del CENSO 2017**. 

Para su entrega, generen otro gráfico de barras con otros datos de [la síntesis de resultados del Censo 2017](https://www.censo2017.cl/descargas/home/sintesis-de-resultados-censo2017.pdf).

Además suban los tres ejemplos que pudieron preparar dentro de la misma carpeta de repositorio.


- - - - - - - 
 
#### TAREA

Revisar en YouTube el primer video de HTML y CSS curso práctico 💪 Desde cero [Tutorial Español]

https://youtu.be/rr2H086z16s

- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-05) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-07) 

