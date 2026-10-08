<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Kurama Sushi</title>

  <style>

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      background:
        linear-gradient(
          rgba(86, 48, 28, 0.15),
          rgba(86, 48, 28, 0.15)
        ),
        #9b6947;

      display: flex;
      justify-content: center;
      align-items: center;

      font-family: Georgia, "Times New Roman", serif;

      overflow-x: hidden;
    }

    /* ESCENARIO COMPLETO */

    .escenario {
      position: relative;

      width: 100%;
      min-height: 100vh;

      overflow: hidden;

      background:
        linear-gradient(
          to bottom,
          #6e432b 0%,
          #8c5b3d 18%,
          #b9825d 55%,
          #9b6848 100%
        );
    }


    /* TECHO DE MADERA */

    .techo {
      position: absolute;

      top: 0;
      left: 0;

      width: 100%;
      height: 17%;

      background:
        repeating-linear-gradient(
          90deg,
          #55331f 0px,
          #55331f 8px,
          #73472d 8px,
          #73472d 65px,
          #4b2c1c 65px,
          #4b2c1c 73px
        );

      border-bottom: 8px solid #3f2518;

      z-index: 1;
    }


    /* VIGAS DEL TECHO */

    .viga {
      position: absolute;

      top: 0;

      width: 18px;
      height: 18%;

      background: #432719;

      box-shadow:
        4px 0 0 rgba(255,255,255,0.04),
        inset -4px 0 0 rgba(0,0,0,0.2);

      z-index: 3;
    }

    .viga.v1 {
      left: 18%;
    }

    .viga.v2 {
      left: 50%;
    }

    .viga.v3 {
      right: 18%;
    }


    /* LÁMPARAS */

    .lampara {
      position: absolute;

      top: 5%;

      width: 90px;
      height: 115px;

      background:
        linear-gradient(
          to right,
          #d58c39,
          #f4c56d,
          #d58c39
        );

      border-radius: 12px 12px 25px 25px;

      box-shadow:
        0 12px 30px rgba(255, 180, 70, 0.25),
        0 15px 35px rgba(0,0,0,0.25);

      z-index: 4;
    }

    .lampara::before {
      content: "";

      position: absolute;

      top: -55px;
      left: 50%;

      width: 4px;
      height: 55px;

      transform: translateX(-50%);

      background: #352014;
    }

    .lampara::after {
      content: "";

      position: absolute;

      inset: 12px;

      border-left: 2px solid rgba(110,60,20,0.25);
      border-right: 2px solid rgba(110,60,20,0.25);

      border-radius: 10px;
    }

    .lampara1 {
      left: 5%;
    }

    .lampara2 {
      left: 43%;
      transform: scale(1.15);
    }

    .lampara3 {
      right: 7%;
    }


    /* PARED IZQUIERDA */

    .pared-izquierda {
      position: absolute;

      left: 0;
      top: 17%;

      width: 20%;
      height: 83%;

      background:
        repeating-linear-gradient(
          90deg,
          #583822 0px,
          #583822 9px,
          #855538 9px,
          #855538 27px
        );

      box-shadow:
        inset -10px 0 20px rgba(0,0,0,0.25);

      z-index: 2;
    }


    /* ESTANTES DERECHOS */

    .estantes {
      position: absolute;

      right: 0;
      top: 22%;

      width: 23%;
      height: 58%;

      background:
        linear-gradient(
          to bottom,
          #5b3823,
          #795036
        );

      border-left: 12px solid #482b1b;

      box-shadow:
        inset 8px 0 12px rgba(0,0,0,0.25);

      z-index: 2;
    }

    .estante {
      height: 25%;

      border-bottom: 10px solid #442819;

      position: relative;
    }

    .estante::before,
    .estante::after {
      content: "";

      position: absolute;

      bottom: 15px;

      width: 30px;
      height: 42px;

      background: #b48a61;

      border-radius: 4px;
    }

    .estante::before {
      left: 25px;
    }

    .estante::after {
      right: 25px;
    }


    /* BOTELLAS DECORATIVAS */

    .botella {
      position: absolute;

      width: 18px;
      height: 45px;

      bottom: 25px;

      border-radius: 4px;

      background: #b45a3a;

      box-shadow:
        0 3px 5px rgba(0,0,0,0.3);
    }

    .botella.b1 {
      left: 55px;
    }

    .botella.b2 {
      left: 90px;
      background: #6e4931;
    }

    .botella.b3 {
      right: 55px;
      background: #a17c48;
    }


    /* MESA / MOSTRADOR INFERIOR */

    .mostrador {
      position: absolute;

      left: 0;
      bottom: 0;

      width: 100%;
      height: 18%;

      background:
        linear-gradient(
          to bottom,
          #70432b,
          #4d2d1d
        );

      border-top: 12px solid #8b5a3a;

      box-shadow:
        0 -10px 25px rgba(0,0,0,0.25);

      z-index: 4;
    }


    /* OBJETOS SOBRE EL MOSTRADOR */

    .objeto {
      position: absolute;

      bottom: 9%;

      width: 45px;
      height: 50px;

      background: #7b5035;

      border-radius: 5px;

      box-shadow:
        0 5px 8px rgba(0,0,0,0.3);
    }

    .objeto1 {
      left: 8%;
    }

    .objeto2 {
      left: 13%;
      width: 35px;
      height: 65px;
    }

    .objeto3 {
      right: 12%;
      width: 50px;
      height: 38px;
    }


    /* BANQUETA */

    .banqueta {
      position: absolute;

      right: 25%;
      bottom: 3%;

      width: 115px;
      height: 65px;

      background: #6d2e28;

      border-radius: 12px 12px 5px 5px;

      box-shadow:
        0 10px 20px rgba(0,0,0,0.3);

      z-index: 3;
    }

    .banqueta::before,
    .banqueta::after {
      content: "";

      position: absolute;

      bottom: -75px;

      width: 10px;
      height: 75px;

      background: #442819;
    }

    .banqueta::before {
      left: 15px;
    }

    .banqueta::after {
      right: 15px;
    }


    /* HOJA CENTRAL */

    .hoja {
      position: absolute;

      left: 19%;
      top: 11%;

      width: 62%;
      height: 82%;

      background:
        radial-gradient(
          ellipse at 20% 15%,
          rgba(255,255,255,0.55),
          transparent 40%
        ),
        radial-gradient(
          ellipse at 80% 85%,
          rgba(190,160,120,0.12),
          transparent 45%
        ),
        #f4ecd9;

      border-radius:
        4px 7px 5px 9px;

      box-shadow:
        12px 14px 30px rgba(0,0,0,0.28),
        inset 0 0 30px rgba(120,80,40,0.06);

      transform: rotate(-0.25deg);

      z-index: 6;

      overflow: hidden;
    }


    /* TEXTURA DEL PAPEL */

    .hoja::before {
      content: "";

      position: absolute;

      inset: 0;

      opacity: 0.18;

      background-image:
        radial-gradient(
          rgba(100,70,40,0.25) 0.6px,
          transparent 0.7px
        );

      background-size: 5px 5px;

      pointer-events: none;
    }


    /* BORDE IRREGULAR */

    .hoja::after {
      content: "";

      position: absolute;

      left: -2px;
      right: -2px;
      bottom: -2px;

      height: 10px;

      background:
        repeating-linear-gradient(
          90deg,
          #e8ddc4 0px,
          #f4ecd9 25px,
          #e4d7bb 45px,
          #f4ecd9 65px
        );

      opacity: 0.8;
    }


    /* DECORACIÓN PEQUEÑA DEL PAPEL */

    .adorno {
      position: absolute;

      width: 35px;
      height: 35px;

      border: 2px solid rgba(142, 87, 44, 0.25);

      border-radius: 50%;
    }

    .adorno1 {
      top: 20px;
      right: 25px;
    }

    .adorno2 {
      bottom: 25px;
      left: 25px;
    }


    /* RESPONSIVE */

    @media (max-width: 700px) {

      .hoja {
        left: 7%;
        width: 86%;
        top: 10%;
        height: 82%;
      }

      .pared-izquierda {
        width: 8%;
      }

      .estantes {
        width: 10%;
      }

      .lampara {
        width: 55px;
        height: 80px;
      }

      .lampara2 {
        transform: scale(0.9);
      }

      .banqueta {
        display: none;
      }

    }

  </style>
</head>


<body>

  <main class="escenario">

    <!-- TECHO -->
    <div class="techo"></div>

    <!-- VIGAS -->
    <div class="viga v1"></div>
    <div class="viga v2"></div>
    <div class="viga v3"></div>


    <!-- LÁMPARAS -->
    <div class="lampara lampara1"></div>
    <div class="lampara lampara2"></div>
    <div class="lampara lampara3"></div>


    <!-- PARED IZQUIERDA -->
    <div class="pared-izquierda"></div>


    <!-- ESTANTES -->
    <div class="estantes">

      <div class="estante">
        <div class="botella b1"></div>
        <div class="botella b2"></div>
      </div>

      <div class="estante">
        <div class="botella b3"></div>
      </div>

      <div class="estante"></div>

      <div class="estante"></div>

    </div>


    <!-- MOSTRADOR -->
    <div class="mostrador"></div>

    <div class="objeto objeto1"></div>
    <div class="objeto objeto2"></div>
    <div class="objeto objeto3"></div>


    <!-- BANQUETA -->
    <div class="banqueta"></div>


    <!-- HOJA CENTRAL -->
    <section class="hoja">

      <div class="adorno adorno1"></div>
      <div class="adorno adorno2"></div>

    </section>

  </main>

</body>
</html>
