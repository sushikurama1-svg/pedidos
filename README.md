<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Kurama Sushi - Pedidos</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      background: #351b13;
      font-family: Arial, sans-serif;

      /* Fondo del restaurante */
      background-image: url("fondo.jpg");
      background-size: cover;
      background-position: center;
      background-attachment: fixed;

      display: flex;
      justify-content: center;
      align-items: flex-start;

      padding: 40px 20px;
    }

    /* Hoja */
    .hoja {
      width: min(92vw, 1100px);
      min-height: 92vh;

      background: #fffdf7;

      margin-top: 20px;
      padding: 55px 70px 80px;

      box-shadow:
        0 10px 35px rgba(0, 0, 0, 0.35);

      position: relative;
    }

    /* Pequeño efecto de papel */
    .hoja::before {
      content: "";
      position: absolute;
      inset: 0;
      pointer-events: none;

      background:
        radial-gradient(
          rgba(120, 100, 80, 0.06) 1px,
          transparent 1px
        );

      background-size: 5px 5px;
      opacity: 0.4;
    }

    .contenido {
      position: relative;
      z-index: 2;
    }

    /* Logo */
    .logo {
      width: 280px;
      max-width: 70%;
      display: block;
      margin: 0 auto 25px;
    }

    /* Línea */
    .linea {
      height: 1px;
      background: #ddd;
      width: 90%;
      margin: 0 auto 35px;
    }

    /* Título */
    h1 {
      text-align: center;
      color: #7b2028;
      font-size: 42px;
      letter-spacing: 2px;
      margin-bottom: 10px;
    }

    .subtitulo {
      text-align: center;
      color: #333;
      font-size: 22px;
      margin-bottom: 45px;
    }

    /* Aquí
    tu-repositorio/
│
├── index.html
├── fondo.jpg
└── logo.png
