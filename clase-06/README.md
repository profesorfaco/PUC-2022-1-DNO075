# Gráficos con SVG, CSS y JavaScript

### Clase 06 → 11/04/2022

**[JavaScript](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/What_is_JavaScript) es un lenguaje de programación con el que las páginas web se hacen interactivas mediante el control de cada navegador y su Modelo de Objetos de Documento ([DOM; Document Object Model](https://es.wikipedia.org/wiki/Document_Object_Model))**. Si lo simplificamos: Con JavaScript se controla la "comprensión de lectura" del navegador web.

Dominar JavaScript, o cualquier lenguaje de programación, toma más tiempo de estudio y práctica del que puede tomarnos dominar un lenguaje o un dialecto de descripción. Esto aplica también para programadores; por esta razón es común que expertos en programación usen *libraries* y *frameworks*, pero es raro que confiesen el uso de *plugins*:

- una *library* ofrece algo como ingredientes seleccionados y preparados para que cocines un plato específico con el menor esfuerzo posible. 

- un *framework* es como una cocina dispuesta para que prepares un tipo de comida específica (una cocina de restaurant que ofrece sushi es distinta de una de restaurant de pastas o parrilladas).

- un *plugin* es una solución ajena y hermética: *No sé quién lo hizo ni cómo lo hizo, pero creo que es comestible*. Con una confesión de ese tipo, ningún cocinero mantendría su trabajo en un buen restaurant.

Sigamos estirando la metáfora de la cocina: Si no sabemos hervir agua ni diferenciar sal de azúcar, difícilmente podemos sacar provecho de cualquier ayuda para cocinar hasta lo más simple: *¡No podríamos preparar ni un tecito!*

**Para poder preparar algo como un tecito, vamos a partir con un pequeño programa (o *script*). Tenemos que copiar y pegar [en la consola de JavaScript](https://wise.com/es/help/articles/2954851/como-abrir-la-consola-de-tu-navegador) del navegador web lo siguiente**: 

```
var retinal = ["size","value","texture","color","orientation","shape"];
retinal.sort();
retinal.forEach(x => console.log(x));
```

**En las tres línea del pequeño programa (o *script*) tenemos**: 

1. Una declaración de variable de nombre `retina`, que se inicia conteniendo un arreglo (*array*) con 6 cadenas (*string*) de caracteres entre comillas.

2. Una reorganización alfabética del arreglo contenido por la variable de nombre `retina`, mediante el [método `sort()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/sort).

3. Con el [método `forEach()`](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) se repite un *log* en la consola **para cada** cadena (*string*) en el arreglo (*array*) ya ordenado alfabéticamente.

**Modifiquemos la tercera línea del pequeño programa (*script*), y pongámoslo dentro de un HTML al que podemos guardar con el nombre `ejemplo-1.html`**:

```
<!DOCTYPE html>
<html lang="es">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>¡Guárdalo como HTML!</title>
    </head>
    <body>
        <script>
            var retinal = ["size","value","texture","color","orientation","shape"];
            retinal.sort();
            retinal.forEach(x => document.querySelector("body").innerHTML += '<p>'+ x +'</p>');
        </script>
    </body>
</html>
```

Con los cambios de la tercera línea se le pide al navegador hacer lo siguiente para cada cadena (*string*) en el arreglo (*array*) ya ordenado alfabéticamente:

- `document.querySelector("body")` Busca en el documento al elemento `body`.
- `.innerHTML` Incluye algo de HTML en el elemento que ya fuiste a buscar.
- `+=` Esto es lo que te corresponde incluir (sin borrar lo anterior).
- `'<p>'+ x +'</p>'` Antes de cada `x` pon un etiqueta de apertura de párrafo y después una de cierre (de tal manera el HTML que se incluye cada vez es un párrafo).

**Si vinculamos lo recién presentado con lo aprendido sobre [SVG](https://developer.mozilla.org/es/docs/Web/SVG/Tutorial) (que es un dialecto con elementos, muy parecido a [HTML](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/HTML_basics)), ya podríamos sospechar que es posible dibujar un SVG desde una serie de datos; veamos como se puede hacer esto sin alejarnos del pequeño programa (o *script*) que venimos usando**. 

Copiemos y peguemos lo que sigue en un nuevo documento creado en un editor de código fuente. Una vez pegado allí, guardemos el documento como `ejemplo-2.html`

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
                document.querySelector("#aqui").innerHTML += '<text x="50" y="' + 20 * (n + 1) + '">' + r + '</text>';
            });
        </script>
    </body>
</html>
```

Si revisan el `ejemplo-2.html` en su navegador, verán cada cadena de caracteres del arreglo dentro de un `<text></text>` de SVG. Todos ellos están, a su vez, dentro del grupo de identidad `aqui` (`<g id="aqui"></g>`). 

Esto es algo que también pueden ver al [**inspeccionar elementos**](https://support.hostinger.es/es/articles/2333029-como-inspeccionar-los-elementos-del-sitio-web). Pero no lo encontrarás al "Ver el código fuente", porque JavaScript no modifica lo escrito por el programador, sino la "comprensión de lectura" que tiene el navegador web para lo que lee.

Demos un paso más creando un nuevo documento, al que llamaremos `ejemplo-3.html`. Allí peguemos el siguiente código:

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

En los ejemplos 1 y 2 tenemos una variable de nombre `retinal` en la que guardamos un arreglo, siendo cada elemento del arreglo una cadena de caracteres. En el `ejemplo-3.html` también tenemos una variable en la que guardamos un arreglo, pero cada elemento del arreglo en `personajes` es un objeto donde los índices son `nombre` e `imagen`, y lo que guarda cada índice es una cadena de caracteres.

Podrán notar otras diferencias entre los ejemplos 2 y 3: 

- `retinal.forEach(function (r, n) {…});` hace lo mismo que `personajes.forEach((p, n) => {…});`
- `document.querySelector("#aqui")` hace lo mismo que `document.getElementById("aqui")`

En este caso estamos trabajando con JavaScript, que es un lenguaje de programación, distinto de un lenguaje o un dialecto de descripción (HTML, CSS, SVG). Lo descriptivo debe ser tan estricto como lo programático. Pero lo descriptivo es conservador comparado con lo programático que [tiende a evolucionar frecuentemente](https://www.w3schools.com/js/js_versions.asp): Se proponen y estandarizan maneras de "hacer" más eficientes.

También podrían preguntarse: ¿Puedo mezclar ambos ejemplo para hacer un `ejemplo-4.html`, donde tenga un listado de palabras y también a los Simpsons? La respuesta es sí. Para hacerlo deben cuidarse de la repetición de identidades, porque una identidad sólo se usa una vez dentro de un documento:

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

**Usaremos sólo uno de los documentos [compartidos en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-06/) de repositorio**: 

**El [`index.html`](https://github.com/profesorfaco/dno075-2022-1/blob/main/clase-06/index.html) que contiene un arreglo con datos del CENSO 2017**. 



Para su entrega, cambien los datos para presentar otro asunto incluido en [la síntesis de resultados del Censo 2017](https://www.censo2017.cl/descargas/home/sintesis-de-resultados-censo2017.pdf). También corresponde modificar el título, subtítulo y párrafos de texto.

También podrán subir los cuatro ejemplos que prepararon en la misma carpeta de repositorio.

- - - - - - - 
 
#### TAREA

Revisar en YouTube el primer video de HTML y CSS curso práctico 💪 Desde cero [Tutorial Español]

https://youtu.be/rr2H086z16s

- - - - - - - -

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-05) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-07) 

