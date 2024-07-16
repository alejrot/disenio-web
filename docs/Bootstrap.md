

# BOOTSTRAP

[Sitio oficial de Bootstrap](https://getbootstrap.com/docs/5.0/getting-started/introduction/)

[FreeCodeCamp - Aprende Bootstrap 5 - Curso de Bootstrap desde Cero](https://youtu.be/QCw0L6FupQ0?list=PL4ONm-ifcbQJ7zDmC2WR_vidFPmxDLraL)

## Pilares de Bootstrap

Bootstrap proporciona tres grandes prestaciones:

- **Grid:** el sistema de maquetado adaptable 
- **Componentes:** recetas y componentes escritos en HTML fácilmente modificables por el diseñador.
- **Iconos:** un pack de 2000 íconos en formato SVG listos para usar libremente, bajo licencia MIT.

## Añadir Bootstrap al proyecto

### CDN
Para poder adjuntar de manera online Bootstrap al proyecto nos dirigimos a la [documentación de la página oficial](https://getbootstrap.com/docs/5.3/getting-started/download/) y copiamos los enlaces indicados en la sección “CDN via jsDelivr":

- El enlace de CSS va dentro del *head* del archivo HTML;
- El enlace de funcionalidades de JavaScript va en el *body* del HTML , justo al final.

Ejemplo:
```html title="Importando Bootstrap"
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

Se puede descargar el archivo comprimido de Bootstrap para descomprimirlo y adjuntarlo completo al proyecto. En ese caso los enlaces del archivo HTML deberán apuntar a los archivos clave del paquete.

### Gestores de paquetes

Bootstrap tiene paquetes preparados para trabajar con gestores de paquetes como NPM, Yarn, etc.



## Breve dicccionario

- **Framework:** Estructura (base) para facilitar el desarrollo.
- **Framework CSS:** son clases que permiten personalizar los elementos HTML
- **Responsive design (diseño adaptable):** Diseño de página que permite adaptar los elementos internos al tamaño de la pantalla usada (PC, tablet, celular) y su orientación (horizontal, vertical).


## Grid (cuadrícula)

Es un conjunto de contenedores , filas y columnas que definen cómo presentar y alinear el contenido.

Cada fila está dividida en 12 columnas.
Cada elemento de una fila puede ocupar varias columnas.
Las columnas de los elementos deben sumar 12. Si la suma supera 12 se crea automáticamente una nueva fila para ubicar los elementos sobrantes.

Clases para la grid:

- .row
- .col
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

## Breakpoint

Un breakpoint es la dimensión (ancho) de ventana que define el umbral para el cambio de estilo. El uso de breakpoints permite diseñar distintas distribuciones de los componentes gráficos de la página en función del ancho de la ventana actual del navegador, permitiendo aprovechar mejor el espacio disponible.


Breakpoints predefinidos según ancho de ventana (*viewport*):

| opción | significado | dimensiones|
|:---:|:---|:---:|
| **xs**  | *extra small* | < 576 px |
| **sm**  | *small*	| > 576 px	|
| **md**  | *medium*	| > 768 px |
| **lg**  | *large* | > 992 px |
| **xl**  | *extra large* | > 1200 px |
| **xxl** | *extra extra large* | > 1400 px |

La equivalencia entre estos breakpoints y las clases predefinidas de Bootstrap es:

| opción | clase |
|:---:|:---:|
| **xs**  | `.col-<N>`| 
| **sm**  | `.col-sm-<N>`| 
| **md**  | `.col-sd-<N>`| 
| **lg**  | `.col-lg-<N>`| 
| **xl**  | `.col-xl-<N>`| 
| **xxl** | `.col-xxl-<N>`| 

En esta notación `<N>` representa el ancho del componente representado en número de las columnas que ocupará dentro de la grid. 


Ejemplo:

```html
<!-- ventana 'xs': 12 columnas -->
.col-12	
<!-- ventana 'lg': 9 columnas -->
.col-lg-9		
<!-- ventana 'xxl': 6 columnas -->
.col-xxl-6		
```

!!! info "Asignación de columnas"
	No es necesario que en un proyecto se configuren todos los anchos de columnas para todos los breakpoints posibles. 


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

- **.container:** crea un contenedor adaptable con **ancho máximo fijo** dependiente del tamaño de dispositivo
- **.container-fluid:** crea un contenedor adaptable que cubre el 100% del ancho de ventana.

Un contenedor puede estar atado a los viewpoints.

 Ejemplo: un container “large" se puede definir así:
```html
<div class="container-lg">
	...
</div>
```


### Contenedores responsivos

Estos contenedores cubren el 100% del ancho de ventana si éste es inferior a las dimensiones de breakpoint elegdos, sino su ancho queda limitado al ancho de columna asignado. 

Opciones implementadas:


| opción | contenedor |
|:---:|:---:|
| **sm**  | `.container-sm`| 
| **md**  | `.container-sd`| 
| **lg**  | `.container-lg`| 
| **xl**  | `.container-xl`| 
| **xxl** | `.container-xxl`| 




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
Bootstrap tiene su propio repositorio de íconos escalables, los cuales se pueden usar por descarga o por CDN. Cada ícono disponible tiene su código de elemento en la página web para poder añadirlo al proyecto donde se requiera. Asimismo, para que funcione el ícono por CDN hay que añadir en el *head* de HTML el enlace de fuente que se indica en la seccion “Install".


[**Galería de íconos de Bootstrap**](https://icons.getbootstrap.com)

Los íconos pueden instalarse localmente via NPM:
```bash
npm i bootstrap-icons
```

### Web font

Los iconos pueden importarse todos juntos mediante CDN. El link del CDN se asigna dentro del `head` del archivo HTML:

```html title="Importación Iconos - CDN"
<!-- archivo HTML -->
<head>
	...
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
</head>
```

El ícono elegido de la galería viene en formato SVG (formato de imagen vectorial) ,el cual puede llamarse por su nombre de clase (campo *'Icon font'*):


```html title="Icono en maqueta HTML"
<!-- archivo HTML -->
<i class="bi bi-windows"></i>  <!-- Icono Windows -->
```


El tamaño y color del ícono se modifica con CSS mediante las propiedades `font-size` y `color`:

```css title="Estilo de íconos SVG"
/* archivo CSS (ó sección <style> del HTML) */
i {
	/* altura -> se toma al icono como si fuera una letra */
	font-size: 250px;
	/* color */
	color: slateblue;  
}

```

!!! tip "Iconos descargables"
	El sitio de Bootstrap permite tanto la descarga individual de los íconos como la descarga en archivo comprimido del paquete completo. En estos casos no es necesario asignar la ruta al servidor CDN.


### Ícono SVG embebido

El ícono SVG también se puede importar en formato texto dentro del archivo HTML:

```html title="SVG embebido"
<!-- Icono 'X circle fill' -->
<svg xmlns="http://www.w3.org/2000/svg" width="250px" height="250px" fill="currentColor" class="bi bi-x-circle-fill" viewBox="0 0 16 16">
  <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293z"/>
</svg>
```

En este caso las dimensiones de indican con los atributos `width` ó `height` (no hace falta indicar ambos).

El color y el tamaño también se pueden indicar con ayuda del CSS:

```css title="Estilo de icono embebido"
svg {
	width: 128px;		
	color: red;
}
```



## Flexbox en Bootstrap

### Flexbox

Flexbox significa *'CSS Flexible Box Layout'*. Sirve para que los elementos adaptables ubicados dentro de un contenedor se distribuyan automáticamente en base al tamaño del dispositivo. 

Flexbox usa *'contenedores flex'* para agrupar los elementos de la página. Flexbox viene integrado en CSS y se usa como:

```html title="Elemento Flexbox en HTML"
<!-- HTML -->
<div class="contenedor"> 
Mi contenedor
</div>
```

``` css title="Elemento Flexbox en CSS"
/*  CSS */
.contenedor{
	display: flex; 
}
```

### Clase *d-flex*


Bootstrap integra Flexbox en sus **clase predefinida `d-flex`**:

```html title="Elemento Flexbox en Bootstrap"
<!-- HTML -->
<div class="d-flex"> 
Mi contenedor
</div>
```

Esta clase trae una serie de propiedades predefinidas basadas en las de Flexbox. Algunas de las más importantes se señalan a continuación.


### flex-direction
Establece el eje principal del contenedor, la dirección en la cual se colocan los elementos internos.
Opciones: 

- row: fila, de izquierda a derecha;
- row-reverse: fila, de derecha a izquierda
- column: columna, de arriba a abajo
- column-reverse: columna, de abajo a arriba.

### justify-content
Define cómo se distribuyen los elementos en el **eje principal**. Opciones en Bootstrap:

- justify-content-start
- justify-content-end
- justify-content-center
- justify-content-between
- justify-content-around
- justify-content-evenly

### align-items
Define cómo se distribuyen los elementos en el eje perpendicular al eje principal (*eje secundario*). Opciones en Bootstrap:

- align-items-start
- align-items-end
- align-items-center
- align-items-baseline
- align-items-stretch

### flex-wrap
Determina si los elementos deben ajustarse para que estén en una misma línea o si se les permite distribuirse en varias líneas si es necesario. Opciones:

- flex-nowrap	→ elementos “apretados" en la misma línea
- flex-wrap 	→ elementos en varias líneas si no hay espacio
- flex-wrap-reverse















