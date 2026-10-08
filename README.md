<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi | Carta y Pedidos</title>
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary: #e63946;
            --primary-dark: #c1121f;
            --dark: #111111;
            --card-bg: #1e1e1e;
            --text-light: #f8f9fa;
            --text-gray: #a0a0a0;
            --accent: #ffb703;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--dark);
            color: var(--text-light);
            padding-bottom: 90px;
        }

        /* HEADER & HERO */
        header {
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.9)), url('https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=1200&q=80') center/cover;
            text-align: center;
            padding: 50px 20px;
            border-bottom: 3px solid var(--primary);
        }

        header h1 {
            font-size: 2.8rem;
            color: #fff;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        header h1 span {
            color: var(--primary);
        }

        header p {
            font-size: 1.1rem;
            color: var(--text-gray);
        }

        /* INFO BAR */
        .info-bar {
            background-color: #181818;
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 15px;
            flex-wrap: wrap;
            border-bottom: 1px solid #333;
            font-size: 0.9rem;
        }

        .info-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--accent);
        }

        /* CATEGORIES FILTER */
        .categories {
            display: flex;
            justify-content: center;
            gap: 10px;
            padding: 20px;
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            background-color: rgba(17, 17, 17, 0.95);
            backdrop-filter: blur(5px);
            z-index: 100;
        }

        .cat-btn {
            background-color: #2a2a2a;
            color: var(--text-light);
            border: 1px solid #444;
            padding: 8px 18px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .cat-btn.active, .cat-btn:hover {
            background-color: var(--primary);
            border-color: var(--primary);
            color: #fff;
        }

        /* CONTAINER & GRID */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        /* CARD */
        .card {
            background-color: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border: 1px solid #2a2a2a;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(230, 57, 70, 0.2);
        }

        .card-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .card-body {
            padding: 18px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .card-desc {
            font-size: 0.85rem;
            color: var(--text-gray);
            margin-bottom: 15px;
            flex-grow: 1;
        }

        .card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 10px;
        }

        .card-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--accent);
        }

        .add-btn {
            background-color: var(--primary);
            color: #fff;
            border: none;
            padding: 8px 15px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.2s;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .add-btn:hover {
            background-color: var(--primary-dark);
        }

        /* FLOATING CART BAR */
        .cart-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: #181818;
            border-top: 2px solid var(--primary);
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 -5px 15px rgba(0,0,0,0.5);
            z-index: 1000;
        }

        .cart-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .cart-count-badge {
            background-color: var(--primary);
            color: #fff;
            padding: 5px 12px;
            border-radius: 20px;
            font-weight: 700;
        }

        .cart-total {
            font-size: 1.2rem;
            font-weight: 700;
        }

        .checkout-btn {
            background-color: #25d366;
            color: #fff;
            border: none;
            padding: 12px 24px;
            border-radius: 8px;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: background 0.2s;
        }

        .checkout-btn:hover {
            background-color: #1eb857;
        }

        /* MODAL CARRITO */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: rgba(0,0,0,0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 500px;
            border-radius: 12px;
            padding: 20px;
            max-height: 80vh;
            display: flex;
            flex-direction: column;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #333;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }

        .modal-body {
            overflow-y: auto;
            flex-grow: 1;
            margin-bottom: 15px;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
            border-bottom: 1px solid #2a2a2a;
        }

        .item-controls {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .qty-btn {
            background: #333;
            color: #fff;
            border: none;
            width: 25px;
            height: 25px;
            border-radius: 5px;
            cursor: pointer;
        }

        .close-btn {
            background: none;
            border: none;
            color: var(--text-gray);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .customer-inputs input, .customer-inputs select {
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            background: #111;
            border: 1px solid #333;
            color: #fff;
            border-radius: 6px;
        }
    </style>
</head>
<body>

    <!-- HERO / HEADER -->
    <header>
        <h1>KURAMA <span>SUSHI</span> 🍣</h1>
        <p>El mejor sabor directo a tu mesa. Realiza tu pedido en línea.</p>
    </header>

    <!-- BARRA DE INFORMACIÓN -->
    <div class="info-bar">
        <div class="info-item"><i class="fa-solid fa-clock"></i> <span>Atención: 17:00 - 23:00 hrs</span></div>
        <div class="info-item"><i class="fa-solid fa-motorcycle"></i> <span>Delivery y Retiro</span></div>
        <div class="info-item"><i class="fa-brands fa-whatsapp"></i> <span>+56 9 3357 0798</span></div>
    </div>

    <!-- FILTRO DE CATEGORÍAS -->
    <div class="categories">
        <button class="cat-btn active" onclick="filterCategory('todos')">Todos</button>
        <button class="cat-btn" onclick="filterCategory('rolls')">Rolls Especiales</button>
        <button class="cat-btn" onclick="filterCategory('california')">California</button>
        <button class="cat-btn" onclick="filterCategory('promos')">Promociones</button>
    </div>

    <!-- PRODUCTOS -->
    <div class="container">
        <div class="products-grid" id="products-container">
            <!-- Los productos se cargan dinámicamente -->
        </div>
    </div>

    <!-- BARRA FLOTANTE DE CARRITO -->
    <div class="cart-bar">
        <div class="cart-info">
            <span class="cart-count-badge" id="cart-count">0 items</span>
            <span class="cart-total" id="cart-total">$0</span>
        </div>
        <button class="checkout-btn" onclick="openModal()">
            <i class="fa-brands fa-whatsapp"></i> Ver Pedido
        </button>
    </div>

    <!-- MODAL DE DETALLE Y ENVÍO -->
    <div class="modal" id="cart-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Detalle de tu Pedido</h3>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            
            <div class="modal-body" id="modal-items">
                <!-- Ítems del carrito -->
            </div>

            <div class="customer-inputs">
                <input type="text" id="cust-name" placeholder="Tu Nombre completo">
                <select id="delivery-type">
                    <option value="Delivery">Delivery / Reparto a Domicilio</option>
                    <option value="Retiro">Retiro en Local</option>
                </select>
                <input type="text" id="cust-address" placeholder="Dirección (si es Delivery)">
            </div>

            <div style="margin-top: 15px; text-align: right;">
                <h4 id="modal-total">Total: $0</h4>
            </div>

            <button class="checkout-btn" style="width: 100%; margin-top: 15px; justify-content: center;" onclick="sendWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> Confirmar por WhatsApp
            </button>
        </div>
    </div>

    <script>
        // LISTA DE PRODUCTOS (Puedes editar o agregar más aquí)
        const products = [
            {
                id: 1,
                name: "Roll Acevichado",
                category: "rolls",
                price: 7500,
                desc: "Camarón furai, palta, queso crema, cubierto de pescado del día en salsa acevichada.",
                img: "https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=500&q=80"
            },
            {
                id: 2,
                name: "California Ebi",
                category: "california",
                price: 6000,
                desc: "Camarón, palta y queso crema, envuelto en sésamo o ciboulette.",
                img: "https://images.unsplash.com/photo-1611143669185-af224c5e3252?auto=format&fit=crop&w=500&q=80"
            },
            {
                id: 3,
                name: "Roll Avocado",
                category: "rolls",
                price: 6500,
                desc: "Pollo teriyaki y queso crema, envuelto en finas láminas de palta.",
                img: "https://images.unsplash.com/photo-1563245372-f21724e3856d?auto=format&fit=crop&w=500&q=80"
            },
            {
                id: 4,
                name: "Promo Kurama 30 Pieces",
                category: "promos",
                price: 18000,
                desc: "10 Roll Avocado, 10 California Ebi y 10 Hot Rolls fritos en panko.",
                img: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?auto=format&fit=crop&w=500&q=80"
            }
        ];

        let cart = [];

        // RENDERIZAR PRODUCTOS
        function renderProducts(filter = 'todos') {
            const container = document.getElementById('products-container');
            container.innerHTML = '';

            const filtered = filter === 'todos' 
                ? products 
                : products.filter(p => p.category === filter);

            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="card">
                        <img src="${p.img}" class="card-img" alt="${p.name}">
                        <div class="card-body">
                            <h3 class="card-title">${p.name}</h3>
                            <p class="card-desc">${p.desc}</p>
                            <div class="card-footer">
                                <span class="card-price">$${p.price.toLocaleString('es-CL')}</span>
                                <button class="add-btn" onclick="addToCart(${p.id})">
                                    <i class="fa-solid fa-plus"></i> Agregar
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            });
        }

        // FILTRAR CATEGORÍAS
        function filterCategory(cat) {
            document.querySelectorAll('.cat-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            renderProducts(cat);
        }

        // AGREGAR AL CARRITO
        function addToCart(id) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.qty++;
            } else {
                const prod = products.find(p => p.id === id);
                cart.push({ ...prod, qty: 1 });
            }
            updateCart();
        }

        // ACTUALIZAR CARRITO
        function updateCart() {
            const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

            document.getElementById('cart-count').innerText = `${totalQty} items`;
            document.getElementById('cart-total').innerText = `$${totalPrice.toLocaleString('es-CL')}`;
            document.getElementById('modal-total').innerText = `Total: $${totalPrice.toLocaleString('es-CL')}`;

            renderModalItems();
        }

        // CAMBIAR CANTIDAD
        function changeQty(id, delta) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.qty += delta;
                if (item.qty <= 0) {
                    cart = cart.filter(i => i.id !== id);
                }
            }
            updateCart();
        }

        // RENDERIZAR MODAL
        function renderModalItems() {
            const container = document.getElementById('modal-items');
            if (cart.length === 0) {
                container.innerHTML = '<p style="text-align:center; color: #888;">El carrito está vacío.</p>';
                return;
            }

            container.innerHTML = cart.map(i => `
                <div class="cart-item">
                    <div>
                        <strong>${i.name}</strong><br>
                        <small>$${i.price.toLocaleString('es-CL')} c/u</small>
                    </div>
                    <div class="item-controls">
                        <button class="qty-btn" onclick="changeQty(${i.id}, -1)">-</button>
                        <span>${i.qty}</span>
                        <button class="qty-btn" onclick="changeQty(${i.id}, 1)">+</button>
                    </div>
                </div>
            `).join('');
        }

        // MODAL TOGGLE
        function openModal() { document.getElementById('cart-modal').classList.add('active'); }
        function closeModal() { document.getElementById('cart-modal').classList.remove('active'); }

        // ENVIAR POR WHATSAPP
        function sendWhatsApp() {
            if (cart.length === 0) {
                alert("Agrega al menos un producto al carrito.");
                return;
            }

            const name = document.getElementById('cust-name').value.trim();
            const type = document.getElementById('delivery-type').value;
            const address = document.getElementById('cust-address').value.trim();

            if (!name) {
                alert("Por favor ingresa tu nombre.");
                return;
            }

            let msg = `🍣 *NUEVO PEDIDO - KURAMA SUSHI*\n`;
            msg += `👤 *Cliente:* ${name}\n`;
            msg += `🛵 *Tipo:* ${type}\n`;
            if (type === 'Delivery' && address) {
                msg += `📍 *Dirección:* ${address}\n`;
            }
            msg += `\n📋 *Detalle del Pedido:*\n`;

            cart.forEach(i => {
                msg += `• ${i.qty}x ${i.name} ($${(i.price * i.qty).toLocaleString('es-CL')})\n`;
            });

            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            msg += `\n💰 *Total:* $${totalPrice.toLocaleString('es-CL')}`;

            const phone = "56933570798";
            const url = `https://wa.me/${phone}?text=${encodeURIComponent(msg)}`;
            window.open(url, '_blank');
        }

        // Inicializar
        renderProducts();
    </script>
</body>
</html>
