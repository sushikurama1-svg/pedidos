<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Kurama Sushi 🍣 | Pedidos Online</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@400;600;700;800&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <!-- Lucide Icons -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            'neon-pink': '#ff007f',
            'neon-purple': '#7b2cbf',
            'neon-cyan': '#00f5d4',
            'neon-yellow': '#ffee32',
            'dark-bg-start': '#0b0914',
            'dark-bg-end': '#18132b',
            'card-bg': 'rgba(23, 19, 38, 0.85)',
          },
          fontFamily: {
            sans: ['Outfit', 'Poppins', 'sans-serif'],
          }
        }
      }
    }
  </script>

  <style>
    body {
      background: radial-gradient(circle at top center, #18132b 0%, #0b0914 100%);
      background-attachment: fixed;
      color: #f8f9fa;
      font-family: 'Outfit', sans-serif;
    }

    .glass-card {
      background: rgba(23, 19, 38, 0.85);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 0, 127, 0.2);
    }

    .glass-card:hover {
      border-color: rgba(255, 0, 127, 0.6);
      box-shadow: 0 10px 25px rgba(255, 0, 127, 0.25);
    }

    .glass-nav {
      background: rgba(11, 9, 20, 0.85);
      backdrop-filter: blur(15px);
    }

    .text-gradient {
      background: linear-gradient(135deg, #ff007f 0%, #00f5d4 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    /* Hide scrollbar for category selector */
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  </style>
</head>
<body class="min-h-screen pb-32">

  <!-- HEADER / HERO SECTION -->
  <header class="text-center pt-8 pb-6 px-4 max-w-4xl mx-auto">
    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-neon-pink/40 bg-neon-pink/10 text-neon-pink text-xs font-bold tracking-widest uppercase mb-4 shadow-[0_0_15px_rgba(255,0,127,0.3)]">
      <i data-lucide="zap" class="w-4 h-4"></i> KURAMA SUSHI
    </div>
    
    <h1 class="text-4xl md:text-6xl font-extrabold tracking-tight mb-2">
      Haz tu Pedido <span class="text-gradient">Online</span> 🍣
    </h1>
    <p class="text-slate-400 text-sm md:text-base max-w-md mx-auto">
      Elige tus rolls favoritos y te los preparamos al instante.
    </p>

    <!-- INFO BAR -->
    <div class="flex flex-wrap justify-center gap-3 mt-6 text-xs md:text-sm">
      <div class="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-slate-900/80 border border-slate-800 text-slate-300">
        <i data-lucide="clock" class="w-4 h-4 text-neon-cyan"></i> 17:00 - 23:00 hrs
      </div>
      <div class="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-slate-900/80 border border-slate-800 text-slate-300">
        <i data-lucide="bike" class="w-4 h-4 text-neon-pink"></i> Delivery & Retiro
      </div>
      <a href="https://wa.me/56933570798" target="_blank" class="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-slate-900/80 border border-slate-800 text-slate-300 hover:border-green-500 transition-colors">
        <i data-lucide="phone" class="w-4 h-4 text-green-400"></i> +56 9 3357 0798
      </a>
    </div>
  </header>

  <!-- CATEGORIES FILTER BAR -->
  <nav class="sticky top-0 z-30 glass-nav border-b border-slate-800/80 py-3 mb-8">
    <div class="max-w-4xl mx-auto px-4 flex gap-2 overflow-x-auto no-scrollbar" id="category-filters">
      <!-- Generated dynamically -->
    </div>
  </nav>

  <!-- MAIN CATALOG -->
  <main class="max-w-5xl mx-auto px-4">
    <div id="products-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <!-- Generated dynamically -->
    </div>
  </main>

  <!-- FLOATING CART BAR -->
  <div class="fixed bottom-4 left-0 right-0 z-40 px-4 pointer-events-none">
    <div class="max-w-md mx-auto bg-slate-900/90 border border-neon-pink/50 rounded-2xl p-3 shadow-[0_10px_30px_rgba(0,0,0,0.8)] backdrop-blur-xl pointer-events-auto flex items-center justify-between">
      <div class="flex items-center gap-3">
        <div class="relative bg-neon-pink/20 p-2.5 rounded-xl border border-neon-pink/30">
          <i data-lucide="shopping-bag" class="w-6 h-6 text-neon-pink"></i>
          <span id="cart-count" class="absolute -top-2 -right-2 bg-neon-pink text-white text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center border-2 border-slate-900">0</span>
        </div>
        <div>
          <p class="text-xs text-slate-400 font-medium">Total Pedido</p>
          <p id="cart-total" class="text-lg font-bold text-neon-cyan">$0</p>
        </div>
      </div>
      
      <button onclick="openModal()" class="bg-gradient-to-r from-emerald-500 to-green-600 hover:from-emerald-400 hover:to-green-500 text-white font-bold px-5 py-2.5 rounded-xl flex items-center gap-2 transition-all active:scale-95 shadow-[0_0_15px_rgba(37,211,102,0.4)]">
        <span>Ver Pedido</span>
        <i data-lucide="arrow-right" class="w-4 h-4"></i>
      </button>
    </div>
  </div>

  <!-- CHECKOUT MODAL -->
  <div id="checkout-modal" class="fixed inset-0 z-50 bg-black/80 backdrop-blur-md hidden items-center justify-center p-4">
    <div class="bg-slate-900 border border-slate-800 w-full max-w-lg rounded-2xl overflow-hidden shadow-2xl flex flex-col max-h-[90vh]">
      
      <!-- Modal Header -->
      <div class="p-4 border-b border-slate-800 flex items-center justify-between bg-slate-950/50">
        <h3 class="text-lg font-bold flex items-center gap-2">
          <i data-lucide="shopping-cart" class="w-5 h-5 text-neon-pink"></i> Tu Pedido
        </h3>
        <button onclick="closeModal()" class="text-slate-400 hover:text-white p-1 rounded-lg hover:bg-slate-800 transition-colors">
          <i data-lucide="x" class="w-6 h-6"></i>
        </button>
      </div>

      <!-- Modal Body -->
      <div class="p-4 overflow-y-auto space-y-6 flex-1">
        <!-- Cart Items List -->
        <div>
          <h4 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-3">Detalle de Productos</h4>
          <div id="cart-items" class="space-y-3">
            <!-- Items added dynamically -->
          </div>
        </div>

        <!-- Form Details -->
        <div class="space-y-4 pt-4 border-t border-slate-800">
          <h4 class="text-xs font-bold text-slate-400 uppercase tracking-wider">Datos de Entrega</h4>
          
          <div>
            <label class="block text-xs font-medium text-slate-300 mb-1">Nombre Completo *</label>
            <input type="text" id="client-name" placeholder="Ej: Juan Pérez" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2.5 text-sm text-white focus:outline-none focus:border-neon-pink">
          </div>

          <div>
            <label class="block text-xs font-medium text-slate-300 mb-1">Tipo de Entrega</label>
            <select id="delivery-type" onchange="toggleAddressField()" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2.5 text-sm text-white focus:outline-none focus:border-neon-pink">
              <option value="Delivery">Reparto a Domicilio (Delivery)</option>
              <option value="Retiro">Retiro en Local</option>
            </select>
          </div>

          <div id="address-container">
            <label class="block text-xs font-medium text-slate-300 mb-1">Dirección Exacta *</label>
            <input type="text" id="client-address" placeholder="Calle, Número, Depto / Villa" class="w-full bg-slate-800 border border-slate-700 rounded-xl px-3 py-2.5 text-sm text-white focus:outline-none focus:border-neon-pink">
          </div>
        </div>
      </div>

      <!-- Modal Footer -->
      <div class="p-4 border-t border-slate-800 bg-slate-950/50 space-y-3">
        <div class="flex justify-between items-center text-slate-300 text-sm">
          <span>Total a pagar:</span>
          <span id="modal-total" class="text-xl font-extrabold text-neon-cyan">$0</span>
        </div>

        <button onclick="sendOrderToWhatsApp()" class="w-full bg-emerald-500 hover:bg-emerald-400 text-slate-950 font-bold py-3 px-4 rounded-xl flex items-center justify-center gap-2 shadow-[0_0_20px_rgba(37,211,102,0.3)] transition-all active:scale-[0.99]">
          <i data-lucide="message-circle" class="w-5 h-5 fill-current"></i> Enviar Pedido a WhatsApp
        </button>
      </div>

    </div>
  </div>

  <script>
    // DATA BASE
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
        name: "Promo Kurama 30 Pzs",
        category: "promos",
        price: 18000,
        desc: "10 Roll Avocado, 10 California Ebi y 10 Hot Rolls fritos en panko.",
        img: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?auto=format&fit=crop&w=500&q=80"
      }
    ];

    const categories = [
      { id: "todos", label: "Todos" },
      { id: "promos", label: "Promociones 🚀" },
      { id: "rolls", label: "Rolls Especiales 🍣" },
      { id: "california", label: "California 🥑" }
    ];

    let cart = [];
    let selectedCategory = "todos";

    // INIT
    document.addEventListener("DOMContentLoaded", () => {
      renderCategories();
      renderProducts();
      updateCartUI();
      lucide.createIcons();
    });

    // RENDER CATEGORIES
    function renderCategories() {
      const filterContainer = document.getElementById("category-filters");
      filterContainer.innerHTML = categories.map(cat => `
        <button 
          onclick="filterCategory('${cat.id}')"
          class="px-4 py-2 rounded-xl text-sm font-semibold whitespace-nowrap transition-all border ${
            selectedCategory === cat.id 
              ? 'bg-neon-pink text-white border-neon-pink shadow-[0_0_15px_rgba(255,0,127,0.4)]' 
              : 'bg-slate-900/60 text-slate-400 border-slate-800 hover:border-slate-700 hover:text-white'
          }"
        >
          ${cat.label}
        </button>
      `).join("");
    }

    // FILTER CATEGORY
    function filterCategory(catId) {
      selectedCategory = catId;
      renderCategories();
      renderProducts();
    }

    // RENDER PRODUCTS
    function renderProducts() {
      const grid = document.getElementById("products-grid");
      const filtered = selectedCategory === "todos" 
        ? products 
        : products.filter(p => p.category === selectedCategory);

      grid.innerHTML = filtered.map(product => `
        <div class="glass-card rounded-2xl overflow-hidden flex flex-col justify-between transition-all duration-300 transform hover:-translate-y-1">
          <div class="relative h-48 overflow-hidden">
            <img src="${product.img}" alt="${product.name}" class="w-full h-full object-cover transition-transform duration-500 hover:scale-105">
            <span class="absolute top-3 right-3 bg-slate-900/80 backdrop-blur-md text-neon-cyan font-bold px-3 py-1 rounded-full text-xs border border-neon-cyan/30">
              ${formatCLP(product.price)}
            </span>
          </div>

          <div class="p-4 flex-1 flex flex-col justify-between">
            <div>
              <h3 class="text-lg font-bold text-white mb-1">${product.name}</h3>
              <p class="text-slate-400 text-xs leading-relaxed mb-4">${product.desc}</p>
            </div>

            <button 
              onclick="addToCart(${product.id})"
              class="w-full bg-slate-800 hover:bg-neon-pink hover:text-white text-slate-200 font-semibold py-2.5 rounded-xl border border-slate-700 hover:border-neon-pink flex items-center justify-center gap-2 transition-all active:scale-95 text-sm"
            >
              <i data-lucide="plus" class="w-4 h-4"></i> Añadir al Pedido
            </button>
          </div>
        </div>
      `).join("");

      lucide.createIcons();
    }

    // CART ACTIONS
    function addToCart(productId) {
      const existing = cart.find(item => item.id === productId);
      if (existing) {
        existing.quantity += 1;
      } else {
        const prod = products.find(p => p.id === productId);
        cart.push({ ...prod, quantity: 1 });
      }
      updateCartUI();
    }

    function updateQuantity(productId, change) {
      const index = cart.findIndex(item => item.id === productId);
      if (index !== -1) {
        cart[index].quantity += change;
        if (cart[index].quantity <= 0) {
          cart.splice(index, 1);
        }
      }
      updateCartUI();
    }

    // UPDATE UI
    function updateCartUI() {
      const totalCount = cart.reduce((acc, item) => acc + item.quantity, 0);
      const totalPrice = cart.reduce((acc, item) => acc + (item.price * item.quantity), 0);

      document.getElementById("cart-count").innerText = totalCount;
      document.getElementById("cart-total").innerText = formatCLP(totalPrice);
      document.getElementById("modal-total").innerText = formatCLP(totalPrice);

      // Render Modal Items
      const cartItemsContainer = document.getElementById("cart-items");
      if (cart.length === 0) {
        cartItemsContainer.innerHTML = `<p class="text-slate-500 text-sm text-center py-4">Tu carrito está vacío 🍣</p>`;
      } else {
        cartItemsContainer.innerHTML = cart.map(item => `
          <div class="flex items-center justify-between bg-slate-800/50 p-3 rounded-xl border border-slate-800">
            <div class="flex-1 pr-2">
              <h5 class="text-sm font-semibold text-white">${item.name}</h5>
              <p class="text-xs text-neon-cyan">${formatCLP(item.price * item.quantity)}</p>
            </div>
            
            <div class="flex items-center gap-2 bg-slate-900 border border-slate-700 rounded-lg p-1">
              <button onclick="updateQuantity(${item.id}, -1)" class="w-6 h-6 flex items-center justify-center text-slate-400 hover:text-white rounded hover:bg-slate-800 text-xs">-</button>
              <span class="text-xs font-bold w-4 text-center">${item.quantity}</span>
              <button onclick="updateQuantity(${item.id}, 1)" class="w-6 h-6 flex items-center justify-center text-slate-400 hover:text-white rounded hover:bg-slate-800 text-xs">+</button>
            </div>
          </div>
        `).join("");
      }
    }

    // FORMAT CURRENCY
    function formatCLP(amount) {
      return new Intl.NumberFormat('es-CL', { style: 'currency', currency: 'CLP' }).format(amount);
    }

    // MODAL CONTROL
    function openModal() {
      if (cart.length === 0) {
        alert("Agrega al menos un producto antes de ver tu pedido.");
        return;
      }
      document.getElementById("checkout-modal").classList.remove("hidden");
      document.getElementById("checkout-modal").classList.add("flex");
    }

    function closeModal() {
      document.getElementById("checkout-modal").classList.add("hidden");
      document.getElementById("checkout-modal").classList.remove("flex");
    }

    function toggleAddressField() {
      const type = document.getElementById("delivery-type").value;
      const addressContainer = document.getElementById("address-container");
      if (type === "Retiro") {
        addressContainer.style.display = "none";
      } else {
        addressContainer.style.display = "block";
      }
    }

    // WHATSAPP INTEGRATION
    function sendOrderToWhatsApp() {
      if (cart.length === 0) return;

      const name = document.getElementById("client-name").value.trim();
      const type = document.getElementById("delivery-type").value;
      const address = document.getElementById("client-address").value.trim();

      if (!name) {
        alert("Por favor ingresa tu nombre completo.");
        return;
      }

      if (type === "Delivery" && !address) {
        alert("Por favor ingresa tu dirección para el delivery.");
        return;
      }

      let orderItemsText = "";
      cart.forEach(item => {
        orderItemsText += `• ${item.quantity}x ${item.name} (${formatCLP(item.price * item.quantity)})\n`;
      });

      const totalPrice = cart.reduce((acc, item) => acc + (item.price * item.quantity), 0);

      let textMessage = `🍣 *NUEVO PEDIDO - KURAMA SUSHI*\n\n`;
      textMessage += `👤 *Cliente:* ${name}\n`;
      textMessage += `🛵 *Tipo:* ${type}\n`;
      if (type === "Delivery") {
        textMessage += `📍 *Dirección:* ${address}\n`;
      }
      textMessage += `\n📋 *Detalle del Pedido:*\n${orderItemsText}\n`;
      textMessage += `💰 *Total a Pagar:* ${formatCLP(totalPrice)}`;

      const phone = "56933570798";
      const encodedUrl = `https://wa.me/${phone}?text=${encodeURIComponent(textMessage)}`;

      window.open(encodedUrl, "_blank");
    }
  </script>
</body>
</html>
