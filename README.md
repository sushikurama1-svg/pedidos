<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi | Menú & Pedidos</title>
    <!-- Google Fonts & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-dark: #0b0914;
            --card-bg: rgba(23, 19, 38, 0.85);
            --accent-pink: #ff007f;
            --accent-purple: #7b2cbf;
            --accent-cyan: #00f5d4;
            --accent-yellow: #ffee32;
            --text-main: #f8f9fa;
            --text-sub: #b0a8b9;
            --gradient-primary: linear-gradient(135deg, #ff007f 0%, #7b2cbf 100%);
            --gradient-neon: linear-gradient(90deg, #ff007f, #00f5d4);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Outfit', sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            background-image: 
                radial-gradient(at 0% 0%, rgba(123, 44, 191, 0.25) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(255, 0, 127, 0.2) 0px, transparent 50%);
            background-attachment: fixed;
            color: var(--text-main);
            padding-bottom: 110px;
        }

        /* HEADER & HERO */
        header {
            text-align: center;
            padding: 45px 20px 25px;
            position: relative;
        }

        .badge-logo {
            display: inline-block;
            background: var(--gradient-primary);
            padding: 6px 16px;
            border-radius: 30px;
            font-size: 0.85rem;
            font-weight: 700;
            letter-spacing: 2px;
            text-transform: uppercase;
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.5);
            margin-bottom: 12px;
        }

        header h1 {
            font-size: 2.8rem;
            font-weight: 800;
            background: var(--gradient-neon);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 6px;
        }

        header p {
            color: var(--text-sub);
            font-size: 1rem;
        }

        /* INFO BAR */
        .info-bar {
            display: flex;
            justify-content: center;
            gap: 12px;
            padding: 10px 15px;
            flex-wrap: wrap;
            max-width: 900px;
            margin: 0 auto 20px;
        }

        .info-chip {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(8px);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.85rem;
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--accent-cyan);
        }

        /* CATEGORIES FILTER */
        .categories {
            display: flex;
            justify-content: center;
            gap: 10px;
            padding: 15px 20px;
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            background-color: rgba(11, 9, 20, 0.9);
            backdrop-filter: blur(12px);
            z-index: 100;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .cat-btn {
            background: rgba(255, 255, 255, 0.05);
            color: var(--text-sub);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 10px 22px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.95rem;
            transition: all 0.3s ease;
        }

        .cat-btn.active, .cat-btn:hover {
            background: var(--gradient-primary);
            color: #fff;
            border-color: transparent;
            box-shadow: 0 0 15px rgba(255, 0, 127, 0.4);
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
            gap: 22px;
        }

        /* CARD STYLE */
        .card {
            background: var(--card-bg);
            border-radius: 18px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(10px);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: rgba(255, 0, 127, 0.4);
            box-shadow: 0 10px 25px rgba(255, 0, 127, 0.25);
        }

        .card-img-wrap {
            position: relative;
            width: 100%;
            height: 180px;
            overflow: hidden;
        }

        .card-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease;
        }

        .card:hover .card-img {
            transform: scale(1.08);
        }

        .card-body {
            padding: 18px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 6px;
            color: #fff;
        }

        .card-desc {
            font-size: 0.88rem;
            color: var(--text-sub);
            margin-bottom: 16px;
            flex-grow: 1;
            line-height: 1.4;
        }

        .card-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-price {
            font-size: 1.3rem;
            font-weight: 800;
            color: var(--accent-cyan);
        }

        .add-btn {
            background: var(--gradient-primary);
            color: #fff;
            border: none;
            padding: 10px 18px;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 700;
            transition: all 0.2s;
            display: flex;
            align-items: center;
            gap: 6px;
            box-shadow: 0 4px 12px rgba(255, 0, 127, 0.3);
        }

        .add-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 6px 18px rgba(255, 0, 127, 0.5);
        }

        /* CART BAR FLOTANTE */
        .cart-bar {
            position: fixed;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            width: 92%;
            max-width: 600px;
            background: rgba(18, 14, 33, 0.95);
            border: 1px solid rgba(255, 0, 127, 0.4);
            backdrop-filter: blur(15px);
            padding: 12px 20px;
            border-radius: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8), 0 0 20px rgba(255, 0, 127, 0.2);
            z-index: 1000;
        }

        .cart-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .cart-badge {
            background: var(--accent-pink);
            color: #fff;
            padding: 6px 12px;
            border-radius: 15px;
            font-weight: 800;
            font-size: 0.9rem;
        }

        .cart-total {
            font-size: 1.25rem;
            font-weight: 800;
            color: #fff;
        }

        .checkout-btn {
            background: #25d366;
            color: #fff;
            border: none;
            padding: 12px 20px;
            border-radius: 14px;
            font-weight: 700;
            font-size: 0.95rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
            transition: all 0.2s ease;
        }

        .checkout-btn:hover {
            transform: scale(1.03);
            background: #20ba5a;
        }

        /* MODAL */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: rgba(5, 3, 10, 0.85);
            backdrop-filter: blur(10px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal.active { display: flex; }

        .modal-content {
            background: var(--bg-dark);
            border: 1px solid rgba(255, 0, 127, 0.3);
            width: 100%;
            max-width: 480px;
            border-radius: 20px;
            padding: 22px;
            max-height: 85vh;
            display: flex;
            flex-direction: column;
            box-shadow: 0 15px 40px rgba(0,0,0,0.9);
        }

        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 12px;
            margin-bottom: 15px;
        }

        .modal-header h3 { font-size: 1.3rem; color: #fff; }

        .close-btn {
            background: none;
            border: none;
            color: var(--text-sub);
            font-size: 1.6rem;
            cursor: pointer;
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
            padding: 12px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        .qty-btn {
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            border: none;
            width: 28px;
            height: 28px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 700;
        }

        .inputs-group input, .inputs-group select {
            width: 100%;
            padding: 12px;
            margin-top: 10px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.15);
            color: #fff;
            border-radius: 10px;
            outline: none;
        }

        .inputs-group input:focus, .inputs-group select:focus {
            border-color: var(--accent-pink);
        }
    </style>
</head>
<body>

    <header>
        <div class="badge-logo">KURAMA SUSHI</div>
        <h1>Haz tu Pedido Online 🍣</h1>
        <p>Elige tus rolls favoritos y te los preparamos al instante</p>
    </header>

    <div class="info-bar">
        <div class="info-chip"><i class="fa-solid fa-clock"></i> 17:00 - 23:00 hrs</div>
        <div class="info-chip"><i class="fa-solid fa-motorcycle"></i> Delivery y Retiro</div>
        <div class="info-chip"><i class="fa-brands fa-whatsapp"></i> +56 9 3357 0798</div>
    </div>

    <div class="categories">
        <button class="cat-btn active" onclick="filterCategory('todos')">Todos</button>
        <button class="cat-btn" onclick="filterCategory('promos')">Promociones</button>
        <button class="cat-btn" onclick="filterCategory('rolls')">Rolls Especiales</button>
        <button class="cat-btn" onclick="filterCategory('california')">California</button>
    </div>

    <div class="container">
        <div class="products-grid" id="products-container"></div>
    </div>

    <div class="cart-bar">
        <div class="cart-info">
            <span class="cart-badge" id="cart-count">0</span>
            <span class="cart-total" id="cart-total">$0</span>
        </div>
        <button class="checkout-btn" onclick="openModal()">
            <i class="fa-brands fa-whatsapp"></i> Ver Pedido
        </button>
    </div>

    <div class="modal" id="cart-modal">
        <div class="modal-content">
            <div class="modal-header">
                <h3>Tu Pedido</h3>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            
            <div class="modal-body" id="modal-items"></div>

            <div class="inputs-group">
                <input type="text" id="cust-name" placeholder="Tu Nombre">
                <select id="delivery-type">
                    <option value="Delivery">Reparto a Domicilio (Delivery)</option>
                    <option value="Retiro">Retiro en Local</option>
                </select>
                <input type="text" id="cust-address" placeholder="Dirección exacta (si es delivery)">
            </div>

            <div style="margin-top: 15px; text-align: right;">
                <h3 id="modal-total" style="color: var(--accent-cyan);">$0</h3>
            </div>

            <button class="checkout-btn" style="width: 100%; margin-top: 15px; justify-content: center;" onclick="sendWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> Enviar Pedido a WhatsApp
            </button>
        </div>
    </div>

    <script>
        // MENU BASE (Apenas me envíes tus datos actualizamos esto)
        const products = [
            { id: 1, name: "Roll Acevichado", category: "rolls", price: 7500, desc: "Camarón furai, palta, queso crema, cubierto de pescado del día en salsa acevichada.", img: "https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=500&q=80" },
            { id: 2, name: "California Ebi", category: "california", price: 6000, desc: "Camarón, palta y queso crema, envuelto en sésamo o ciboulette.", img: "https://images.unsplash.com/photo-1611143669185-af224c5e3252?auto=format&fit=crop&w=500&q=80" },
            { id: 3, name: "Roll Avocado", category: "rolls", price: 6500, desc: "Pollo teriyaki y queso crema, envuelto en finas láminas de palta.", img: "https://images.unsplash.com/photo-1563245372-f21724e3856d?auto=format&fit=crop&w=500&q=80" },
            { id: 4, name: "Promo Kurama 30 Pzs", category: "promos", price: 18000, desc: "10 Roll Avocado, 10 California Ebi y 10 Hot Rolls fritos en panko.", img: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?auto=format&fit=crop&w=500&q=80" }
        ];

        let cart = [];

        function renderProducts(filter = 'todos') {
            const container = document.getElementById('products-container');
            container.innerHTML = '';
            const filtered = filter === 'todos' ? products : products.filter(p => p.category === filter);

            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="card">
                        <div class="card-img-wrap">
                            <img src="${p.img}" class="card-img" alt="${p.name}">
                        </div>
                        <div class="card-body">
                            <h3 class="card-title">${p.name}</h3>
                            <p class="card-desc">${p.desc}</p>
                            <div class="card-footer">
                                <span class="card-price">$${p.price.toLocaleString('es-CL')}</span>
                                <button class="add-btn" onclick="addToCart(${p.id})">
                                    <i class="fa-solid fa-plus"></i> Añadir
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
            if (item) item.qty++;
            else {
                const prod = products.find(p => p.id === id);
                cart.push({ ...prod, qty: 1 });
            }
            updateCart();
        }

        function updateCart() {
            const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            document.getElementById('cart-count').innerText = totalQty;
            document.getElementById('cart-total').innerText = `$${totalPrice.toLocaleString('es-CL')}`;
            document.getElementById('modal-total').innerText = `Total: $${totalPrice.toLocaleString('es-CL')}`;
            renderModalItems();
        }

        function changeQty(id, delta) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.qty += delta;
                if (item.qty <= 0) cart = cart.filter(i => i.id !== id);
            }
            updateCart();
        }

        function renderModalItems() {
            const container = document.getElementById('modal-items');
            if (cart.length === 0) {
                container.innerHTML = '<p style="text-align:center; color: #aaa;">Tu carrito está vacío.</p>';
                return;
            }
            container.innerHTML = cart.map(i => `
                <div class="cart-item">
                    <div>
                        <strong>${i.name}</strong><br>
                        <small style="color:var(--text-sub)">$${i.price.toLocaleString('es-CL')} c/u</small>
                    </div>
                    <div style="display:flex; align-items:center; gap:8px;">
                        <button class="qty-btn" onclick="changeQty(${i.id}, -1)">-</button>
                        <span>${i.qty}</span>
                        <button class="qty-btn" onclick="changeQty(${i.id}, 1)">+</button>
                    </div>
                </div>
            `).join('');
        }

        function openModal() { document.getElementById('cart-modal').classList.add('active'); }
        function closeModal() { document.getElementById('cart-modal').classList.remove('active'); }

        function sendWhatsApp() {
            if (cart.length === 0) return alert("Agrega un producto primero.");
            const name = document.getElementById('cust-name').value.trim();
            const type = document.getElementById('delivery-type').value;
            const address = document.getElementById('cust-address').value.trim();

            if (!name) return alert("Por favor ingresa tu nombre.");

            let msg = `🍣 *NUEVO PEDIDO - KURAMA SUSHI*\n`;
            msg += `👤 *Cliente:* ${name}\n`;
            msg += `🛵 *Tipo:* ${type}\n`;
            if (type === 'Delivery' && address) msg += `📍 *Dirección:* ${address}\n`;
            msg += `\n📋 *Detalle:*\n`;

            cart.forEach(i => {
                msg += `• ${i.qty}x ${i.name} ($${(i.price * i.qty).toLocaleString('es-CL')})\n`;
            });

            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);
            msg += `\n💰 *Total:* $${totalPrice.toLocaleString('es-CL')}`;

            window.open(`https://wa.me/56933570798?text=${encodeURIComponent(msg)}`, '_blank');
        }

        renderProducts();
    </script>
</body>
</html>
