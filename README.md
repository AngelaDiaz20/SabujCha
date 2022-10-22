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

## Navbar

[![Navbar](https://i.postimg.cc/wxmZTtFj/Group-117.png "Navbar")](http://https://i.postimg.cc/wxmZTtFj/Group-117.png "Navbar")

La estructura de la barra de la barra de navegación está compuesta por tres partes, los ítems para navegar entre las diferentes secciones, el logo, y el apartado de idioma con el carrito de compras. Se estructuró adicionalmente con uno íconos e inputs especifícamente para dar despliegue a un menú en dispositivos móviles.

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

En dispositivos móviles, el menú desplegable se posiciona sobre el banner con ayuda del **z-index** y **position:fixed**, iniciando oculto a través del **display:none**, estado que se alterará a través de la pseudoclase **:checked**, en la cual el input relacionado podrá determinar si mostrar u ocultar el menú. Por último se implementó una animación, para hacer más amigable el despliegue del menú.

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

Respecto al contenedor y cómo este logra adaptarse a diferentes dispositivos, se debe al manejo de mediaqueries haciendo en ellas uso de **display:grid**, manipulando el tamaño de las columnas según el tipo de dispositivos; adicional a ello, siguiendo el diseño original, la cantidad de productos a mostrar disminuye proporcionalmente al tamaño del viewport, por lo cual se usó aquí un **overflow:hidden**.

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
