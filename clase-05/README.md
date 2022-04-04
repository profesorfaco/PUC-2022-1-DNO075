# Gráficos con SVG y CSS

### Clase 05 → 04/04/2022

**[CSS](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/CSS_basics)** (Cascading Style Sheets) es un lenguaje descriptivo que podemos reconocer por sus **reglas**, que se estructuran con: 

```
selector{
 propiedad:valor;
 propiedad:valor;
 propiedad:valor;
}
```

Un documento [SVG](https://developer.mozilla.org/es/docs/Web/SVG/Tutorial) puede contener a tal lenguaje, entre etiquetas `<style></style>`.

Cuando usamos Illustrator para guardar una gráfica (figurativa, no figurativa o mixta) como un SVG, el programa genera automáticamente tantas **reglas de [CSS]((https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/CSS_basics))** como sean necesarias para describir el aspecto de los elementos gráficos que contiene el SVG.

Los selectores de las **reglas de [CSS]((https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/CSS_basics))** generadas por Illustrator son [selectores de clase](https://developer.mozilla.org/es/docs/Web/CSS/Class_selectors). Estos comienzan con un punto pegado a un `st`, a lo que se agregar un número: `.st0{…}`, `.st1{…}`, `.st2{…}`, etc.

El selector de clase se identifica en el CSS por el punto inmediatamente anterior al nombre. Y así como Illustrator nombra a una clase `.st0{}`, nosotros podríamos llamarle `.primera{}`, o `.como_se_nos_ocurra{}`, NUNCA iniciando tal nombre con un número ni usando palabras separadas. Luego, si queremos que un elemento sea afectado por un selector de clase, el elemento debe utilizar la clase que lo seleccionará.

Revisemos lo recién presentado en el siguiente código generado por Adobe Illustrator, noten como entre etiquetas `<style></style>` tenemos un punto antecediendo al nombre de clase, y más abajo tenemos a los nombres de clase como valores de un atributo de clase (`class="…"`):

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 22.0.1, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 500 200" style="enable-background: new 0 0 500 200;" xml:space="preserve">
    <style type="text/css">
        .st0 { fill: #ff0000; }
        .st1 { fill: #ffff00; }
        .st2 { fill: #00ff00; }
    </style>
    <circle class="st0" cx="100" cy="100" r="50" />
    <circle class="st1" cx="250" cy="100" r="50" />
    <circle class="st2" cx="400" cy="100" r="50" />
</svg>
```

Primero leamos lo que está entre de las etiquetas `<style></style>`. La regla cuyo selector es una clase de nombre `st0`, tiene una propiedad de relleno de valor rojo en [código de color hexadecimal](https://htmlcolorcodes.com/es/). La regla de cuyo selector es una clase de nombre `st1`, tiene un relleno amarillo. Mientras que la regla cuyo selector es una clase de nombre `st2`, verde.

Fuera y seguido de las etiquetas `<style></style>`, tenemos tres circulos, cuyo centro está en distintas posiciones en la horizontal. Al primer círculo se le asigna la clase `st0`, al segundo la `st1` y al tercer la `st2`. Con esto, los círculos se verán rojo, amarillo y verde. 

A las clases de CSS se pueden agregar las [pseudoclases](https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes), que son palabras clave que se añaden inmediatamente después de los selectores, y que especifican un estado especial del elemento seleccionado. Por ejemplo, `:hover` aplicará un estilo cuando el usuario haga rondar el puntero del mouse sobre el elemento correspondiente.

Aplicando las pseudoclases podemos hacer lo siguiente:

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 22.0.1, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 500 200" style="enable-background: new 0 0 500 200;" xml:space="preserve">
    <style type="text/css">
        .st0, .st1, .st2 { fill:silver; }
        .st0:hover { fill: #ff0000; }
        .st1:hover { fill: #ffff00; }
        .st2:hover { fill: #00ff00; }
    </style>
    <circle class="st0" cx="100" cy="100" r="50" />
    <circle class="st1" cx="250" cy="100" r="50" />
    <circle class="st2" cx="400" cy="100" r="50" />
</svg>
```

En un principio, los elementos con clase `st0`, `st1` y `st2` tienen un mismo relleno gris. Pero cuando se ponga el mouse encima, se mostrará algo distinto. Para un caso será rojo, para otro amarillo y para otro más será verde (como un semáforo).

Con el mouse encima (`:hover`) también puedo gatillar algunas [transformaciones de CSS](https://developer.mozilla.org/es/docs/Web/CSS/transform):

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 22.0.1, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 500 200" style="enable-background: new 0 0 500 200;" xml:space="preserve">
    <style type="text/css">
        svg:hover circle.st0 {transform: translate(300px,0); transition:transform ease 1s;}
    </style>
    <circle class="st0" cx="100" cy="100" r="50" />
</svg>
```

Para ver una transformación, puedo aprovecharme de las [transiciones de CSS](https://developer.mozilla.org/es/docs/Web/CSS/transition). Con una transición que demora 1 segundo, tengo 1 segundo para ver cómo se traslada 300 pixeles a la derecha lo que tiene clase `st0`.

Algo más complejo puede ser creado mediante [animaciones de CSS](https://developer.mozilla.org/es/docs/Web/CSS/animation):

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 22.0.1, SVG Export Plug-In . SVG Version: 6.00 Build 0)  -->
<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 500 200" style="enable-background: new 0 0 500 200;" xml:space="preserve">
    <style type="text/css">
    	circle {
    		animation: nombre 5s linear 0s infinite;
    	}
    	@keyframes nombre {
    		0%   {fill:#FF0000;}
    		25%  {fill:#FFFF00; transform: translate(300px,0);}
    		50%  {fill:#00FFFF; transform: translate(300px,100px);}
    		75%  {fill:#0000FF; transform: translate(0px,100px);}
    		100%  {fill:#FF0000; transform: translate(0px,0px);}
    	}
    </style>
    <circle class="st0" cx="100" cy="50" r="50" />
</svg>
```

Pueden encontrar más ejemplos de animaciones en: 

- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-1.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-2.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-3.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-4.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-5.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/ejemplo-animacion-6.svg
- https://profesorfaco.github.io/dno075-2022-1/clase-05/img/blip.svg

Hay otra manera de hacer animación con SVG, que no usa CSS (Cascading Style Sheets) sino SMIL (Synchronized Multimedia Integration Language), pero conviene revisar el aviso que nos entrega MDN: https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL

Si es que por su cuenta quisieran investigar más respecto de animación SVG con SMIL, podrían aprovechar este artículo: https://css-tricks.com/guide-svg-animations-smil/

- - - - - - - - 

#### EJERCICIO

Pasemos a la práctica implementando dos gráficos, ambos pueden ser figurativos. 

En uno de ellos habrá que usar un `:hover` y en otro una [animación](https://developer.mozilla.org/es/docs/Web/CSS/animation) de iteración [infinita](https://developer.mozilla.org/es/docs/Web/CSS/animation-iteration-count). 

**Ambos usos deben aportar algo significativo (algo relevante para la comprensión; que no sea animar por animar), y ambos gráficos deben referir a un único asunto, el que tendrán que desplegar aprovechando [los archivos compartidos en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-05/) de repositorio**.

Como en la clase recién pasada, pueden tomar un gráfico figurativo de https://visualpharm.com/ o https://www.guemil.info/icons/

También podrían tomarlo de: 
- https://www.svgrepo.com/
- https://openmoji.org/library/
- https://icons.getbootstrap.com/

**¡Ojo!** En el SVG con el `:hover`, donde reutilizo el “pescado”, notarán una diferencia respecto de la clase recién pasada, el cambio se debe a https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/xlink:href 

- - - - - - - - 

#### TAREA

Leer este artículo: https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Variables

- - - - - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-04) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) 

