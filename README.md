<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi - Pedidos Online</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #121212;
            color: #f1f1f1;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #1f1f1f;
            text-align: center;
            padding: 20px;
            border-bottom: 2px solid #ff4757;
        }
        h1 {
            color: #ff4757;
            margin: 0;
        }
        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 15px;
        }
        .menu-section {
            margin-bottom: 30px;
        }
        .menu-item {
            background-color: #1e1e1e;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 1px solid #333;
        }
        .item-info h3 {
            margin: 0 0 5px 0;
            color: #fff;
        }
        .item-info p {
            margin: 0;
            color: #aaa;
            font-size: 14px;
        }
        .item-price {
            font-weight: bold;
            color: #2ed573;
            font-size: 16px;
        }
        .order-box {
            background-color: #1f1f1f;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            margin-top: 30px;
        }
        .btn-whatsapp {
            background-color: #25d366;
            color: white;
            padding: 12px 20px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            display: inline-block;
            margin-top: 10px;
        }
        .btn-whatsapp:hover {
            background-color: #20ba5a;
        }
    </style>
</head>
<body>

    <header>
        <h1>Kurama Sushi 🍣</h1>
        <p>Haz tu pedido directo por WhatsApp</p>
    </header>

    <div class="container">
        <div class="menu-section">
            <h2>Nuestros Rolls</h2>
            
            <div class="menu-item">
                <div class="item-info">
                    <h3>Roll Acevichado</h3>
                    <p>Camarón furai, palta, queso crema, cubierto de pescado del día en salsa acevichada.</p>
                </div>
                <div class="item-price">$7.500</div>
            </div>

            <div class="menu-item">
                <div class="item-info">
                    <h3>California Ebi</h3>
                    <p>Camarón, palta y queso crema, envuelto en sésamo o ciboulette.</p>
                </div>
                <div class="item-price">$6.000</div>
            </div>

            <div class="menu-item">
                <div class="item-info">
                    <h3>Roll Avocado</h3>
                    <p>Pollo teriyaki y queso crema, envuelto en finas láminas de palta.</p>
                </div>
                <div class="item-price">$6.500</div>
            </div>
        </div>

        <div class="order-box">
            <h3>¿Listo para ordenar?</h3>
            <p>Escríbenos directamente a nuestro WhatsApp para coordinar tu pedido y despacho.</p>
            <a href="https://wa.me/56933570798?text=Hola,%20quiero%20hacer%20un%20pedido%20de%20sushi:" class="btn-whatsapp" target="_blank">Pedir por WhatsApp 📱</a>
        </div>
    </div>

</body>
</html>
