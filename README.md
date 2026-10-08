<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi | Carta & Pedidos</title>
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-main: #0c0a14;
            --bg-card: #151124;
            --bg-card-hover: #1f1a33;
            --neon-pink: #ff2a6d;
            --neon-pink-hover: #e01f5c;
            --neon-amber: #ffb703;
            --neon-cyan: #05d9e8;
            --text-white: #f8f9fa;
            --text-muted: #a09cb0;
            --border-color: #2a2440;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Plus Jakarta Sans', sans-serif;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-white);
            padding-bottom: 100px;
        }

        /* HEADER & HERO */
        header {
            background: linear-gradient(180deg, rgba(12,10,20,0.6) 0%, rgba(12,10,20,0.98) 100%), 
                        url('https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=1200&q=80') center/cover;
            text-align: center;
            padding: 45px 20px 30px;
            border-bottom: 2px solid var(--border-color);
        }

        .brand-badge {
            display: inline-block;
            background: rgba(255, 42, 109, 0.15);
            color: var(--neon-pink);
            border: 1px solid var(--neon-pink);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 700;
            margin-bottom: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        header h1 {
            font-size: 2.5rem;
            font-weight: 800;
            letter-spacing: -1px;
            margin-bottom: 8px;
        }

        header h1 span {
            color: var(--neon-pink);
            text-shadow: 0 0 15px rgba(255, 42, 109, 0.5);
        }

        header p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* INFO BAR */
        .info-bar {
            background-color: #110d1e;
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 12px 15px;
            flex-wrap: wrap;
            border-bottom: 1px solid var(--border-color);
            font-size: 0.85rem;
        }

        .info-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--neon-amber);
            font-weight: 600;
        }

        /* CATEGORIES FILTER */
        .categories {
            display: flex;
            justify-content: flex-start;
            gap: 8px;
            padding: 15px 20px;
            overflow-x: auto;
            position: sticky;
            top: 0;
            background-color: rgba(12, 10, 20, 0.92);
            backdrop-filter: blur(10px);
            z-index: 100;
            border-bottom: 1px solid var(--border-color);
        }

        .categories::-webkit-scrollbar {
            display: none;
        }

        .cat-btn {
            background-color: var(--bg-card);
            color: var(--text-muted);
            border: 1px solid var(--border-color);
            padding: 8px 18px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.85rem;
            white-space: nowrap;
            transition: all 0.25s ease;
        }

        .cat-btn.active, .cat-btn:hover {
            background: var(--neon-pink);
            border-color: var(--neon-pink);
            color: #fff;
            box-shadow: 0 0 12px rgba(255, 42, 109, 0.4);
        }

        /* CONTAINER & GRID */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px 15px;
        }

        .section-title {
            font-size: 1.2rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--text-white);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 18px;
        }

        /* CARD DESIGN */
        .card {
            background-color: var(--bg-card);
            border-radius: 16px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border: 1px solid var(--border-color);
            transition: transform 0.2s ease, border-color 0.2s ease;
        }

        .card:hover {
            transform: translateY(-4px);
            border-color: var(--neon-pink);
        }

        .card-body {
            padding: 16px;
            display: flex;
            flex-direction: column;
            height: 100%;
        }

        .card-header-row {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 8px;
        }

        .card-title {
            font-size: 1.05rem;
            font-weight: 700;
            color: #fff;
        }

        .card-desc {
            font-size: 0.82rem;
            color: var(--text-muted);
            line-height: 1.4;
            margin-bottom: 15px;
            flex-grow: 1;
        }

        .card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: auto;
            padding-top: 10px;
            border-top: 1px dashed var(--border-color);
        }

        .card-price {
            font-size: 1.15rem;
            font-weight: 800;
            color: var(--neon-amber);
        }

        .add-btn {
            background: var(--neon-pink);
            color: #fff;
            border: none;
            padding: 8px 14px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 700;
            font-size: 0.85rem;
            transition: all 0.2s;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .add-btn:hover {
            background: var(--neon-pink-hover);
            box-shadow: 0 0 10px rgba(255, 42, 109, 0.4);
        }

        /* FLOATING CART BAR */
        .cart-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: rgba(18, 14, 30, 0.95);
            backdrop-filter: blur(12px);
            border-top: 1px solid var(--border-color);
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 -5px 25px rgba(0,0,0,0.6);
            z-index: 1000;
        }

        .cart-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .cart-count-badge {
            background: var(--neon-pink);
            color: #fff;
            padding: 4px 10px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 0.85rem;
        }

        .cart-total {
            font-size: 1.15rem;
            font-weight: 800;
            color: var(--text-white);
        }

        .checkout-btn {
            background: #25d366;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 12px;
            font-weight: 700;
            font-size: 0.9rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: background 0.2s;
        }

        .checkout-btn:hover {
            background: #1eb857;
        }

        /* MODAL CARRITO */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-color: rgba(0,0,0,0.85);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 15px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            width: 100%;
            max-width: 480px;
            border-radius: 20px;
            padding: 20px;
            max-height: 85vh;
            display: flex;
            flex-direction: column;
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 12px;
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
            border-bottom: 1px solid var(--border-color);
        }

        .item-controls {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .qty-btn {
            background: #231c38;
            color: #fff;
            border: 1px solid var(--border-color);
            width: 28px;
            height: 28px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .close-btn {
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 1.5rem;
            cursor: pointer;
        }

        .customer-inputs input, .customer-inputs select {
            width: 100%;
            padding: 10px 12px;
            margin-top: 8px;
            background: #0f0c1a;
            border: 1px solid var(--border-color);
            color: #fff;
            border-radius: 10px;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <!-- HEADER -->
    <header>
        <span class="brand-badge"><i class="fa-solid fa-fire"></i> Menú Oficial</span>
        <h1>KURAMA <span>SUSHI</span> 🍣</h1>
        <p>Pide directo por WhatsApp y recibe en tu puerta</p>
    </header>

    <!-- INFO BAR -->
    <div class="info-bar">
        <div class="info-item"><i class="fa-solid fa-clock"></i> <span>Atención hoy</span></div>
        <div class="info-item"><i class="fa-solid fa-motorcycle"></i> <span>Delivery / Retiro</span></div>
        <div class="info-item"><i class="fa-brands fa-whatsapp"></i> <span>+56 9 3357 0798</span></div>
    </div>

    <!-- CATEGORÍAS -->
    <div class="categories">
        <button class="cat-btn active" onclick="filterCategory('todos')">🔥 Todos</button>
        <button class="cat-btn" onclick="filterCategory('entradas')">🥟 Entradas</button>
        <button class="cat-btn" onclick="filterCategory('promos')">⚡ Super Promos</button>
        <button class="cat-btn" onclick="filterCategory('handrolls')">🌯 Handrolls 2X</button>
    </div>

    <!-- PRODUCTOS -->
    <div class="container">
        <div class="products-grid" id="products-container">
            <!-- Carga de productos dinámicos -->
        </div>
    </div>

    <!-- BARRA FLOTANTE -->
    <div class="cart-bar">
        <div class="cart-info">
            <span class="cart-count-badge" id="cart-count">0 items</span>
            <span class="cart-total" id="cart-total">$0</span>
        </div>
        <button class="checkout-btn" onclick="openModal()">
            <i class="fa-brands fa-whatsapp"></i> Ver Pedido
        </button>
    </div>

    <!-- MODAL PEDIDO -->
    <div class="modal" id="cart-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3><i class="fa-solid fa-bag-shopping"></i> Tu Pedido</h3>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            
            <div class="modal-body" id="modal-items"></div>

            <div class="customer-inputs">
                <input type="text" id="cust-name" placeholder="Tu Nombre completo">
                <select id="delivery-type">
                    <option value="Delivery">Delivery / Reparto</option>
                    <option value="Retiro">Retiro en Local</option>
                </select>
                <input type="text" id="cust-address" placeholder="Dirección exactas (para Delivery)">
            </div>

            <div style="margin-top: 15px; text-align: right;">
                <h4 id="modal-total" style="color: var(--neon-amber); font-size: 1.2rem;">Total: $0</h4>
            </div>

            <button class="checkout-btn" style="width: 100%; margin-top: 15px; justify-content: center;" onclick="sendWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> Enviar Pedido a WhatsApp
            </button>
        </div>
    </div>

    <script>
        // MENÚ EXTRAÍDO Y ADAPTADO
        const products = [
            // Entradas
            { id: 1, name: "Sashimi (9 cortes)", category: "entradas", price: 6000, desc: "Cortes frescos de Salmón o Atún." },
            { id: 2, name: "Niguiri (3 unidades)", category: "entradas", price: 3500, desc: "Base de arroz cubierta con Salmón o Camarón." },
            { id: 3, name: "Temaki", category: "entradas", price: 6500, desc: "Cono de alga con Pollo, Salmón, Camarón, Choclo, Palmito o Champiñón." },
            { id: 4, name: "Gyosas (5 uds)", category: "entradas", price: 3500, desc: "Empanaditas japonesas de Camarón, Cerdo o Pollo." },
            { id: 5, name: "Ceviche Kurama", category: "entradas", price: 7000, desc: "Ceviche fresco de reineta con el toque especial de la casa." },
            { id: 6, name: "Tender de Pollo (5 uds)", category: "entradas", price: 4500, desc: "Crujientes tiritas de pollo empanizadas." },

            // Promos
            { id: 7, name: "Super Promo 5 Hand Rolls + Bebida", category: "promos", price: 9900, desc: "5 Handrolls a elección (Pollo, Palmito, Kanikama, Choclo o Champiñón) + Bebida." },
            
            // Handrolls
            { id: 8, name: "Promo Handrolls 2X", category: "handrolls", price: 6500, desc: "Combina 2 Handrolls a elección: Pollo, Palmito, Kanikama, Choclo o Champiñón." }
        ];

        let cart = [];

        function renderProducts(filter = 'todos') {
            const container = document.getElementById('products-container');
            container.innerHTML = '';

            const filtered = filter === 'todos' 
                ? products 
                : products.filter(p => p.category === filter);

            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="card">
                        <div class="card-body">
                            <div class="card-header-row">
                                <h3 class="card-title">${p.name}</h3>
                            </div>
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

        function filterCategory(cat) {
            document.querySelectorAll('.cat-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            renderProducts(cat);
        }

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

        function updateCart() {
            const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

            document.getElementById('cart-count').innerText = `${totalQty} items`;
            document.getElementById('cart-total').innerText = `$${totalPrice.toLocaleString('es-CL')}`;
            document.getElementById('modal-total').innerText = `Total: $${totalPrice.toLocaleString('es-CL')}`;

            renderModalItems();
        }

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

        function renderModalItems() {
            const container = document.getElementById('modal-items');
            if (cart.length === 0) {
                container.innerHTML = '<p style="text-align:center; color: var(--text-muted); padding: 20px 0;">El carrito está vacío.</p>';
                return;
            }

            container.innerHTML = cart.map(i => `
                <div class="cart-item">
                    <div>
                        <strong style="color:#fff;">${i.name}</strong><br>
                        <small style="color: var(--text-muted);">$${i.price.toLocaleString('es-CL')} c/u</small>
                    </div>
                    <div class="item-controls">
                        <button class="qty-btn" onclick="changeQty(${i.id}, -1)">-</button>
                        <span style="font-weight: bold; color: #fff;">${i.qty}</span>
                        <button class="qty-btn" onclick="changeQty(${i.id}, 1)">+</button>
                    </div>
                </div>
            `).join('');
        }

        function openModal() { document.getElementById('cart-modal').classList.add('active'); }
        function closeModal() { document.getElementById('cart
