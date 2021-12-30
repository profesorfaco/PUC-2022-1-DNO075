# Gráficos con SVG y CSS

### Clase 05 → 04/04/2022

**[CSS](https://github.com/profesorfaco/dno075-2021-2/wiki/CSS)** es un lenguaje descriptivo que podemos reconocer por sus **reglas** que se estructuran con `selector{propiedad:valor;}`. 

Un documento SVG puede contener, entre etiquetas `<style></style>`, a tal lenguaje.

Cuando usamos Illustrator para guardar un SVG, el programa genera, automáticamente, tantas reglas como sean necesarias para describir el aspecto de los distintos elementos gráficos que contiene el SVG. Estas reglas tienen selectores de clase `st+n`, como en: `.st0{…}`, `.st1{…}`, `.st2{…}`, etc.

El selector de clase se identificar por el punto inmediatamente anterior al nombre. Así como Illustrator nombre a algo `.st0{}`, nosotros podríamos llamarle `.primero{}`, o `.como_se_nos_ocurra{}`, nunca iniciando tal nombre con un número ni usando palabras separadas. Luego, cuando necesitemos que un elemento utilice la clase, debemos sumarle el atributo `class="…"`, con el nombre de la clase entre comillas, sin el punto antecesor.

Revisemos lo recién presentado en el siguiente código:

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

A las clases de CSS se pueden agregar las pseudoclases, que son palabras clave que se añaden inmediatamente después de los selectores, y que especifican un estado especial del elemento seleccionado. Por ejemplo, `:hover` aplicará un estilo cuando el usuario pose el mouse sobre el elemento correspondiente.

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

En un principio, todas las clases definen un relleno gris. Pero cuando se ponga el mouse encima, se mostrará algo distinto.

- - - - - - - - 

#### EJERCICIO

Pasemos a práctica implementando dos gráficos, ambos deben ser gráficos mixto que utilicen en un capa un gráfico figurativo rasterizado y en otra un gráfico no figurativo vectorizado; ahora bien, parte de los elementos deben cambiar con clases y pseudoclases.

**Los dos gráficos que se implementen deben referir a un único asunto, el que tendrán que desplegar aprovechando [los archivos compartidos en esta carpeta](https://profesorfaco.github.io/dno075-2022-1/clase-05/) de repositorio**.

- - - - - - - - 

#### TAREA

Leer este artículo: https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Variables

- - - - - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-04) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) 

