<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Kurama Sushi</title>

<style>
/* =========================================================
   KURAMA SUSHI
   TODO EL SITIO EN UN SOLO ARCHIVO
   ========================================================= */

:root{
    --vino:#7b1e27;
    --vino-oscuro:#4d1017;
    --dorado:#c89b52;
    --crema:#f8f1df;
    --papel:#fffaf0;
    --marron:#351c16;
    --marron2:#5b3426;
    --texto:#2b1814;
    --sombra:0 15px 40px rgba(0,0,0,.25);
}

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:Georgia, "Times New Roman", serif;
    color:var(--texto);
    background:
        linear-gradient(rgba(45,23,16,.35),rgba(45,23,16,.55)),
        repeating-linear-gradient(
            90deg,
            #4a281c 0px,
            #4a281c 35px,
            #3b2018 36px,
            #3b2018 40px
        );
    min-height:100vh;
}

/* =========================================================
   FONDO RESTAURANTE
   ========================================================= */

.restaurant-bg{
    position:fixed;
    inset:0;
    z-index:-2;
    overflow:hidden;
    background:
        radial-gradient(circle at 50% 20%,rgba(255,190,100,.18),transparent 30%),
        linear-gradient(90deg,#291712,#633a27 25%,#44251c 50%,#633a27 75%,#291712);
}

.restaurant-bg::before{
    content:"";
    position:absolute;
    inset:0;
    background:
        repeating-linear-gradient(
            90deg,
            rgba(255,255,255,.025) 0px,
            rgba(255,255,255,.025) 2px,
            transparent 3px,
            transparent 70px
        ),
        repeating-linear-gradient(
            0deg,
            rgba(0,0,0,.12) 0px,
            rgba(0,0,0,.12) 3px,
            transparent 4px,
            transparent 55px
        );
}

/* techo */

.ceiling{
    position:absolute;
    top:0;
    left:0;
    width:100%;
    height:18%;
    background:
        repeating-linear-gradient(
            90deg,
            #2b1711 0px,
            #2b1711 25px,
            #573322 26px,
            #573322 90px
        );
    border-bottom:12px solid #24130e;
}

.ceiling::after{
    content:"";
    position:absolute;
    inset:20px 0 0;
    background:
        repeating-linear-gradient(
            0deg,
            transparent 0,
            transparent 40px,
            rgba(20,10,7,.7) 41px,
            rgba(20,10,7,.7) 50px
        );
}

/* =========================================================
   LÁMPARAS
   ========================================================= */

.lamp{
    position:absolute;
    width:70px;
    height:125px;
    border-radius:45%;
    background:
        repeating-linear-gradient(
            0deg,
            rgba(120,50,20,.35) 0px,
            rgba(120,50,20,.35) 3px,
            rgba(255,210,120,.85) 4px,
            rgba(255,210,120,.85) 13px
        );
    box-shadow:
        0 0 35px rgba(255,176,68,.65),
        inset 0 0 25px rgba(255,225,150,.4);
    z-index:1;
}

.lamp::before{
    content:"";
    position:absolute;
    width:2px;
    height:70px;
    background:#18100d;
    top:-70px;
    left:50%;
}

.lamp.one{top:8%;left:8%;transform:rotate(-3deg);}
.lamp.two{top:5%;left:44%;width:90px;height:145px;}
.lamp.three{top:8%;right:8%;transform:rotate(3deg);}
.lamp.four{top:28%;left:4%;width:55px;height:95px;}
.lamp.five{top:36%;right:4%;width:55px;height:95px;}
.lamp.six{bottom:22%;left:7%;width:42px;height:75px;background:#8e392a;}

/* =========================================================
   DECORACIÓN LATERAL
   ========================================================= */

.left-wall,
.right-shelf{
    position:absolute;
    top:18%;
    bottom:0;
}

.left-wall{
    left:0;
    width:20%;
    background:
        repeating-linear-gradient(
            90deg,
            #271610 0px,
            #271610 8px,
            #583321 9px,
            #583321 25px
        );
    opacity:.9;
}

.right-shelf{
    right:0;
    width:22%;
    background:#321b14;
    border-left:12px solid #1e100c;
    padding:25px 15px;
}

.shelf-row{
    height:22%;
    margin-bottom:10px;
    border:8px solid #5b3424;
    background:#24130f;
    display:flex;
    justify-content:space-around;
    align-items:center;
    box-shadow:inset 0 0 20px #000;
}

.bottle,
.bowl,
.plate{
    display:block;
    position:relative;
}

.bottle{
    width:20px;
    height:45px;
    border-radius:5px 5px 8px 8px;
    background:#58705c;
}

.bottle::before{
    content:"";
    position:absolute;
    width:8px;
    height:10px;
    background:#39231a;
    top:-8px;
    left:6px;
}

.bowl{
    width:38px;
    height:20px;
    border-radius:0 0 50% 50%;
    background:#d9d1bd;
}

.plate{
    width:42px;
    height:8px;
    border-radius:50%;
    background:#eee7d7;
}

/* =========================================================
   CONTENEDOR PRINCIPAL
   ========================================================= */

.page{
    width:min(1100px,94%);
    margin:auto;
    padding:25px 0 60px;
    position:relative;
}

/* =========================================================
   HOJA CENTRAL
   ========================================================= */

.menu-paper{
    width:72%;
    margin:80px auto 0;
    min-height:1500px;
    background:
        radial-gradient(rgba(100,80,50,.025) 1px,transparent 1px),
        var(--papel);
    background-size:7px 7px;
    padding:45px 7% 80px;
    position:relative;
    box-shadow:var(--sombra);
    clip-path:polygon(
        1% 0%,
        99% 1%,
        100% 30%,
        98% 65%,
        99% 99%,
        70% 100%,
        35% 99%,
        1% 100%,
        0% 70%,
        1% 35%
    );
}

.menu-paper::after{
    content:"";
    position:absolute;
    inset:0;
    box-shadow:inset 0 0 50px rgba(80,50,20,.06);
    pointer-events:none;
}

/* =========================================================
   HEADER
   ========================================================= */

header{
    text-align:center;
    position:relative;
    z-index:2;
}

.logo{
    width:180px;
    height:180px;
    margin:0 auto 10px;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    color:var(--vino);
}

.fox{
    font-size:75px;
    line-height:1;
    filter:sepia(.3);
}

.logo-kurama{
    font-size:34px;
    font-weight:bold;
    letter-spacing:5px;
}

.logo-sushi{
    font-size:17px;
    color:var(--dorado);
    letter-spacing:8px;
    margin-top:2px;
}

.subtitle{
    color:#765b42;
    font-size:14px;
    margin-bottom:25px;
}

/* =========================================================
   NAVEGACIÓN
   ========================================================= */

.nav{
    position:sticky;
    top:0;
    z-index:50;
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    gap:7px;
    padding:10px;
    background:rgba(255,250,240,.95);
    backdrop-filter:blur(8px);
    border-bottom:1px solid rgba(123,30,39,.15);
}

.nav button{
    border:none;
    background:transparent;
    color:var(--vino);
    padding:9px 13px;
    border-radius:20px;
    cursor:pointer;
    font-weight:bold;
    transition:.2s;
}

.nav button:hover{
    background:var(--vino);
    color:white;
}

/* =========================================================
   CATEGORÍAS
   ========================================================= */

.category{
    margin-top:55px;
    scroll-margin-top:70px;
}

.category-title{
    text-align:center;
    color:var(--vino);
    font-size:28px;
    margin-bottom:25px;
}

.category-title::after{
    content:"";
    display:block;
    width:60px;
    height:2px;
    background:var(--dorado);
    margin:9px auto;
}

/* =========================================================
   PRODUCTOS
   ========================================================= */

.products{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:18px;
}

.product{
    background:rgba(255,255,255,.65);
    border:1px solid rgba(123,30,39,.13);
    border-radius:12px;
    padding:17px;
    box-shadow:0 5px 15px rgba(60,30,15,.08);
    transition:.25s;
}

.product:hover{
    transform:translateY(-3px);
    box-shadow:0 10px 25px rgba(60,30,15,.15);
}

.product-image{
    height:140px;
    border-radius:8px;
    margin-bottom:12px;
    background:
        linear-gradient(135deg,#ead5ae,#c58a58);
    display:flex;
    align-items:center;
    justify-content:center;
    font-size:50px;
    overflow:hidden;
}

.product-image img{
    width:100%;
    height:100%;
    object-fit:cover;
}

.product h3{
    color:var(--vino-oscuro);
    margin-bottom:6px;
}

.description{
    color:#705a4b;
    font-size:13px;
    line-height:1.5;
    min-height:40px;
}

.price{
    font-size:20px;
    color:var(--vino);
    font-weight:bold;
    margin:10px 0;
}

.product-actions{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:8px;
}

.counter{
    display:flex;
    align-items:center;
    border:1px solid #c8b69a;
    border-radius:20px;
    overflow:hidden;
}

.counter button{
    border:none;
    width:32px;
    height:32px;
    background:#eee2cf;
    cursor:pointer;
    font-size:18px;
}

.counter span{
    width:30px;
    text-align:center;
}

.add-btn,
.whatsapp-btn,
.checkout-btn{
    border:none;
    background:var(--vino);
    color:white;
    padding:10px 15px;
    border-radius:20px;
    cursor:pointer;
    font-weight:bold;
    transition:.2s;
}

.add-btn:hover,
.whatsapp-btn:hover,
.checkout-btn:hover{
    background:var(--vino-oscuro);
    transform:scale(1.02);
}

/* =========================================================
   CONFIGURADOR
   ========================================================= */

.modal{
    position:fixed;
    inset:0;
    background:rgba(20,10,7,.7);
    display:none;
    justify-content:center;
    align-items:center;
    z-index:200;
    padding:15px;
}

.modal.active{
    display:flex;
}

.modal-box{
    width:min(520px,100%);
    max-height:90vh;
    overflow:auto;
    background:var(--papel);
    border-radius:18px;
    padding:25px;
    box-shadow:0 20px 70px rgba(0,0,0,.45);
}

.modal-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:20px;
}

.close{
    border:none;
    background:none;
    font-size:28px;
    cursor:pointer;
    color:var(--vino);
}

.option-group{
    margin:20px 0;
}

.option-group h4{
    color:var(--vino);
    margin-bottom:10px;
}

.option{
    display:flex;
    align-items:center;
    gap:8px;
    background:#f5ead7;
    margin:6px 0;
    padding:9px;
    border-radius:8px;
}

.option input{
    accent-color:var(--vino);
}

.selection-info{
    background:#ead9bf;
    padding:10px;
    border-radius:8px;
    font-size:13px;
    margin-bottom:10px;
}

.modal-total{
    font-size:23px;
    color:var(--vino);
    font-weight:bold;
    text-align:center;
    margin:20px;
}

/* =========================================================
   CARRITO
   ========================================================= */

.cart-button{
    position:fixed;
    right:20px;
    bottom:20px;
    width:60px;
    height:60px;
    border-radius:50%;
    border:none;
    background:var(--vino);
    color:white;
    font-size:25px;
    cursor:pointer;
    z-index:100;
    box-shadow:0 8px 25px rgba(0,0,0,.3);
}

.cart-count{
    position:absolute;
    right:-3px;
    top:-3px;
    width:23px;
    height:23px;
    background:var(--dorado);
    border-radius:50%;
    font-size:12px;
    display:flex;
    align-items:center;
    justify-content:center;
    color:#2b1814;
    font-weight:bold;
}

.cart{
    position:fixed;
    right:-450px;
    top:0;
    height:100%;
    width:min(420px,95%);
    background:var(--papel);
    z-index:150;
    box-shadow:-10px 0 40px rgba(0,0,0,.3);
    transition:.3s;
    padding:22px;
    overflow:auto;
}

.cart.open{
    right:0;
}

.cart-header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    border-bottom:1px solid #d7c6a9;
    padding-bottom:15px;
}

.cart-item{
    padding:15px 0;
    border-bottom:1px solid #dfd1ba;
}

.cart-item-title{
    font-weight:bold;
    color:var(--vino);
}

.cart-details{
    font-size:12px;
    color:#725c4d;
    margin:5px 0;
    line-height:1.5;
}

.cart-controls{
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.cart-controls button{
    border:none;
    background:#eadbc4;
    border-radius:5px;
    width:27px;
    height:27px;
    cursor:pointer;
}

.remove{
    color:#a22;
    background:none!important;
}

.cart-total{
    padding:20px 0;
    font-size:21px;
    font-weight:bold;
    color:var(--vino);
}

/* =========================================================
   CHECKOUT
   ========================================================= */

.checkout{
    margin-top:60px;
    padding:25px;
    background:rgba(255,255,255,.5);
    border-radius:15px;
}

.checkout h2{
    color:var(--vino);
    text-align:center;
    margin-bottom:20px;
}

.form-group{
    margin:15px 0;
}

.form-group label{
    display:block;
    font-weight:bold;
    margin-bottom:6px;
}

select{
    width:100%;
    padding:11px;
    border:1px solid #cdbb9f;
    border-radius:8px;
    background:#fffaf0;
    color:var(--texto);
}

.radio-group{
    display:flex;
    flex-direction:column;
    gap:8px;
}

.payment-message{
    display:none;
    background:#f0dfc3;
    padding:15px;
    border-radius:8px;
    font-size:13px;
    line-height:1.5;
}

.order-summary{
    margin-top:20px;
    border-top:1px solid #d4c3a7;
    padding-top:15px;
}

.final-total{
    font-size:25px;
    font-weight:bold;
    color:var(--vino);
    text-align:right;
    margin:15px 0;
}

/* =========================================================
   RESEÑAS
   ========================================================= */

.reviews{
    margin-top:60px;
    text-align:center;
}

.review-box{
    width:min(500px,90%);
    margin:20px auto;
    min-height:60px;
    position:relative;
}

.review{
    background:#e9f5e5;
    border-radius:15px 15px 5px 15px;
    padding:14px 18px;
    display:inline-block;
    box-shadow:0 4px 15px rgba(0,0,0,.08);
    animation:messageIn 5s ease-in-out infinite;
}

@keyframes messageIn{
    0%{opacity:0;transform:translateY(10px);}
    15%{opacity:1;transform:translateY(0);}
    75%{opacity:1;transform:translateY(0);}
    100%{opacity:0;transform:translateY(-10px);}
}

/* =========================================================
   FOOTER
   ========================================================= */

footer{
    margin-top:50px;
    text-align:center;
    padding:30px 10px 10px;
    border-top:1px solid #d5c5aa;
    color:#705849;
}

.socials{
    display:flex;
    justify-content:center;
    gap:15px;
    margin:15px;
}

.social{
    text-decoration:none;
    color:white;
    background:var(--vino);
    width:45px;
    height:45px;
    border-radius:50%;
    display:flex;
    justify-content:center;
    align-items:center;
    font-weight:bold;
}

.transfer{
    display:none;
}

/* =========================================================
   RESPONSIVE
   ========================================================= */

@media(max-width:700px){

    .page{
        width:100%;
    }

    .menu-paper{
        width:94%;
        margin-top:50px;
        padding:35px 6% 60px;
        min-height:0;
        clip-path:none;
        border-radius:4px;
    }

    .left-wall,
    .right-shelf{
        opacity:.4;
    }

    .products{
        grid-template-columns:1fr;
    }

    .product-image{
        height:170px;
    }

    .nav{
        overflow-x:auto;
        justify-content:flex-start;
        flex-wrap:nowrap;
    }

    .nav button{
        white-space:nowrap;
    }

    .logo{
        width:150px;
        height:150px;
    }

    .fox{
        font-size:60px;
    }

    .logo-kurama{
        font-size:27px;
    }

    .category-title{
        font-size:25px;
    }
}
</style>
</head>

<body>

<div class="restaurant-bg">
    <div class="ceiling"></div>

    <div class="lamp one"></div>
    <div class="lamp two"></div>
    <div class="lamp three"></div>
    <div class="lamp four"></div>
    <div class="lamp five"></div>
    <div class="lamp six"></div>

    <div class="left-wall"></div>

    <div class="right-shelf">
        <div class="shelf-row">
            <span class="bottle"></span>
            <span class="bottle"></span>
            <span class="bowl"></span>
        </div>

        <div class="shelf-row">
            <span class="plate"></span>
            <span class="bowl"></span>
            <span class="bottle"></span>
        </div>

        <div class="shelf-row">
            <span class="bottle"></span>
            <span class="plate"></span>
            <span class="bowl"></span>
        </div>

        <div class="shelf-row">
            <span class="plate"></span>
            <span class="plate"></span>
            <span class="bowl"></span>
        </div>
    </div>
</div>

<main class="page">

<div class="menu-paper">

<header>

    <div class="logo">
        <div class="fox">🦊</div>
        <div class="logo-kurama">KURAMA</div>
        <div class="logo-sushi">SUSHI</div>
    </div>

    <div class="subtitle">
        Sushi artesanal hecho con cariño 🍣
    </div>

</header>

<nav class="nav">

    <button onclick="goTo('sushi')">🍣 Sushi</button>
    <button onclick="goTo('cortes')">🥢 Cortes</button>
    <button onclick="goTo('arma')">🍱 Arma tu pedido</button>
    <button onclick="goTo('box')">📦 Box</button>
    <button onclick="goTo('agregar')">➕ Agregar</button>

</nav>


<!-- =====================================================
     SUSHI
     ===================================================== -->

<section class="category" id="sushi">

<h2 class="category-title">🍣 Sushi</h2>

<div class="products">

<script>
const sushiProducts = [
    ["Sushi mixto - 30 piezas","$13.500",13500,"30 piezas mixtas a elección del chef.","🍣"],
    ["Sushi mixto - 40 piezas","$17.500",17500,"40 piezas mixtas a elección del chef.","🍣"],
    ["Sushi mixto - 50 piezas","$22.500",22500,"50 piezas mixtas a elección del chef.","🍣"],
    ["Sushi mixto - 60 piezas","$27.500",27500,"60 piezas mixtas a elección del chef.","🍣"]
];

document.write(
sushiProducts.map((p,i)=>`
<div class="product">
    <div class="product-image">${p[4]}</div>
    <h3>${p[0]}</h3>
    <p class="description">${p[3]}</p>
    <div class="price">${p[1]}</div>

    <div class="product-actions">
        <div class="counter">
            <button onclick="changeQuick(${i},-1)">−</button>
            <span id="sushiQty${i}">1</span>
            <button onclick="changeQuick(${i},1)">+</button>
        </div>

        <button class="add-btn"
            onclick="addSushi(${i})">
            Agregar
        </button>
    </div>
</div>
`).join("")
);
</script>

</div>
</section>


<!-- =====================================================
     CORTES
     ===================================================== -->

<section class="category" id="cortes">

<h2 class="category-title">🥢 Cortes</h2>

<div class="products" id="cortesProducts"></div>

</section>


<!-- =====================================================
     ARMA TU PEDIDO
     ===================================================== -->

<section class="category" id="arma">

<h2 class="category-title">🍱 Arma tu pedido</h2>

<div class="products" id="armaProducts"></div>

</section>


<!-- =====================================================
     BOX
     ===================================================== -->

<section class="category" id="box">

<h2 class="category-title">📦 Box</h2>

<div class="products" id="boxProducts"></div>

</section>


<!-- =====================================================
     AGREGAR
     =====================
