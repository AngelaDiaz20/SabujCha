[![sabujcha](https://i.postimg.cc/T1JqVrZr/sabujcha.png "sabujcha")](http://https://i.postimg.cc/T1JqVrZr/sabujcha.png "sabujcha")

**Sabujcha** es una nueva marca de té matcha que busca incursionar en el mercado a través de una tienda virtual fácil de navegar y que muestre los beneficios de su producto, Andrea y Diana que son las emprendedoras tras esta marca, quieren que el sitio web tenga un look fresco y que su producto sea el principal protagonista.

------------

## Cambios en el mockup
### Navbar
En cuanto a los mockups, en ellos se presentó dos estilos de navbar diferentes; por lo cual se optó por elegir uno de los dos para evitar cualquier tipo de confusión en el usuario.

[![navbar](https://i.postimg.cc/FR5pynkd/navbar.png "navbar")](http://https://i.postimg.cc/FR5pynkd/navbar.png "navbar")


### Banners
En el caso de los banners, en su diseño original los anuncios de descuento se sobreponen a las imágenes y estos letreros se confunden con el color de la imagen. Para ello se hizo una modificación, agregando un pequeño borde al texto junto con un fondo de leve color blanco que incluye un blur.

[![Banners](https://i.postimg.cc/k4QcfFWj/banners.png "Banners")](http://https://i.postimg.cc/k4QcfFWj/banners.png "Banners")


### Contenedrores principales
El diseño original suponía unos márgenes a ambos costados de cada sección en la página, lo cual generaba una sensación extraña; ante esto, opté por ajustar los contenedores al 100% del viewport.

[![contenedores](https://i.postimg.cc/FKJGJQzX/homepage.png "contenedores")](http://https://i.postimg.cc/FKJGJQzX/homepage.png "contenedores")

# Estructura del código

## Hecho con

<div>
<a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML5" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/html5-colored.svg" width="46" height="36" alt="HTML5" /></a>
<a href="https://www.w3.org/TR/CSS/#css" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/css3-colored.svg" width="46" height="36" alt="CSS3" /></a>
<img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/d843eb4d-482e-4f76-b676-25b073d1d522/d5lujy4-2908b934-c794-436e-92fe-1bd5f8df39f5.png/v1/fill/w_526,h_461,strp/corazon_rojo_png_by_catatini_d5lujy4-fullview.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9NDYxIiwicGF0aCI6IlwvZlwvZDg0M2ViNGQtNDgyZS00Zjc2LWI2NzYtMjViMDczZDFkNTIyXC9kNWx1ank0LTI5MDhiOTM0LWM3OTQtNDM2ZS05MmZlLTFiZDVmOGRmMzlmNS5wbmciLCJ3aWR0aCI6Ijw9NTI2In1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.pNq_uQyIyT_9OM3KQsAPrUplcX6Oz6Br0Hz8MZudEUE" width="46" height="36" alt="Corazón"/>
</div>

## Root
Se establece un :root para declarar una serie de variables a aquellos valores que se usarán repetitivamente a medida que se apliquen estilos.

```css
:root{
    --title-font:'Playfair Display', serif;
    --title-product-font:'Work Sans', sans-serif;
    --text-font:'Lora', serif;

    --line-height:1.5;

    --black-color:#333333;
    --gray-color:#575757;
    --green-color:#529F0F;

    --transition:all 300ms;

}
```

## Navbar

[![Navbar](https://i.postimg.cc/wxmZTtFj/Group-117.png "Navbar")](http://https://i.postimg.cc/wxmZTtFj/Group-117.png "Navbar")

La estructura de la barra de navegación está compuesta por tres partes, los ítems para navegar entre las diferentes secciones, el logo, y el apartado de idioma con el carrito de compras. Se estructuró adicionalmente con íconos e inputs especifícamente para dar despliegue al menú en dispositivos móviles.

```html
<header>
        <nav>
            <div class="nav_items">
                <a href="index.html">HOME</a>
                <a href="#">ABOUT</a>
                <a href="#">BLOG</a>
                <a href="#">PAGES</a>
                <a href="#">CONTACT</a>
            </div>
            <img src="img/logo.png" alt="Logo de SabujCha" class="logo">
            <div class="cart">
                <span>USD <i class="fa-solid fa-chevron-down"></i></sppan>
                <i class="fa-solid fa-cart-shopping"></i>
            </div>
            <div class="menu">
                <input type="radio" name="menu" id="menu">
                <label for="menu" class="label_menu"><i class='bx bx-menu'></i></label>
                <input ... id="close"><label for="close" class="label_close">...</label>
            </div>
        </nav>
    </header>
```

En dispositivos móviles, el menú desplegable se posiciona sobre el banner con ayuda de **"z-index"** y **"position:fixed"**, iniciando oculto a través del **"display:none"**, estado que se alterará a través de la pseudoclase **":checked"**, en la cual el input relacionado podrá determinar si mostrar u ocultar el menú. Por último se implementó una animación, para hacer más amigable el despliegue del menú.

```css
.nav_items{
    position: fixed;
    z-index: 100;
    display: none;
    animation: desplegar 300ms backwards;
}

#menu:checked ~ .label_menu{
    display: none;
}

#menu:checked ~ .nav_items, #menu:checked ~ .label_close div{
    display: flex;
}

/*----Animación menú desplegable---*/
@keyframes desplegar {
    0%{ border-bottom-right-radius: 50%;}
    100%{border-bottom-right-radius: 0%;}
}
```

Para escritorio, el apartado de ítems y el carrito de compras se acomodan a cada extremo mediante **"display:flex**" y **"justify-content:space-between"**. Por otra parte, el logo se acomoda en el centro a través de un **"position:absolute"** y un respectivo cálculo sobre el eje x.

```css
.nav_items{
        width: 45%;
        display: flex;
        justify-content: space-between;
    }
    
    .logo{
        position: absolute;
        height: 35px;
        left: calc(50%-75px);
    }
```

## Sección de productos

[![productos](https://i.postimg.cc/kMz10nmP/image-224.png "productos")](http://https://i.postimg.cc/kMz10nmP/image-224.png "productos")

Para cada una de las secciones de productos (3 en total, "latest products" - "new products" - "related products") se planteó una estructura base, de tal manera que lo único a cambiar serían los detalles propios de cada producto. Cada producto figura como artículo, el cual comprende la imagen y descripción del mismo, además de 3 botones de acción, dentro de los cuales, uno de ellos despliega el modal de visualización de producto.

```html
<section class="products" id="products">
            <h1>Latest Products</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit sed do eiusmod tempor incidunt</p>
            <div class="container_products latest_products">
            
                <article class="product">
                    <div class="product_image">
                        <a href="product.html"><img src="img/product-1.jpg" alt="Imagen de Nature Close Tea"></a>
                        <div class="discount">-20%</div>
                        <div class="product_actions">
                            <i class="fa-regular fa-heart"></i>
                            <i class="fa-solid fa-shuffle"></i>
                            <a href="#modal"><i class="fa-solid fa-magnifying-glass"></i></a>
                        </div>
                    </div>            
                    <div>
                        <p class="add">+ Add to cart</p>
                        <p class="product_name">Nature Close Tea</p>
                        <p><span>$100.00</span> - <del>120.00 </del></p>
                    </div>
                </article>

                <article class="product">...</article>

                <article class="product">...</article>

                <article class="product">...</article>
            </div>
        </section>
```

Respecto al contenedor y cómo este logra adaptarse a diferentes dispositivos, se debe al manejo de mediaqueries haciendo en ellas uso de **"display:grid"**, manipulando el tamaño de las columnas según el tipo de dispositivos; adicional a ello, siguiendo el diseño original, la cantidad de productos a mostrar disminuye proporcionalmente al tamaño del viewport, por lo cual se usó aquí un **overflow:hidden**.

```css
/*--------Versión móvil--------*/
.container_products{
    width: 95%;
    margin: auto;
    overflow-x: hidden;
    display: grid;
    grid-template-columns: repeat(4, 100%);
    column-gap: 20px;
    justify-content: space-between;
}

/*--------Versión escritorio--------*/
.container_products{
        width: 85%;
        grid-template-columns: repeat(4, 1fr);
    }
```

## Footer

[![Footer](https://i.postimg.cc/Hk5r53Dh/image-230.png "Footer")](http://https://i.postimg.cc/Hk5r53Dh/image-230.png "Footer")

La estructura del footer es la misma para cada una de sus secciones, un artículo compuesto por un subtítulo y una serie de enlaces.

```html
<footer>
        <div class="footer_container">
            <article class="footer_column">
                <h2>My Account</h2><br>
                <a href="#">My Account</a>
                <a href="#">Order History</a>
                <a href="#">...</a>
            </article>
            <article class="footer_column">...</article>
            <article class="footer_column">...</article>
            <article class="footer_column">...</article>
        </div>
        <div class="footer_made">
            <div>
                <p>© 2021 <strong>SabujCha</strong> Made with 🧡 By <strong>HasThemes</strong></p>
                <img src="img/payment.png" alt="">
            </div>
        </div>
    </footer> 
```
La disposición de columnas del footer se da con **"display:grid"**, para móvil se fija en una sola columna. En cuanto al pie de página de elaboración, maneja **"display:flex"**, también a manera de una sola columna.

```css
.footer_container{
    display: grid;
    grid-template-columns:1fr;
    gap: 30px;
    width: 90%;
}

.footer_made div{
    width: 90%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
```

Finalmente, para escritorio se acomoda el contenido en 4 columnas de igual tamaño y el pie de página cambia de dirección a estar en una sola fila, con los elementos a cada lado.

```css
.footer_container{
        grid-template-columns: repeat(4, 1fr);
    }

.footer_made div{
        flex-direction: row;
        justify-content: space-between;
    }
```
## Modal

[![Modal](https://i.postimg.cc/gJYbzyP5/Group-118.png "Modal")](http://https://i.postimg.cc/gJYbzyP5/Group-118.png "Modal")

El modal se divide en dos secciones, la primera corresponde a la mini galería de producto y la segunda a la descripción del mismo.

```html
<section id="modal" class="modal">
            <div class="modal_container">
                <div class="modal_header">
                    <a href="#products" class="modalClose"><strong>X</strong></a> 
                </div>
                <div class="modal_content">
                    <figure class="modal_picture">
                        <img src="img/product-1.jpg" alt="Imagen de producto">
                        <div class="modal_miniature">
                            <img src="img/product-1.jpg" alt="Imagen de producto">...
                        </div>
                    </figure>
                    <article class="modal_product_description">
                        <h1>Dutchman's Breeches</h1><br>
                        <select name="size" id="size">
                            <option value="s">...</option>
                        </select><br>
                        <p>Color*</p>
                        <div class="colors">
                            <ul><li class="blue">...</li></ul>
                        </div>
                        ...
                        <p><i class="fa-solid fa-check"></i> In stock</p>
                    </article></div></div>
        </section>
```

> Para acceder a este modal, es necesario referenciarlo en la tarjeta del producto a través del id
```html
> <article class="product">
          ...<a href="#modal"><i class="fa-solid fa-magnifying-glass"></i></a>...
</article>
```

Es útil aquí usar la pseudoclase **":target"** para determinar en qué momento el modal debe hacerse visible cambiando no solo su opacidad, sino convirtiéndose además en objetivo del puntero. El modal siempre permanece ahí, pero solo hasta que se pulse sobre el enlace, éste podra hacerse visible.

```css
.modal{
    position: fixed;
    z-index: 100;
    display: flex;
    --opacity:0;
    --pointer:none;

    opacity:var(--opacity);

    pointer-events: var(--pointer);
    transition: opacity 0.5s;
}

.modal:target{
    --opacity:1;
    --pointer:unset;
}


```

## Description, tags and reviews

[![Description, tags, reviews](https://i.postimg.cc/jq9D3CTN/Group-119.png "Description, tags, reviews")](http://https://i.postimg.cc/jq9D3CTN/Group-119.png "Description, tags, reviews")

Se establece un input tipo radio y label, para cada una de las secciones a mostrar y/o ocultar

```html
<section class="information_single_product">

            <input type="radio" name="nav" id="description" checked>
            <label for="description" class="label label_description">Description</label>

            <input type="radio" name="nav" id="tags">
            <label for="tags" class="label label_tags">Tags</label>

            <input type="radio" name="nav" id="review">
            <label for="review" class="label label_review">Review</label>

            <article class="description"> ...</article>

            <article class="tags">...</article>

            <article class="review">...</article>
        </section>
```
A cada elemento se le atribuye "display:none" para que permanezca oculto, y, solo cuando él haga uso de la pseudoclase  ":checked" pueda aparecer a través de "display:block", adicional a esto, cuando el input esté seleccionado, el color del label cambiará de negro a verde para que sea distinguible qué sección se está mostrando.

```css
.review, .tags, .description{
    display: none;
}

#description:checked ~ .description, #tags:checked ~ .tags, #review:checked ~ .review{
    display: block;
}

#description:checked ~ .label_description, #tags:checked ~ .label_tags, #review:checked ~ .label_review{
    color: var(--green-color);
    border-bottom: 2px solid var(--green-color);
}
```
