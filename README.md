<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Kurama Sushi | Catálogo</title>

<style>
/* =========================================================
   KURAMA SUSHI
   CATÁLOGO + CONFIGURADOR + CARRITO
   ========================================================= */

:root {
    --vino: #7d1f25;
    --vino-oscuro: #541318;
    --dorado: #b89452;
    --crema: #f7f0df;
    --papel: #fffdf6;
    --madera: #3b2118;
    --madera2: #5a3324;
    --texto: #30231d;
    --verde: #536548;
    --sombra: rgba(0,0,0,.25);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Georgia, "Times New Roman", serif;
    color: var(--texto);
    background:
        linear-gradient(rgba(48,27,20,.55),rgba(48,27,20,.55)),
        url("fondo-kurama.jpg") center top / cover fixed;
    min-height: 100vh;
}

/* =========================================================
   ENCABEZADO
   ========================================================= */

header {
    padding: 25px 15px 15px;
    text-align: center;
    color: white;
}

.logo {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 18px;
}

.logo-icon {
    font-size: 65px;
    line-height: 1;
    filter: drop-shadow(0 3px 4px #000);
}

.logo h1 {
    color: #9d252b;
    font-size: clamp(35px, 8vw, 58px);
    letter-spacing: 4px;
    text-shadow: 1px 2px 0 #fff;
}

.logo span {
    color: #d2ad67;
    font-size: 18px;
    letter-spacing: 7px;
}

/* =========================================================
   NAVEGACIÓN
   ========================================================= */

.nav {
    position: sticky;
    top: 0;
    z-index: 50;
    display: flex;
    gap: 8px;
    overflow-x: auto;
    padding: 10px;
    background: rgba(54,29,21,.95);
    box-shadow: 0 4px 12px rgba(0,0,0,.3);
}

.nav button {
    flex: 0 0 auto;
    border: 1px solid #b89452;
    background: transparent;
    color: white;
    border-radius: 30px;
    padding: 10px 16px;
    cursor: pointer;
    font-weight: bold;
}

.nav button:hover {
    background: #b89452;
    color: #29150f;
}

/* =========================================================
   HOJA CENTRAL
   ========================================================= */

.paper {
    width: min(94%, 1100px);
    margin: 20px auto 80px;
    background:
        radial-gradient(circle at 20% 20%, rgba(150,120,70,.04) 0 1px, transparent 2px),
        radial-gradient(circle at 70% 80%, rgba(150,120,70,.03) 0 1px, transparent 2px),
        var(--papel);
    background-size: 12px 12px, 17px 17px, auto;
    min-height: 900px;
    padding: 35px 20px 80px;
    box-shadow: 0 15px 35px var(--sombra);
    border-radius: 4px;
    position: relative;
}

.paper:before {
    content: "";
    position: absolute;
    inset: 0;
    pointer-events: none;
    border: 1px solid rgba(100,70,40,.1);
}

/* =========================================================
   TÍTULOS
   ========================================================= */

.section {
    scroll-margin-top: 80px;
    margin-top: 55px;
}

.section:first-of-type {
    margin-top: 15px;
}

.section-title {
    text-align: center;
    color: var(--vino);
    font-size: clamp(28px, 6vw, 42px);
    margin-bottom: 8px;
}

.section-subtitle {
    text-align: center;
    color: #80664d;
    margin-bottom: 25px;
}

/* =========================================================
   PRODUCTOS
   ========================================================= */

.products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 18px;
}

.product {
    background: rgba(255,255,255,.86);
    border: 1px solid #dfd2bc;
    border-radius: 15px;
    padding: 18px;
    box-shadow: 0 5px 15px rgba(70,40,20,.1);
    transition: .2s;
}

.product:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 20px rgba(70,40,20,.16);
}

.product h3 {
    color: var(--vino);
    font-size: 21px;
    margin-bottom: 7px;
}

.description {
    font-size: 14px;
    color: #66564c;
    min-height: 40px;
    line-height: 1.45;
}

.price {
    font-size: 22px;
    font-weight: bold;
    color: #8d6325;
    margin: 12px 0;
}

/* =========================================================
   CONTADOR
   ========================================================= */

.quantity {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    margin: 10px 0;
}

.quantity button {
    width: 38px;
    height: 38px;
    border: none;
    border-radius: 50%;
    background: var(--vino);
    color: white;
    font-size: 22px;
    cursor: pointer;
}

.quantity span {
    min-width: 25px;
    text-align: center;
    font-weight: bold;
}

/* =========================================================
   BOTONES
   ========================================================= */

.btn {
    width: 100%;
    padding: 12px 15px;
    border: none;
    border-radius: 10px;
    background: var(--vino);
    color: white;
    font-weight: bold;
    cursor: pointer;
    transition: .2s;
}

.btn:hover {
    background: var(--vino-oscuro);
    transform: scale(1.01);
}

.btn.gold {
    background: var(--dorado);
    color: #2c1a12;
}

/* =========================================================
   CARRITO
   ========================================================= */

.cart-button {
    position: fixed;
    right: 18px;
    bottom: 18px;
    z-index: 100;
    width: 62px;
    height: 62px;
    border-radius: 50%;
    border: 3px solid white;
    background: var(--vino);
    color: white;
    font-size: 26px;
    cursor: pointer;
    box-shadow: 0 5px 18px rgba(0,0,0,.35);
}

.cart-count {
    position: absolute;
    right: -3px;
    top: -5px;
    background: var(--dorado);
    color: #24140e;
    font-size: 13px;
    min-width: 22px;
    height: 22px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
}

.cart-panel {
    position: fixed;
    top: 0;
    right: -430px;
    width: min(430px, 100%);
    height: 100vh;
    background: var(--crema);
    z-index: 200;
    box-shadow: -5px 0 25px rgba(0,0,0,.3);
    transition: .3s;
    display: flex;
    flex-direction: column;
}

.cart-panel.open {
    right: 0;
}

.cart-header {
    background: var(--vino);
    color: white;
    padding: 18px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.cart-header button {
    background: none;
    color: white;
    border: none;
    font-size: 25px;
    cursor: pointer;
}

.cart-items {
    flex: 1;
    overflow-y: auto;
    padding: 15px;
}

.cart-item {
    background: white;
    border-radius: 10px;
    padding: 13px;
    margin-bottom: 12px;
    border: 1px solid #ddd0bc;
}

.cart-item h4 {
    color: var(--vino);
    margin-bottom: 5px;
}

.cart-item small {
    display: block;
    color: #66564c;
    line-height: 1.5;
}

.cart-actions {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-top: 9px;
}

.cart-actions button {
    border: none;
    background: var(--vino);
    color: white;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    cursor: pointer;
}

.cart-footer {
    padding: 18px;
    border-top: 1px solid #d4c5ae;
    background: #fffaf0;
}

.total {
    font-size: 25px;
    font-weight: bold;
    text-align: center;
    margin-bottom: 12px;
    color: var(--vino);
}

/* =========================================================
   MODAL CONFIGURADOR
   ========================================================= */

.modal {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 300;
    background: rgba(0,0,0,.68);
    padding: 15px;
    overflow-y: auto;
}

.modal.open {
    display: flex;
    align-items: center;
    justify-content: center;
}

.modal-box {
    width: min(600px, 100%);
    max-height: 94vh;
    overflow-y: auto;
    background: var(--papel);
    border-radius: 18px;
    padding: 22px;
    box-shadow: 0 15px 50px rgba(0,0,0,.45);
}

.modal-header {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    margin-bottom: 18px;
}

.modal-header h2 {
    color: var(--vino);
}

.close {
    border: none;
    background: transparent;
    font-size: 28px;
    cursor: pointer;
}

.config-group {
    margin-bottom: 20px;
}

.config-group h3 {
    color: var(--vino);
    margin-bottom: 10px;
}

.option-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 8px;
}

.option {
    border: 1px solid #d3c2a8;
    background: white;
    border-radius: 9px;
    padding: 11px;
    cursor: pointer;
}

.option.selected {
    background: #f2dfbd;
    border: 2px solid var(--vino);
}

.option input {
    display: none;
}

.selection-note {
    background: #f4ead8;
    padding: 10px;
    border-radius: 8px;
    margin-bottom: 15px;
    font-size: 14px;
}

/* =========================================================
   OVERLAY
   ========================================================= */

.overlay {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 150;
    background: rgba(0,0,0,.35);
}

.overlay.show {
    display: block;
}

/* =========================================================
   RESPONSIVE
   ========================================================= */

@media(max-width:600px) {

    .paper {
        width: 96%;
        padding: 25px 13px 70px;
    }

    .products {
        grid-template-columns: 1fr;
    }

    .option-grid {
        grid-template-columns: 1fr;
    }

    .logo-icon {
        font-size: 50px;
    }
}
</style>
</head>

<body>

<header>
    <div class="logo">
        <div class="logo-icon">🦊</div>
        <h1>KURAMA</h1>
        <span>SUSHI</span>
    </div>
</header>

<nav class="nav">
    <button onclick="goTo('sushi')">🍣 Sushi</button>
    <button onclick="goTo('cortes')">🥢 Cortes</button>
    <button onclick="goTo('arma')">🍙 Arma tu pedido</button>
    <button onclick="goTo('box')">📦 Box</button>
    <button onclick="goTo('agregar')">➕ Agregar</button>
</nav>

<main class="paper">

<!-- =====================================================
     SUSHI
     ===================================================== -->

<section id="sushi" class="section">

    <h2 class="section-title">🍣 Sushi</h2>

    <p class="section-subtitle">
        Sushi mixto a elección del chef.
        Tú eliges la cantidad, el chef se encarga de la combinación.
    </p>

    <div class="products">

        <article class="product">
            <h3>30 piezas mixtas</h3>
            <p class="description">
                Sushi mixto a elección del chef.
            </p>
            <div class="price">$13.500</div>
            <div class="quantity">
                <button onclick="changeQty('sushi30',-1)">−</button>
                <span id="qty-sushi30">1</span>
                <button onclick="changeQty('sushi30',1)">+</button>
            </div>
            <button class="btn"
                onclick="addFixed('Sushi mixto 30 piezas',13500,'sushi30')">
                Agregar al carrito
            </button>
        </article>

        <article class="product">
            <h3>40 piezas mixtas</h3>
            <p class="description">Sushi mixto a elección del chef.</p>
            <div class="price">$17.500</div>
            <div class="quantity">
                <button onclick="changeQty('sushi40',-1)">−</button>
                <span id="qty-sushi40">1</span>
                <button onclick="changeQty('sushi40',1)">+</button>
            </div>
            <button class="btn"
                onclick="addFixed('Sushi mixto 40 piezas',17500,'sushi40')">
                Agregar al carrito
            </button>
        </article>

        <article class="product">
            <h3>50 piezas mixtas</h3>
            <p class="description">Sushi mixto a elección del chef.</p>
            <div class="price">$22.500</div>
            <div class="quantity">
                <button onclick="changeQty('sushi50',-1)">−</button>
                <span id="qty-sushi50">1</span>
                <button onclick="changeQty('sushi50',1)">+</button>
            </div>
            <button class="btn"
                onclick="addFixed('Sushi mixto 50 piezas',22500,'sushi50')">
                Agregar al carrito
            </button>
        </article>

        <article class="product">
            <h3>60 piezas mixtas</h3>
            <p class="description">Sushi mixto a elección del chef.</p>
            <div class="price">$27.500</div>
            <div class="quantity">
                <button onclick="changeQty('sushi60',-1)">−</button>
                <span id="qty-sushi60">1</span>
                <button onclick="changeQty('sushi60',1)">+</button>
            </div>
            <button class="btn"
                onclick="addFixed('Sushi mixto 60 piezas',27500,'sushi60')">
                Agregar al carrito
            </button>
        </article>

    </div>
</section>


<!-- =====================================================
     CORTES
     ===================================================== -->

<section id="cortes" class="section">

<h2 class="section-title">🥢 Cortes</h2>

<p class="section-subtitle">
    Todos incluyen 1 proteína + 2 secundarios.
</p>

<div class="products">

    <script>
    const cortes = [
        ["Panko",5000],
        ["Tempura",5000],
        ["Queso",5500],
        ["Palta",5500],
        ["Nori",4500],
        ["Sésamo",4500]
    ];
    </script>

</div>

<div id="cortes-container" class="products"></div>

</section>


<!-- =====================================================
     ARMA TU PEDIDO
     ===================================================== -->

<section id="arma" class="section">

<h2 class="section-title">🍙 Arma tu pedido</h2>

<p class="section-subtitle">
    Personaliza tu pedido eligiendo exactamente los ingredientes permitidos.
</p>

<div id="arma-container" class="products"></div>

</section>


<!-- =====================================================
     BOX
     ===================================================== -->

<section id="box" class="section">

<h2 class="section-title">📦 Box</h2>

<div class="products">

    <article class="product">
        <h3>Box normal</h3>
        <p class="description">
            2 rolls acevichados + 6 aros de cebolla +
            6 arrollados primavera.
        </p>
        <div class="price">$21.000</div>
        <button class="btn" onclick="openBoxNormal()">
            Personalizar Box
        </button>
    </article>

    <article class="product">
        <h3>Box</h3>
        <p class="description">
            3 handroll de pollo, palta y queso +
            6 arrollados primavera.
        </p>
        <div class="price">$14.000</div>
        <button class="btn"
            onclick="addFixed('Box 3 handroll pollo, palta y queso + 6 arrollados',14000,'box')">
            Agregar al carrito
        </button>
    </article>

    <article class="product">
        <h3>Box Premium</h3>
        <p class="description">
            40 piezas de sushi + 6 empanadas de queso +
            6 arrollados primavera + 6 aros de cebolla +
            5 piezas de pollo apanado.
        </p>
        <div class="price">$32.000</div>
        <button class="btn"
            onclick="addFixed('Box Premium',32000,'premium')">
            Agregar al carrito
        </button>
    </article>

</div>
</section>


<!-- =====================================================
     AGREGAR
     ===================================================== -->

<section id="agregar" class="section">

<h2 class="section-title">➕ Agregar</h2>

<div class="products">

    <article class="product">
        <h3>6 aros de cebolla</h3>
        <div class="price">$3.000</div>

        <div class="quantity">
            <button onclick="changeQty('aros',-1)">−</button>
            <span id="qty-aros">1</span>
            <button onclick="changeQty('aros',1)">+</button>
        </div>

        <button class="btn"
            onclick="addFixed('6 aros de cebolla',3000,'aros')">
            Agregar
        </button>
    </article>

    <article class="product">
        <h3>6 arrollados primavera</h3>
        <div class="price">$3.000</div>

        <div class="quantity">
            <button onclick="changeQty('arrollados',-1)">−</button>
            <span id="qty-arrollados">1</span>
            <button onclick="changeQty('arrollados',1)">+</button>
        </div>

        <button class="btn"
            onclick="addFixed('6 arrollados primavera',3000,'arrollados')">
            Agregar
        </button>
    </article>

    <article class="product">
        <h3>6 empanadas de queso</h3>
        <div class="price">$3.000</div>

        <div class="quantity">
            <button onclick="changeQty('empanadas',-1)">−</button>
            <span id="qty-empanadas">1</span>
            <button onclick="changeQty('empanadas',1)">+</button>
        </div>

        <button class="btn"
            onclick="addFixed('6 empanadas de queso',3000,'empanadas')">
            Agregar
        </button>
    </article>

</div>
</section>

</main>


<!-- =====================================================
     BOTÓN CARRITO
     ===================================================== -->

<button class="cart-button" onclick="toggleCart()">
    🛒
    <span class="cart-count" id="cart-count">0</span>
</button>

<div class="overlay" id="overlay" onclick="toggleCart()"></div>

<!-- =====================================================
     CARRITO
     ===================================================== -->

<aside class="cart-panel" id="cart">

    <div class="cart-header">
        <h2>Tu pedido</h2>
        <button onclick="toggleCart()">×</button>
    </div>

    <div class="cart-items" id="cart-items">
        <p style="text-align:center;margin-top:30px;">
            Tu carrito está vacío 🍣
        </p>
    </div>

    <div class="cart-footer">

        <div class="total">
            Total: $<span id="cart-total">0</span>
        </div>

        <button class="btn" onclick="sendWhatsApp()">
            📲 Pedir por WhatsApp
        </button>

        <br><br>

        <button class="btn gold" onclick="clearCart()">
            Vaciar carrito
        </button>

    </div>

</aside>


<!-- =====================================================
     MODAL CONFIGURADOR
     ===================================================== -->

<div class="modal" id="modal">

    <div class="modal-box">

        <div class="modal-header">
            <h2 id="modal-title">Personalizar</h2>
            <button class="close" onclick="closeModal()">×</button>
        </div>

        <div id="modal-content"></div>

        <button class="btn" onclick="confirmConfiguration()">
            Agregar al carrito
        </button>

    </div>

</div>


<script>

/* =========================================================
   DATOS
   ========================================================= */

const proteins = [
    "Pollo apanado",
    "Camarón"
];

const sides = [
    "Queso",
    "Palta",
    "Morrón",
    "Cebollín",
    "Champiñón"
];

const wrappers = [
    "Palta",
    "Queso",
    "Nori",
    "Sésamo",
    "Panko",
    "Tempura"
];

const restrictedWrappers = [
    "Panko",
    "Tempura"
];

let cart = [];

let quantities = {
    sushi30:1,
    sushi40:1,
    sushi50:1,
    sushi60:1,
    aros:1,
    arrollados:1,
    empanadas:1
};

let currentConfig = null;


/* =========================================================
   NAVEGACIÓN
   ========================================================= */

function goTo(id) {
    document.getElementById(id).scrollIntoView({
        behavior:"smooth",
        block:"start"
    });
}


/* =========================================================
   CANTIDA
