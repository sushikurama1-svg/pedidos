<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi | Pedidos Online</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <!-- Font Awesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        outfit: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        'neon-pink': '#ff007f',
                        'neon-purple': '#7b2cbf',
                        'neon-cyan': '#00f5d4',
                        'neon-yellow': '#ffee32',
                        'dark-bg': '#0b0914',
                        'card-bg': 'rgba(23, 19, 38, 0.85)',
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #0b0914;
            background-image: 
                radial-gradient(at 0% 0%, rgba(123, 44, 191, 0.25) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(255, 0, 127, 0.2) 0px, transparent 50%);
            background-attachment: fixed;
            font-family: 'Outfit', sans-serif;
        }
        .neon-border {
            border: 1px solid rgba(255, 0, 127, 0.3);
        }
        .card-hover {
            transition: all 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-6px);
            border-color: rgba(255, 0, 127, 0.6);
            box-shadow: 0 10px 25px rgba(255, 0, 127, 0.25);
        }
    </style>
</head>
<body class="text-gray-100 min-h-screen pb-28">

    <!-- HEADER / HERO -->
    <header class="text-center pt-8 pb-4 px-4">
        <span class="inline-block bg-gradient-to-r from-neon-pink to-neon-purple text-white text-xs font-bold px-4 py-1.5 rounded-full uppercase tracking-widest shadow-lg shadow-neon-pink/50 mb-3">
            KURAMA SUSHI
        </span>
        <h1 class="text-4xl md:text-5xl font-extrabold bg-gradient-to-r from-neon-pink via-neon-cyan to-neon-yellow bg-clip-text text-transparent">
            Haz tu Pedido Online 🍣
        </h1>
        <p class="text-gray-400 mt-2 text-sm md:text-base">
            Elige tus rolls favoritos y te los preparamos al instante
        </p>
    </header>

    <!-- INFO BAR -->
    <div class="flex flex-wrap justify-center gap-3 px-4 mb-6 text-xs md:text-sm">
        <div class="bg-white/5 border border-white/10 backdrop-blur-md px-4 py-2 rounded-full flex items-center gap-2 text-neon-cyan">
            <i class="fa-solid fa-clock"></i> <span>17:00 - 23:00 hrs</span>
        </div>
        <div class="bg-white/5 border border-white/10 backdrop-blur-md px-4 py-2 rounded-full flex items-center gap-2 text-neon-cyan">
            <i class="fa-solid fa-motorcycle"></i> <span>Delivery y Retiro</span>
        </div>
        <div class="bg-white/5 border border-white/10 backdrop-blur-md px-4 py-2 rounded-full flex items-center gap-2 text-neon-cyan">
            <i class="fa-brands fa-whatsapp"></i> <span>+56 9 3357 0798</span>
        </div>
    </div>

    <!-- CATEGORÍAS -->
    <nav class="sticky top-0 z-40 bg-dark-bg/90 backdrop-blur-xl border-b border-white/10 py-3 px-4 mb-6">
        <div class="flex justify-center gap-2 overflow-x-auto no-scrollbar">
            <button onclick="filterCategory('todos')" class="cat-btn active bg-gradient-to-r from-neon-pink to-neon-purple text-white border border-transparent px-5 py-2 rounded-full font-semibold text-sm whitespace-nowrap shadow-md">
                Todos
            </button>
            <button onclick="filterCategory('promos')" class="cat-btn bg-white/5 text-gray-400 border border-white/10 px-5 py-2 rounded-full font-semibold text-sm whitespace-nowrap hover:text-white">
                Promociones
            </button>
            <button onclick="filterCategory('rolls')" class="cat-btn bg-white/5 text-gray-400 border border-white/10 px-5 py-2 rounded-full font-semibold text-sm whitespace-nowrap hover:text-white">
                Rolls Especiales
            </button>
            <button onclick="filterCategory('california')" class="cat-btn bg-white/5 text-gray-400 border border-white/10 px-5 py-2 rounded-full font-semibold text-sm whitespace-nowrap hover:text-white">
                California
            </button>
        </div>
    </nav>

    <!-- GRILLA DE PRODUCTOS -->
    <main class="max-w-6xl mx-auto px-4">
        <div id="products-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
            <!-- Cargado por JavaScript -->
        </div>
    </main>

    <!-- BARRA FLOTANTE DEL CARRITO -->
    <div class="fixed bottom-4 left-1/2 -translate-x-1/2 w-[92%] max-w-lg bg-[#120e21]/95 border border-neon-pink/40 backdrop-blur-xl p-3 px-5 rounded-2xl flex justify-between items-center shadow-2xl shadow-neon-pink/20 z-50">
        <div class="flex items-center gap-3">
            <span id="cart-count" class="bg-neon-pink text-white font-extrabold text-sm px-3 py-1 rounded-full">0</span>
            <span id="cart-total" class="text-lg font-bold text-white">$0</span>
        </div>
        <button onclick="openModal()" class="bg-[#25d366] hover:bg-[#1eb857] text-white font-bold px-5 py-2.5 rounded-xl text-sm flex items-center gap-2 transition-all transform active:scale-95 shadow-lg shadow-[#25d366]/30">
            <i class="fa-brands fa-whatsapp text-lg"></i> Ver Pedido
        </button>
    </div>

    <!-- MODAL DE CHECKOUT -->
    <div id="cart-modal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-[100] hidden items-center justify-center p-4">
        <div class="bg-[#0b0914] border border-neon-pink/40 w-full max-w-md rounded-2xl p-6 max-h-[85vh] flex flex-col shadow-2xl">
            <div class="flex justify-between items-center border-b border-white/10 pb-3 mb-4">
                <h3 class="text-xl font-bold text-white">Tu Pedido</h3>
                <button onclick="closeModal()" class="text-gray-400 hover:text-white text-2xl">&times;</button>
            </div>

            <div id="modal-items" class="overflow-y-auto flex-grow mb-4 divide-y divide-white/5">
                <!-- Ítems del carrito -->
            </div>

            <div class="space-y-3">
                <input type="text" id="cust-name" placeholder="Tu Nombre completo" class="w-full bg-white/5 border border-white/10 rounded-xl p-3 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-neon-pink">
                <select id="delivery-type" onchange="toggleAddressInput()" class="w-full bg-[#18132b] border border-white/10 rounded-xl p-3 text-sm text-white focus:outline-none focus:border-neon-pink">
                    <option value="Delivery">Reparto a Domicilio (Delivery)</option>
                    <option value="Retiro">Retiro en Local</option>
                </select>
                <input type="text" id="cust-address" placeholder="Dirección exacta (calle, número, depto)" class="w-full bg-white/5 border border-white/10 rounded-xl p-3 text-sm text-white placeholder-gray-500 focus:outline-none focus:border-neon-pink">
            </div>

            <div class="mt-4 pt-3 border-t border-white/10 flex justify-between items-center">
                <span class="text-gray-400 text-sm">Total a pagar:</span>
                <span id="modal-total" class="text-2xl font-extrabold text-neon-cyan">$0</span>
            </div>

            <button onclick="sendWhatsApp()" class="mt-4 w-full bg-[#25d366] hover:bg-[#1eb857] text-white font-bold py-3 rounded-xl flex items-center justify-center gap-2 transition-all shadow-lg shadow-[#25d366]/30">
                <i class="fa-brands fa-whatsapp text-xl"></i> Enviar Pedido a WhatsApp
            </button>
        </div>
    </div>

    <!-- JAVASCRIPT -->
    <script>
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

            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="bg-card-bg border border-white/10 rounded-2xl overflow-hidden card-hover flex flex-col justify-between">
                        <div>
                            <div class="h-44 overflow-hidden relative">
                                <img src="${p.img}" alt="${p.name}" class="w-full h-full object-cover transition-transform duration-500 hover:scale-110">
                            </div>
                            <div class="p-4">
                                <h3 class="text-lg font-bold text-white mb-1">${p.name}</h3>
                                <p class="text-gray-400 text-xs leading-relaxed mb-4">${p.desc}</p>                             </div>                         </div>                         <div class="p-4 pt-0 flex justify-between items-center">                             <span class="text-xl font-extrabold text-neon-cyan">$${p.price.toLocaleString('es-CL')}</span>
                            <button onclick="addToCart(${p.id})" class="bg-gradient-to-r from-neon-pink to-neon-purple hover:opacity-90 text-white font-bold text-xs px-4 py-2 rounded-xl flex items-center gap-1 shadow-md shadow-neon-pink/30 transition-transform active:scale-95">
                                <i class="fa-solid fa-plus"></i> Añadir
                            </button>
                        </div>
                    </div>
                `;
            });
        }

        function filterCategory(cat) {
            document.querySelectorAll('.cat-btn').forEach(btn => {
                btn.classList.remove('bg-gradient-to-r', 'from-neon-pink', 'to-neon-purple', 'text-white');
                btn.classList.add('bg-white/5', 'text-gray-400');
            });
            event.target.classList.add('bg-gradient-to-r', 'from-neon-pink', 'to-neon-purple', 'text-white');
            event.target.classList.remove('bg-white/5', 'text-gray-400');
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
            document.getElementById('modal-total').innerText = `$${totalPrice.toLocaleString('es-CL')}`;
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
                container.innerHTML = '<p class="text-center text-gray-500 py-6 text-sm">Tu carrito está vacío.</p>';
                return;
            }

            container.innerHTML = cart.map(i => `
                <div class="flex justify-between items-center py-3">
                    <div>
                        <h4 class="font-semibold text-sm text-white">${i.name}</h4>                         <span class="text-xs text-gray-400">$${i.price.toLocaleString('es-CL')} c/u</span>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="changeQty(${i.id}, -1)" class="w-7 h-7 bg-white/10 hover:bg-white/20 text-white rounded-lg font-bold text-xs">-</button>
                        <span class="text-sm font-bold text-white px-1">${i.qty}</span>
                        <button onclick="changeQty(${i.id}, 1)" class="w-7 h-7 bg-white/10 hover:bg-white/
