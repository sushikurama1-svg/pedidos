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
