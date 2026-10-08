<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi | Catálogo y Pedidos</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-body: #0a0912;
            --bg-card: #151224;
            --bg-header: #100d1d;
            --primary-fuchsia: #ff007f;
            --primary-purple: #7b2cbf;
            --accent-cyan: #00f5d4;
            --text-main: #f8f9fa;
            --text-sub: #a099b2;
            --border-color: rgba(255, 255, 255, 0.08);
            --gradient-accent: linear-gradient(135deg, #ff007f, #7b2cbf);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Outfit', sans-serif;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-main);
            padding-bottom: 90px;
        }

        /* HEADER NAV */
        header.nav-header {
            background-color: var(--bg-header);
            border-bottom: 1px solid var(--border-color);
            padding: 15px 20px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-logo {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
            color: #fff;
        }

        .brand-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--gradient-accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
            box-shadow: 0 0 12px rgba(255, 0, 127, 0.4);
        }

        .brand-text h1 {
            font-size: 1.2rem;
            font-weight: 800;
            letter-spacing: 0.5px;
        }

        .brand-text p {
            font-size: 0.75rem;
            color: var(--text-sub);
        }

        /* HERO BANNER - ESTILO CERRO ALTO */
        .hero-section {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }

        .hero-banner {
            background: linear-gradient(rgba(10, 9, 18, 0.75), rgba(10, 9, 18, 0.95)), url('https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=1200&q=80') center/cover;
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 40px 25px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .status-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(37, 211, 102, 0.15);
            color: #25d366;
            border: 1px solid rgba(37, 211, 102, 0.3);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .status-badge i { font-size: 0.6rem; }

        .hero-banner h2 {
            font-size: 2.2rem;
            font-weight: 800;
            margin-bottom: 10px;
            background: linear-gradient(90deg, #fff, var(--accent-cyan));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-banner p {
            color: var(--text-sub);
            font-size: 1rem;
            max-width: 600px;
            margin: 0 auto 20px;
        }

        .feature-tags {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-bottom: 25px;
        }

        .tag-item {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid var(--border-color);
            padding: 8px 16px;
            border-radius: 12px;
            font-size: 0.85rem;
            color: var(--text-main);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn-cta {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: var(--gradient-accent);
            color: #fff;
            padding: 12px 28px;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 700;
            box-shadow: 0 4px 15px rgba(255, 0, 127, 0.4);
            transition: transform 0.2s;
        }

        .btn-cta:hover { transform: scale(1.03); }

        /* NOTICE BAR */
        .notice-bar {
            background: rgba(255, 0, 127, 0.1);
            border-y: 1px solid rgba(255, 0, 127, 0.2);
            text-align: center;
            padding: 10px 15px;
            font-size: 0.9rem;
            color: #fff;
            margin-bottom: 25px;
        }

        /* MAIN CONTENT & CATEGORIES */
        .main-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .section-title { font-size: 1.5rem; font-weight: 700; }
        .product-count { color: var(--text-sub); font-size: 0.9rem; }

        .categories-filter {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 15px;
            margin-bottom: 25px;
        }

        .cat-btn {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            color: var(--text-sub);
            padding: 8px 20px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 600;
            white-space: nowrap;
            transition: all 0.2s;
        }

        .cat-btn.active, .cat-btn:hover {
            background: var(--gradient-accent);
            color: #fff;
            border-color: transparent;
            box-shadow: 0 4px 12px rgba(255, 0, 127, 0.3);
        }

        /* PRODUCTS GRID */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 0, 127, 0.4);
            box-shadow: 0 8px 20px rgba(255, 0, 127, 0.2);
        }

        .card-img-wrap {
            height: 170px;
            width: 100%;
            overflow: hidden;
        }

        .card-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .card:hover .card-img { transform: scale(1.05); }

        .card-content {
            padding: 16px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-title { font-size: 1.1rem; font-weight: 700; margin-bottom: 6px; }
        .card-desc { font-size: 0.85rem; color: var(--text-sub); margin-bottom: 15px; flex-grow: 1; line-height: 1.4; }

        .card-bottom {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-price { font-size: 1.2rem; font-weight: 800; color: var(--accent-cyan); }

        .add-btn {
            background: var(--gradient-accent);
            color: #fff;
            border: none;
            padding: 8px 16px;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 6px;
            transition: opacity 0.2s;
        }

        .add-btn:hover { opacity: 0.9; }

        /* UBICACIÓN Y CONTACTO SECTION */
        .location-section {
            background: var(--bg-header);
            border-top: 1px solid var(--border-color);
            padding: 40px 20px;
            margin-top: 40px;
        }

        .location-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            align-items: center;
        }

        .location-info h3 { font-size: 1.6rem; margin-bottom: 10px; font-weight: 800; }
        .location-info p { color: var(--text-sub); margin-bottom: 20px; }

        .info-list { list-style: none; }
        .info-list li {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 12px;
            color: var(--text-main);
            font-size: 0.95rem;
        }

        .info-list i { color: var(--primary-fuchsia); font-size: 1.1rem; }

        /* FLOATING CART BAR */
        .cart-bar {
            position: fixed;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            width: 90%;
            max-width: 550px;
            background: rgba(16, 13, 29, 0.95);
            border: 1px solid rgba(255, 0, 127, 0.4);
            backdrop-filter: blur(15px);
            padding: 12px 20px;
            border-radius: 18px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.8);
            z-index: 1000;
        }

        .cart-badge {
            background: var(--primary-fuchsia);
            color: #fff;
            padding: 4px 10px;
            border-radius: 12px;
            font-weight: 800;
            font-size: 0.85rem;
        }

        .cart-total { font-size: 1.2rem; font-weight: 800; color: #fff; margin-left: 8px; }

        .checkout-btn {
            background: #25d366;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: background 0.2s;
        }

        .checkout-btn:hover { background: #20ba5a; }

        /* MODAL */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal.active { display: flex; }

        .modal-card {
            background: var(--bg-body);
            border: 1px solid rgba(255, 0, 127, 0.3);
            width: 100%;
            max-width: 450px;
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
            padding-bottom: 10px;
            margin-bottom: 15px;
        }

        .close-btn { background: none; border: none; color: var(--text-sub); font-size: 1.5rem; cursor: pointer; }

        .modal-body { overflow-y: auto; flex-grow: 1; margin-bottom: 15px; }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .qty-btn {
            background: rgba(255, 255, 255, 0.1);
            color: #fff;
            border: none;
            width: 26px; height: 26px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 700;
        }

        .inputs-group input, .inputs-group select {
            width: 100%;
            padding: 10px;
            margin-top: 8px;
            background: rgba(255,255,255,0.05);
            border: 1px solid var(--border-color);
            color: #fff;
            border-radius: 8px;
            outline: none;
        }

        /* FOOTER */
        footer {
            background: #06050b;
            border-top: 1px solid var(--border-color);
            padding: 30px 20px;
            text-align: center;
            color: var(--text-sub);
            font-size: 0.85rem;
        }
    </style>
</head>
<body>

    <!-- NAVBAR HEADER -->
    <header class="nav-header">
        <div class="nav-container">
            <a href="#" class="brand-logo">
                <div class="brand-avatar">🍣</div>
                <div class="brand-text">
                    <h1>Kurama Sushi</h1>
                    <p>Pedidos & Delivery</p>
                </div>
            </a>
        </div>
    </header>

    <!-- HERO BANNER -->
    <section class="hero-section">
        <div class="hero-banner">
            <div class="status-badge">
                <i class="fa-solid fa-circle"></i> Abierto ahora - Haz tu Pedido
            </div>
            <h2>El mejor Sushi listo para llevar o delivery</h2>
            <p>Arma tu carrito con tus rolls favoritos y cotiza o pide al instante vía WhatsApp.</p>
            
            <div class="feature-tags">
                <div class="tag-item"><i class="fa-solid fa-motorcycle" style="color:var(--accent-cyan);"></i> Delivery rápido</div>
                <div class="tag-item"><i class="fa-solid fa-store" style="color:var(--primary-fuchsia);"></i> Retiro en local</div>
            </div>

            <a href="#productos" class="btn-cta">
                <i class="fa-solid fa-utensils"></i> Ver Productos y Pedir
            </a>
        </div>
    </section>

    <!-- NOTICE BAR -->
    <div class="notice-bar">
        <i class="fa-solid fa-clock"></i> Horario de Atención: Lunes a Domingo de 17:00 a 23:00 hrs
    </div>

    <!-- PRODUCTOS MAIN -->
    <main class="main-container" id="productos">
        <div class="section-header">
            <h3 class="section-title">Nuestra Carta</h3>
            <span class="product-count" id="total-count">4 productos</span>
        </div>

        <div class="categories-filter">
            <button class="cat-btn active" onclick="filterCategory('todos')">Todos</button>
            <button class="cat-btn" onclick="filterCategory('promos')">Promociones</button>
            <button class="cat-btn" onclick="filterCategory('rolls')">Rolls Especiales</button>
            <button class="cat-btn" onclick="filterCategory('california')">California</button>
        </div>

        <div class="products-grid" id="products-container">
            <!-- Productos cargados por JS -->
        </div>
    </main>

    <!-- SECCIÓN UBICACIÓN Y CONTACTO -->
    <section class="location-section">
        <div class="location-container">
            <div class="location-info">
                <h3>¿Dónde Encontrarnos?</h3>
                <p>Coordina tu retiro directo o consulta por nuestra zona de reparto.</p>
                <ul class="info-list">
                    <li><i class="fa-solid fa-location-dot"></i> Punto de Retiro disponible</li>
                    <li><i class="fa-brands fa-whatsapp"></i> +56 9 3357 0798</li>
                    <li><i class="fa-solid fa-clock"></i> Lunes a Domingo: 17:00 - 23:00 hrs</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- BARRA FLOTANTE DE CARRITO -->
    <div class="cart-bar">
        <div>
            <span class="cart-badge" id="cart-count">0</span>
            <span class="cart-total" id="cart-total">$0</span>
        </div>
        <button class="checkout-btn" onclick="openModal()">
            <i class="fa-brands fa-whatsapp"></i> Ver Pedido
        </button>
    </div>

    <!-- MODAL DETALLE DE PEDIDO -->
    <div class="modal" id="cart-modal">
        <div class="modal-card">
            <div class="modal-header">
                <h3>Tu Pedido</h3>
                <button class="close-btn" onclick="closeModal()">&times;</button>
            </div>
            
            <div class="modal-body" id="modal-items"></div>

            <div class="inputs-group">
                <input type="text" id="cust-name" placeholder="Tu Nombre completo">
                <select id="delivery-type" onchange="toggleAddressInput()">
                    <option value="Delivery">Reparto a Domicilio (Delivery)</option>
                    <option value="Retiro">Retiro en Local</option>
                </select>
                <input type="text" id="cust-address" placeholder="Dirección (si es Delivery)">
            </div>

            <div style="margin-top: 15px; text-align: right;">
                <h3 id="modal-total" style="color: var(--accent-cyan);">$0</h3>
            </div>

            <button class="checkout-btn" style="width: 100%; margin-top: 15px; justify-content: center;" onclick="sendWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> Confirmar por WhatsApp
            </button>
        </div>
    </div>

    <!-- FOOTER -->
    <footer>
        <p>&copy; 2026 Kurama Sushi. Todos los derechos reservados.</p>
    </footer>

    <script>
        // BASE DE DATOS DE PRODUCTOS
        const products = [
            { id: 1, name: "Roll Acevichado", category: "rolls", price: 7500, desc: "Camarón furai, palta, queso crema, cubierto de pescado del día en salsa acevichada.", img: "https://images.unsplash.com/photo-1579871494447-9811cf80d66c?auto=format&fit=crop&w=500&q=80" },
            { id: 2, name: "California Ebi", category: "california", price: 6000, desc: "Camarón, palta y queso crema, envuelto en sésamo o ciboulette.", img: "https://images.unsplash.com/photo-1611143669185-af224c5e3252?auto=format&fit=crop&w=500&q=80" },
            { id: 3, name: "Roll Avocado", category: "rolls", price: 6500, desc: "Pollo teriyaki y queso crema, envuelto en finas láminas de palta.", img: "https://images.unsplash.com/photo-1563245372-f21724e3856d?auto=format&fit=crop&w=500&q=80" },
            { id: 4, name: "Promo Kurama 30 Pzs", category: "promos", price: 18000, desc: "10 Roll Avocado, 10 California Ebi y 10 Hot Rolls fritos en panko.", img: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?auto=format&fit=crop&w=500&q=80" }
        ];

        let cart = [];

        function renderProducts(catFilter = 'todos') {
            const container = document.getElementById('products-container');
            container.innerHTML = '';
            const filtered = catFilter === 'todos' ? products : products.filter(p => p.category === catFilter);

            document.getElementById('total-count').innerText = `${filtered.length} productos`;

            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="card">
                        <div class="card-img-wrap">
                            <img src="${p.img}" class="card-img" alt="${p.name}">
                        </div>
                        <div class="card-content">
                            <h4 class="card-title">${p.name}</h4>
                            <p class="card-desc">${p.desc}</p>
                            <div class="card-bottom">
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
                container.innerHTML = '<p style="text-align:center; color: #888; padding: 20px 0;">El carrito está vacío.</p>';
                return;
            }
            container.innerHTML = cart.map(i => `
                <div class="cart-item">
                    <div>
                        <strong>${i.name}</strong><br>
                        <small style="color:var(--text-sub);">$${i.price.toLocaleString('es-CL')} c/u</small>
                    </div>
                    <div style="display:flex; align-items:center; gap:8px;">
                        <button class="qty-btn" onclick="changeQty(${i.id}, -1)">-</button>
                        <span>${i.qty}</span>
                        <button class="qty-btn" onclick="changeQty(${i.id}, 1)">+</button>
                    </div>
                </div>
            `).join('');
        }

        function toggleAddressInput() {
            const type = document.getElementById('delivery-type').value;
            const input = document.getElementById('cust-address');
            input.style.display = (type === 'Retiro') ? 'none' : 'block';
        }

        function openModal() { document.getElementById('cart-modal').classList.add('active'); }
        function closeModal() { document.getElementById('cart-modal').classList.remove('active'); }

        function sendWhatsApp() {
            if (cart.length === 0) return alert("Agrega al menos un producto.");
            const name = document.getElementById('cust-name').value.trim();
            const type = document.getElementById('delivery-type').value;
            const address = document.getElementById('cust-address').value.trim();

            if (!name) return alert("Por favor ingresa tu nombre.");
            if (type === 'Delivery' && !address) return alert("Por favor ingresa la dirección para despacho.");

            let msg = `🍣 *NUEVO PEDIDO - KURAMA SUSHI*\n`;
            msg += `👤 *Cliente:* ${name}\n`;
            msg += `🛵 *Tipo:* ${type}\n`;
            if (type === 'Delivery') msg += `📍 *Dirección:* ${address}\n`;
            msg += `\n📋 *Detalle del Pedido:*\n`;

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
