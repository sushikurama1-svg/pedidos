<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Kurama Sushi - Fondo Sakura</title>

<style>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    overflow-x: hidden;

    background:
        linear-gradient(
            rgba(73, 42, 28, 0.12),
            rgba(73, 42, 28, 0.12)
        ),
        #9b6748;

    font-family: Georgia, "Times New Roman", serif;
}


/* =========================================
   ESCENARIO PRINCIPAL
========================================= */

.escenario {
    position: relative;

    width: 100%;
    min-height: 100vh;

    overflow: hidden;

    background:
        linear-gradient(
            to bottom,
            #654029 0%,
            #87563a 20%,
            #b77f5c 60%,
            #8c5a3d 100%
        );
}


/* =========================================
   TECHO DE MADERA
========================================= */

.techo {
    position: absolute;

    top: 0;
    left: 0;

    width: 100%;
    height: 17%;

    background:
        repeating-linear-gradient(
            90deg,
            #4a2b1b 0px,
            #4a2b1b 9px,
            #70462d 9px,
            #70462d 70px,
            #3f2518 70px,
            #3f2518 79px
        );

    border-bottom: 7px solid #382015;

    z-index: 1;
}


/* =========================================
   VIGAS
========================================= */

.viga {
    position: absolute;

    top: 0;

    width: 19px;
    height: 18%;

    background: #3b2317;

    box-shadow:
        inset -4px 0 rgba(255,255,255,0.05),
        4px 0 rgba(0,0,0,0.18);

    z-index: 3;
}

.viga1 {
    left: 17%;
}

.viga2 {
    left: 50%;
}

.viga3 {
    right: 17%;
}


/* =========================================
   LÁMPARAS JAPONESAS
========================================= */

.lampara {
    position: absolute;

    top: 5%;

    width: 78px;
    height: 105px;

    background:
        linear-gradient(
            to right,
            #c87335,
            #f2bd65,
            #d67e38
        );

    border-radius:
        12px 12px 25px 25px;

    box-shadow:
        0 10px 35px rgba(255, 190, 90, 0.35),
        0 12px 30px rgba(0,0,0,0.25);

    z-index: 5;
}

.lampara::before {
    content: "";

    position: absolute;

    top: -55px;
    left: 50%;

    width: 4px;
    height: 55px;

    transform: translateX(-50%);

    background: #302015;
}

.lampara::after {
    content: "";

    position: absolute;

    inset: 10px;

    border-left: 2px solid rgba(110,55,20,0.2);
    border-right: 2px solid rgba(110,55,20,0.2);

    border-radius: 10px;
}

.lampara1 {
    left: 5%;
}

.lampara2 {
    left: 44%;

    transform: scale(1.15);
}

.lampara3 {
    right: 5%;
}


/* =========================================
   PARED IZQUIERDA
========================================= */

.pared {
    position: absolute;

    left: 0;
    top: 17%;

    width: 21%;
    height: 83%;

    background:
        repeating-linear-gradient(
            90deg,
            #51321f 0px,
            #51321f 8px,
            #825237 8px,
            #825237 27px
        );

    box-shadow:
        inset -12px 0 20px rgba(0,0,0,0.25);

    z-index: 2;
}


/* =========================================
   ESTANTERÍA DERECHA
========================================= */

.estanteria {
    position: absolute;

    right: 0;
    top: 22%;

    width: 22%;
    height: 60%;

    background:
        linear-gradient(
            to bottom,
            #583520,
            #765039
        );

    border-left: 12px solid #3d2417;

    z-index: 2;
}

.repisa {
    position: relative;

    width: 100%;
    height: 25%;

    border-bottom: 10px solid #402517;
}


/* CERÁMICAS */

.plato {
    position: absolute;

    bottom: 15px;

    width: 38px;
    height: 15px;

    border-radius: 50%;

    background: #d6c19f;

    box-shadow:
        0 3px 4px rgba(0,0,0,0.3);
}

.plato1 {
    left: 25px;
}

.plato2 {
    right: 30px;
}

.frase {
    position: absolute;

    bottom: 30px;
    left: 45%;

    width: 15px;
    height: 42px;

    border-radius: 4px;

    background: #a9563c;
}


/* =========================================
   RAMAS DE SAKURA
========================================= */

.rama {
    position: absolute;

    z-index: 8;

    pointer-events: none;
}


/* RAMA SUPERIOR IZQUIERDA */

.rama-izquierda {
    top: 3%;
    left: -3%;

    width: 40%;
    height: 35%;

    transform: rotate(-8deg);
}


/* RAMA SUPERIOR DERECHA */

.rama-derecha {
    top: 8%;
    right: -5%;

    width: 42%;
    height: 35%;

    transform: scaleX(-1) rotate(-10deg);
}


/* RAMA INFERIOR IZQUIERDA */

.rama-abajo {
    bottom: 8%;
    left: -5%;

    width: 34%;
    height: 30%;

    transform: rotate(15deg);
}


/* TRONCO DE RAMA */

.tronco {
    position: absolute;

    width: 75%;
    height: 14px;

    background:
        linear-gradient(
            to bottom,
            #422719,
            #70452d,
            #392217
        );

    border-radius: 50px;

    transform: rotate(-20deg);

    box-shadow:
        0 3px 5px rgba(0,0,0,0.25);
}

.rama-derecha .tronco {
    transform: rotate(20deg);
}

.rama-abajo .tronco {
    transform: rotate(-10deg);
}


/* RAMITAS */

.ramita {
    position: absolute;

    width: 110px;
    height: 7px;

    background: #50301e;

    border-radius: 20px;
}


/* =========================================
   FLORES SAKURA
========================================= */

.flor {
    position: absolute;

    width: 38px;
    height: 38px;

    z-index: 10;
}


/* PÉTALOS */

.flor span {
    position: absolute;

    width: 17px;
    height: 22px;

    background:
        radial-gradient(
            circle at 50% 75%,
            #fff1f2 0%,
            #f7c1cb 65%,
            #df8e9e 100%
        );

    border-radius:
        50% 50% 45% 45%;

    transform-origin: bottom center;
}


/* CINCO PÉTALOS */

.flor span:nth-child(1) {
    top: 0;
    left: 11px;
    transform: rotate(0deg);
}

.flor span:nth-child(2) {
    top: 9px;
    left: 22px;
    transform: rotate(72deg);
}

.flor span:nth-child(3) {
    top: 20px;
    left: 15px;
    transform: rotate(144deg);
}

.flor span:nth-child(4) {
    top: 18px;
    left: 2px;
    transform: rotate(216deg);
}

.flor span:nth-child(5) {
    top: 8px;
    left: 0;
    transform: rotate(288deg);
}


/* CENTRO DE LA FLOR */

.flor::after {
    content: "";

    position: absolute;

    top: 14px;
    left: 14px;

    width: 10px;
    height: 10px;

    background: #c87a61;

    border-radius: 50%;

    box-shadow:
        0 0 0 3px rgba(255,255,255,0.2);
}


/* =========================================
   FLORES POSICIONADAS
========================================= */

.f1 {
    top: 9%;
    left: 9%;
}

.f2 {
    top: 16%;
    left: 20%;

    transform: scale(0.7);
}

.f3 {
    top: 6%;
    right: 10%;

    transform: scale(1.1);
}

.f4 {
    top: 19%;
    right: 20%;

    transform: scale(0.65);
}

.f5 {
    top: 30%;
    left: 7%;

    transform: scale(0.8);
}

.f6 {
    bottom: 22%;
    left: 8%;

    transform: scale(0.75);
}

.f7 {
    bottom: 15%;
    right: 8%;

    transform: scale(0.9);
}


/* =========================================
   PÉTALOS SUELTOS
========================================= */

.petalo {
    position: absolute;

    width: 13px;
    height: 20px;

    background:
        linear-gradient(
            135deg,
            #f6c4cd,
            #dd8798
        );

    border-radius:
        70% 30% 70% 30%;

    opacity: 0.9;

    z-index: 9;

    transform: rotate(35deg);
}

.p1 {
    top: 26%;
    left: 13%;
}

.p2 {
    top: 34%;
    right: 13%;
}

.p3 {
    top: 43%;
    left: 8%;
}

.p4 {
    top: 52%;
    right: 10%;
}

.p5 {
    bottom: 28%;
    left: 16%;
}

.p6 {
    bottom: 20%;
    right: 17%;
}

.p7 {
    top: 25%;
    right: 28%;
}


/* =========================================
   MOSTRADOR
========================================= */

.mostrador {
    position: absolute;

    bottom: 0;
    left: 0;

    width: 100%;
    height: 17%;

    background:
        linear-gradient(
            to bottom,
            #71452d,
            #47291b
        );

    border-top: 10px solid #8b593a;

    z-index: 4;
}


/* =========================================
   HOJA CENTRAL DEL MENÚ
========================================= */

.hoja {
    position: absolute;

    left: 19%;
    top: 11%;

    width: 62%;
    height: 82%;

    background:
        radial-gradient(
            ellipse at 20% 15%,
            rgba(255,255,255,0.7),
            transparent 45%
        ),

        radial-gradient(
            ellipse at 80% 85%,
            rgba(150,110,70,0.12),
            transparent 50%
        ),

        #f4ecd9;

    box-shadow:
        12px 15px 35px rgba(0,0,0,0.3);

    z-index: 7;

    overflow: hidden;

    border-radius:
        5px 8px 4px 7px;

    transform: rotate(-0.2deg);
}


/* TEXTURA PAPEL */

.hoja::before {
    content: "";

    position: absolute;

    inset: 0;

    background-image:
        radial-gradient(
            rgba(100,70,40,0.2) 0.6px,
            transparent 0.7px
        );

    background-size: 6px 6px;

    opacity: 0.2;

    pointer-events: none;
}


/* BORDE INFERIOR */

.hoja::after {
    content: "";

    position: absolute;

    bottom: 0;
    left: 0;

    width: 100%;
    height: 9px;

    background:
        repeating-linear-gradient(
            90deg,
            #e5d9bd 0px,
            #f4ecd9 25px,
            #dfd0b0 45px,
            #f4ecd9 65px
        );
}


/* =========================================
   RESPONSIVE PARA CELULAR
========================================= */

@media (max-width: 700px) {

    .hoja {
        left: 8%;
        width: 84%;

        top: 10%;
        height: 83%;
    }

    .pared {
        width: 7%;
    }

    .estanteria {
        width: 9%;
    }

    .lampara {
        width: 52px;
        height: 75px;
    }

    .lampara2 {
        transform: scale(0.8);
    }

    .rama-izquierda {
        width: 48%;
    }

    .rama-derecha {
        width: 48%;
    }

    .flor {
        transform: scale(0.75);
    }

}

</style>
</head>


<body>

<div class="escenario">

    <!-- TECHO -->
    <div class="techo"></div>

    <!-- VIGAS -->
    <div class="viga viga1"></div>
    <div class="viga viga2"></div>
    <div class="viga viga3"></div>


    <!-- LÁMPARAS -->
    <div class="lampara lampara1"></div>
    <div class="lampara lampara2"></div>
    <div class="lampara lampara3"></div>


    <!-- PARED -->
    <div class="pared"></div>


    <!-- ESTANTERÍA -->
    <div class="estanteria">

        <div class="repisa">
            <div class="plato plato1"></div>
            <div class="plato plato2"></div>
        </div>

        <div class="repisa">
            <div class="frase"></div>
        </div>

        <div class="repisa">
            <div class="plato plato1"></div>
        </div>

        <div class="repisa"></div>

    </div>


    <!-- =====================================
         RAMAS SAKURA
    ====================================== -->

    <div class="rama rama-izquierda">
        <div class="tronco"></div>
    </div>

    <div class="rama rama-derecha">
        <div class="tronco"></div>
    </div>

    <div class="rama rama-abajo">
        <div class="tronco"></div>
    </div>


    <!-- =====================================
         FLORES
    ====================================== -->

    <div class="flor f1">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f2">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f3">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f4">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f5">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f6">
        <span></span><span></span><span></span><span></span><span></span>
    </div>

    <div class="flor f7">
        <span></span><span></span><span></span><span></span><span></span>
    </div>


    <!-- PÉTALOS SUELTOS -->

    <div class="petalo p1"></div>
    <div class="petalo p2"></div>
    <div class="petalo p3"></div>
    <div class="petalo p4"></div>
    <div class="petalo p5"></div>
    <div class="petalo p6"></div>
    <div class="petalo p7"></div>


    <!-- MOSTRADOR -->
    <div class="mostrador"></div>


    <!-- HOJA CENTRAL -->
    <div class="hoja"></div>

</div>

</body>
</html>
