<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>Kurama Sushi</title>

    <link rel="stylesheet" href="estilo.css">
</head>


<body>

    <!-- =====================================
         PORTADA
    ====================================== -->

    <header class="portada">

        <div class="portada-contenido">

            <div class="logo">
                KURAMA
                <span>SUSHI</span>
            </div>

            <p class="frase">
                Sushi hecho para disfrutar
            </p>

            <a href="#productos" class="boton-menu">
                VER MENÚ
            </a>

        </div>

    </header>


    <!-- =====================================
         NAVEGACIÓN
    ====================================== -->

    <nav class="categorias">

        <a href="#sushi">
            🍣 Sushi
        </a>

        <a href="#cortes">
            🥢 Cortes
        </a>

        <a href="#arma">
            🍱 Arma tu pedido
        </a>

        <a href="#box">
            📦 Box
        </a>

        <a href="#agregar">
            ➕ Agregar
        </a>

    </nav>


    <!-- =====================================
         CONTENIDO PRINCIPAL
    ====================================== -->

    <main id="productos">


        <!-- SUSHI -->

        <section id="sushi" class="categoria">

            <h2>SUSHI</h2>

            <p class="descripcion">
                Selección de sushi a elección del chef.
                Tú eliges la cantidad de piezas.
            </p>

            <div class="productos">

                <!-- Aquí pondremos los productos después -->

            </div>

        </section>


        <!-- CORTES -->

        <section id="cortes" class="categoria">

            <h2>CORTES</h2>

            <div class="productos">

                <!-- Aquí pondremos los cortes después -->

            </div>

        </section>


        <!-- ARMA TU PEDIDO -->

        <section id="arma" class="categoria">

            <h2>ARMA TU PEDIDO</h2>

            <div class="productos">

                <!-- Aquí pondremos los productos después -->

            </div>

        </section>


        <!-- BOX -->

        <section id="box" class="categoria">

            <h2>BOX</h2>

            <div class="productos">

                <!-- Aquí pondremos los box después -->

            </div>

        </section>


        <!-- AGREGAR -->

        <section id="agregar" class="categoria">

            <h2>AGREGAR</h2>

            <div class="productos">

                <!-- Aquí pondremos los adicionales después -->

            </div>

        </section>


    </main>


    <!-- =====================================
         CARRITO
    ====================================== -->

    <aside id="carrito" class="carrito">

        <h2>🛒 Tu pedido</h2>

        <div id="lista-carrito">

            <p>
                Tu pedido está vacío.
            </p>

        </div>

        <div class="total">

            Total:
            <strong id="total">
                $0
            </strong>

        </div>

        <button id="whatsapp">
            ENVIAR PEDIDO POR WHATSAPP
        </button>

    </aside>


    <!-- =====================================
         JAVASCRIPT
    ====================================== -->

    <script src="funciones.js"></script>

</body>

</html>
/* =========================================
   CONFIGURACIÓN GENERAL
========================================= */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Georgia, "Times New Roman", serif;
    background: #eadcc2;
    color: #4b2b20;
}


/* =========================================
   PORTADA
========================================= */

.portada {
    min-height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;

    position: relative;
    overflow: hidden;

    background:
        linear-gradient(
            rgba(67, 37, 25, 0.25),
            rgba(67, 37, 25, 0.25)
        ),
        linear-gradient(
            to bottom,
            #75452f,
            #a66f50,
            #d2a47c
        );
}


/* Decoración Sakura */

.portada::before {
    content: "🌸   🌸        🌸     🌸";

    position: absolute;

    top: 5%;
    left: 0;

    width: 100%;

    font-size: 45px;

    opacity: 0.85;

    letter-spacing: 25px;

    transform: rotate(-3deg);
}


/* Segunda rama */

.portada::after {
    content: "🌸        🌸   🌸          🌸";

    position: absolute;

    bottom: 8%;
    right: -30px;

    font-size: 38px;

    opacity: 0.75;

    transform: rotate(4deg);
}


/* =========================================
   CONTENIDO DE PORTADA
========================================= */

.portada-contenido {
    position: relative;

    z-index: 2;

    width: min(700px, 88%);

    min-height: 75vh;

    padding: 70px 40px;

    display: flex;
    flex-direction: column;

    justify-content: center;
    align-items: center;

    text-align: center;

    background:
        radial-gradient(
            circle at 30% 20%,
            rgba(255,255,255,0.6),
            transparent 35%
        ),
        #f5ecd9;

    box-shadow:
        12px 18px 35px rgba(0,0,0,0.25);

    border-radius: 5px 8px 4px 7px;
}


/* Textura del papel */

.portada-contenido::before {
    content: "";

    position: absolute;

    inset: 0;

    background-image:
        radial-gradient(
            rgba(80,50,30,0.15) 0.7px,
            transparent 0.8px
        );

    background-size: 6px 6px;

    opacity: 0.35;

    pointer-events: none;
}


/* =========================================
   LOGO
========================================= */

.logo {
    position: relative;

    font-size: clamp(48px, 10vw, 90px);

    font-weight: bold;

    letter-spacing: 7px;

    color: #7b2927;

    text-shadow:
        2px 2px 0 #d8b56f;
}


.logo span {
    display: block;

    margin-top: -5px;

    font-size: clamp(20px, 4vw, 32px);

    letter-spacing: 12px;

    color: #a77a35;
}


/* =========================================
   FRASE
========================================= */

.frase {
    position: relative;

    margin-top: 30px;

    font-size: 19px;

    color: #76523d;

    letter-spacing: 2px;
}


/* =========================================
   BOTÓN VER MENÚ
========================================= */

.boton-menu {
    position: relative;

    margin-top: 40px;

    padding: 16px 45px;

    background: #7b2927;

    color: #fff7e7;

    text-decoration: none;

    font-size: 18px;

    letter-spacing: 3px;

    border-radius: 3px;

    border: 2px solid #c69a4b;

    box-shadow:
        0 7px 15px rgba(0,0,0,0.2);

    transition: 0.3s;
}

.boton-menu:hover {
    transform: translateY(-3px);

    background: #9a3a35;

    box-shadow:
        0 10px 20px rgba(0,0,0,0.25);
}


/* =========================================
   CATEGORÍAS
========================================= */

.categorias {
    position: sticky;

    top: 0;

    z-index: 50;

    display: flex;

    justify-content: center;

    flex-wrap: wrap;

    gap: 8px;

    padding: 14px;

    background:
        rgba(68, 38, 27, 0.97);

    box-shadow:
        0 4px 12px rgba(0,0,0,0.2);
}


.categorias a {
    color: #f7e9cc;

    text-decoration: none;

    padding: 10px 15px;

    border: 1px solid #b9914e;

    border-radius: 3px;

    font-size: 14px;

    transition: 0.25s;
}


.categorias a:hover {
    background: #a34b3d;

    color: white;
}


/* =========================================
   CONTENIDO
========================================= */

main {
    max-width: 1100px;

    margin: auto;

    padding: 30px 15px 80px;
}


/* =========================================
   CATEGORÍA
========================================= */

.categoria {
    margin-bottom: 55px;

    padding: 35px 20px;

    background: #f5ecd9;

    border-radius: 5px;

    box-shadow:
        0 7px 20px rgba(70,40,25,0.12);
}


.categoria h2 {
    text-align: center;

    color: #7b2927;

    font-size: 30px;

    letter-spacing: 4px;

    margin-bottom: 12px;
}


.descripcion {
    text-align: center;

    max-width: 600px;

    margin: 0 auto 30px;

    color: #76523d;

    line-height: 1.6;
}


/* =========================================
   PRODUCTOS
========================================= */

.productos {
    display: grid;

    grid-template-columns:
        repeat(auto-fit, minmax(240px, 1fr));

    gap: 20px;
}


/* =========================================
   TARJETAS
========================================= */

.producto {
    background: #fffaf0;

    border: 1px solid #d8bd8d;

    border-radius: 5px;

    padding: 22px;

    text-align: center;

    box-shadow:
        0 4px 12px rgba(80,45,25,0.1);

    transition: 0.25s;
}


.producto:hover {
    transform: translateY(-4px);

    box-shadow:
        0 9px 20px rgba(80,45,25,0.18);
}


.producto h3 {
    color: #7b2927;

    margin-bottom: 10px;
}


.precio {
    font-size: 21px;

    font-weight: bold;

    color: #a47732;

    margin: 12px 0;
}


/* =========================================
   CARRITO
========================================= */

.carrito {
    position: fixed;

    right: 20px;
    bottom: 20px;

    z-index: 100;

    width: min(360px, calc(100% - 40px));

    padding: 22px;

    background: #f5ecd9;

    border: 2px solid #9b7037;

    border-radius: 7px;

    box-shadow:
        0 10px 30px rgba(0,0,0,0.3);
}


.carrito h2 {
    color: #7b2927;

    margin-bottom: 15px;
}


.total {
    margin-top: 20px;

    padding-top: 15px;

    border-top: 1px solid #cdb58b;

    font-size: 20px;
}


#whatsapp {
    width: 100%;

    margin-top: 15px;

    padding: 13px;

    border: none;

    border-radius: 4px;

    background: #397447;

    color: white;

    font-weight: bold;

    cursor: pointer;
}


/* =========================================
   CELULAR
========================================= */

@media (max-width: 600px) {

    .portada-contenido {
        min-height: 80vh;

        padding: 50px 20px;
    }

    .categorias {
        justify-content: flex-start;

        overflow-x: auto;

        flex-wrap: nowrap;
    }

    .categorias a {
        flex-shrink: 0;
    }

    .categoria {
        padding: 
