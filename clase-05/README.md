# Gráficos con SVG y CSS

### Clase 05 → 04/04/2022

**[CSS](https://github.com/profesorfaco/dno075-2021-2/wiki/CSS)** es un lenguaje descriptivo que podemos reconocer por sus **reglas** que se estructuran con `selector{propiedad:valor;}`. 

Un documento SVG puede contener, entre etiquetas `<style></style>`, a tal lenguaje.

Cuando usamos Illustrator para guardar un SVG, el programa genera, automáticamente, tantas reglas como sean necesarias para describir el aspecto de los distintos elementos gráficos que contiene el SVG. Estas reglas tienen selectores de clase `st+n`, como en: `.st0{…}`, `.st1{…}`, `.st2{…}`, etc.

Así, por ejemplo, podemos obtener el siguiente código:

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

La regla cuyo selector es una clase de nombre `st0`, tiene una propiedad de relleno de valor rojo en [código de color hexadecimal](https://htmlcolorcodes.com/es/). La regla de cuyo selector es una clase de nombre `st1`, tiene un relleno amarillo. Mientras que la regla cuyo selector es una clase de nombre `st2`, verde.

Fuera y seguido de las etiquetas `<style></style>`, tenemos tres circulos, cuyo centro está en distintas posiciones en la horizontal. Al primer círculo se le asigna la clase `st0`, al segundo la `st1` y al tercer la `st2`. Con esto, los círculos se verán rojo, amarillo y verde. 

- - - - - - - - - - 

###### [← CLASE PASADA](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-04) — [CLASE SIGUIENTE →](https://github.com/profesorfaco/dno075-2022-1/tree/main/clase-06) 

