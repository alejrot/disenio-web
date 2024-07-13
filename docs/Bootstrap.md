

# BOOTSTRAP

[Sitio oficial de Bootstrap](https://getbootstrap.com/docs/5.0/getting-started/introduction/)

[Aprende Bootstrap 5 - Curso de Bootstrap desde Cero](https://youtu.be/QCw0L6FupQ0?list=PL4ONm-ifcbQJ7zDmC2WR_vidFPmxDLraL)

## Breve dicccionario
- **Framework:** Estructura (base) para facilitar el desarrollo.
- **Framework CSS:** son clases que permiten personalizar los elementos HTML
- **Responsive design (diseño adaptable):** Diseño de página que permite adaptar los elementos internos al tamaño de la pantalla usada (PC, tablet, celular) y su orientación (horizontal, vertical).

## Tres pilares:
- Grid
- Componentes
- Iconos

## Grid 
Es un conjunto de contenedores , filas y columnas que definen cómo presentar y alinear el contenido.

Cada fila está dividida en 12 columnas.
Clases para la grid:
- .row
- .col-
- .col-sm-
- .col-md-
- .col-lg-
- .col-xl-

*row*: fila ; col (*column*): columna
ejemplo: uso de clase row
```html
<div class="row">
	...
</div>
```

Tamaños según ancho de ventana (viewport)
- xs → extra small <576px
- sm → small	>=576px	
- md → medium	 >=768px
- lg → large >=992px
- xl → extra large >= 1200px
- xxl → extra extra large =>1400px


## Breakpoint
Dimensión (ancho) que define el umbral para el cambio de estilo


## Contenedores
Un contenedor puede tener varias filas y cada fila contiene doce columnas de la grid. Una columna visual puede ocupar múltiples columnas de la grid.
Ejemplo: un contenedor con una única fila subdividida en dos columnas visuales
```html
<div class="container">
	<div class="row">
		<div class="col"></div>
		<div class="col"></div>
	</div>
</div>
```
Hay dos clases de contenedores
- **.container:** crea un contenedor adaptable con ancho máximo fijo dependiente del tamaño de dispositivo
- **.container-fluid:** crea un contenedor adaptable que cubre el 100% del ancho de ventana.

Un contenedor puede estar atado a los viewpoints: Ejemplo: un container “large" se puede definir aí:
```html
<div class="container-lg">
	...
</div>
```

## Añadir Bootstrap al proyecto

### CDN
Para poder adjuntar de manera online Bootstrap al proyecto nos dirigimos a la [documentación de la página oficial](https://getbootstrap.com/docs/5.3/getting-started/download/) y copiamos los enlaces indicados en la sección “CDN via jsDelivr":
- El enlace de CSS va dentro del head del archivo HTML;
- El enlace de funcionalidades de JavaScript va en el body del HTML , justo al final.
Ejemplo:
```html
<!DOCTYPE html >
<html lang="es">
	<head>
		...
		...
		<!-- CSS Bootstrap -->
		<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
		...
	</head>
	<body>
		...
		...
		<!-- JS Bootstrap -->
		<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
	</body>
</html>
```
**CDN** significa *Content Delivery Network*.

### Descarga manual (ZIP)

Se puede descargar el archivo comprimido para adjuntarlo al proyect. En ese caso los enlaces del archivo HTML deberán apuntar a los archivos clave del paquete

### Gestores de paquetes

Bootstrap tiene paquetes preparados para trabajar con gestores como NPM, Yarn, etc.



## Estructura de la grid
Los elementos de una fila pueden ocupar varias columnas. Para aprovechar el ancho disponible la suma de columnas usadas por los elementos debe dar doce.
Ejemplo: un elemento que ocupa 5 columnas y otro ocupa 7:
```html
    .col-sm-5   
	.col-sm-7
```
Si la suma de columnas da más de doce los elementos cambian de fila automáticamente.

A un mismo elemento se le puede asignar varias clases distintas. 

Ejemplo: una columna con ancho relativo variable de 4 columnas (pantallas pequeñas) a 6 columnas (pantallas grandes) y una clase de estilo personalizada:
```html
<div class="col-sm-4  col-lg-6  columna">  ... </div>
```

## Componentes de Bootstrap
Son elementos HTML reutilizables, con estilo predeterminado pero personalizables. En la sección “Componentes" de la página oficial se encuentra un abanico de componentes disponibles para copiar y pegar.

[**Componentes de Bootstrap**](https://getbootstrap.com/docs/5.3/components/accordion/)

## Iconos de bootstrap
Bootstrap tiene su propio repositorio de íconos escalables, los cuales se pueden usar por descarga o por CDN. Cada ícono disponible tiene su código de elemento en la página web para poder añadirlo al proyecto donde se requiera. Asimismo, para que funcione el ícono por CDN hay que añadir en el *head* de HTML el enlace de fuente que se indica en la seccion “Install"


[**Iconos de Bootstrap**](https://icons.getbootstrap.com)

Los íconos pueden instalarse localmente via NPM:
```bash
npm i bootstrap-icons
```


## Flexbox
CSS Flexible Box Layout. Sirve para que los elementos adaptables ubicados dentro de un contenedor se distribuyan automáticamente en base al tamaño del dispositivo. Los flexbox usan la clase *d-flex*:
```html
<div class="d-flex"> 
    Mi contenedor 
</div>
```

## flex-direction
Establece el eje principal del contenedor, la dirección en la cual se colocan los elementos internos.
Opciones: 
- row: fila, de izquierda a derecha;
- row-reverse: fila, de derecha a izquierda
- column: columna, de arriba a abajo
- column-reverse: columna, de abajo a arriba.

## justify-content
Define cómo se distribuyen los elementos en el eje principal. Clases de Bootstrap prearmadas:
- justify-content-start
- justify-content-end
- justify-content-center
- justify-content-between
- justify-content-around
- justify-content-evenly

## align-items
Define cómo se distribuyen los elementos en el eje perpendicular al eje principal. Opciones:
- align-items-start
- align-items-end
- align-items-center
- align-items-baseline
- align-items-stretch

## flex-wrap
Determina si los elementos deben ajustarse para que estén en una misma línea o si se les permite distribuirse en varias líneas si es necesario. Opciones:
- flex-nowrap	→ elementos “apretados" en la misma línea
- flex-wrap 	→ elementos en varias líneas si no hay espacio
- flex-wrap-reverse















