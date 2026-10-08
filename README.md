<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kurama Sushi & Nikkei Bar | Delivery & Takeaway</title>

    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            red: '#E53E3E',
                            orange: '#FF6B35',
                            dark: '#111318',
                            surface: '#1A1D24',
                            card: '#222630',
                            accent: '#F7C948'
                        }
                    },
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <!-- Google Fonts & Font Awesome Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: #0E1015;
            color: #F3F4F6;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #111318;
        }
        ::-webkit-scrollbar-thumb {
            background: #2D3748;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #FF6B35;
        }

        /* Smooth Glassmorphism */
        .glass-panel {
            background: rgba(26, 29, 36, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glass-nav {
            background: rgba(14, 16, 21, 0.9);
            backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
        }

        /* Glow Effects */
        .glow-orange {
            box-shadow: 0 0 25px -5px rgba(255, 107, 53, 0.4);
        }
        
        .glow-red {
            box-shadow: 0 0 20px -5px rgba(229, 62, 62, 0.4);
        }

        /* Cart Slide Drawer */
        .cart-drawer {
            transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* Custom pulse animation */
        @keyframes subtlePulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.03); }
        }
        .pulse-subtle {
            animation: subtlePulse 3s infinite ease-in-out;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between antialiased selection:bg-brand-orange selection:text-white">

    <!-- Navigation Header -->
    <header class="sticky top-0 z-40 glass-nav transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            
            <!-- Brand Logo -->
            <a href="#" class="flex items-center gap-3 group">
                <div class="w-11 h-11 rounded-xl bg-gradient-to-tr from-brand-red to-brand-orange flex items-center justify-center text-white text-xl font-bold shadow-lg shadow-brand-orange/20 group-hover:scale-105 transition-transform">
                    <i class="fa-solid font-bold">九</i>
                </div>
                <div>
                    <span class="text-xl font-extrabold tracking-tight text-white flex items-center gap-1.5">
                        KURAMA <span class="text-brand-orange">SUSHI</span>
                    </span>
                    <span class="block text-[10px] tracking-widest text-gray-400 font-semibold uppercase">Nikkei & Rolls</span>
                </div>
            </a>

            <!-- Desktop Nav Links -->
            <nav class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-300">
                <a href="#menu" class="hover:text-brand-orange transition-colors">Menú Principales</a>
                <a href="#builder" class="hover:text-brand-orange transition-colors flex items-center gap-1">
                    <i class="fa-solid fa-wand-magic-sparkles text-brand-accent text-xs"></i> Arma tu Roll
                </a>
                <a href="#promos" class="hover:text-brand-orange transition-colors">Promociones</a>
                <a href="#location" class="hover:text-brand-orange transition-colors">Horarios y Ubicación</a>
            </nav>

            <!-- Action Controls -->
            <div class="flex items-center gap-3">
                <!-- GitHub Pages Deployment Info Badge -->
                <button onclick="toggleGithubModal()" class="hidden sm:flex items-center gap-2 px-3 py-1.5 rounded-lg text-xs font-semibold bg-gray-800/80 hover:bg-gray-700 text-gray-300 border border-gray-700 transition">
                    <i class="fa-brands fa-github text-sm"></i>
                    <span>GitHub Ready</span>
                </button>

                <!-- Shopping Cart Button -->
                <button onclick="toggleCart()" class="relative bg-brand-orange hover:bg-orange-600 text-white p-3 sm:px-5 sm:py-2.5 rounded-xl font-semibold flex items-center gap-2 shadow-lg shadow-brand-orange/20 hover:scale-105 active:scale-95 transition">
                    <i class="fa-solid fa-cart-shopping"></i>
                    <span class="hidden sm:inline">Tu Pedido</span>
                    <span id="cart-badge" class="bg-white text-brand-dark text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center border border-brand-orange">0</span>
                </button>

                <!-- Mobile Menu Button -->
                <button onclick="toggleMobileNav()" class="md:hidden text-gray-300 hover:text-white p-2">
                    <i class="fa-solid fa-bars text-xl" id="menu-icon"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobile-nav" class="hidden md:hidden bg-brand-surface border-b border-gray-800 px-6 py-4 space-y-3">
            <a href="#menu" onclick="toggleMobileNav()" class="block text-gray-300 hover:text-brand-orange py-1">Menú Principal</a>
            <a href="#builder" onclick="toggleMobileNav()" class="block text-brand-accent font-semibold py-1">Arma tu Roll Personalizado</a>
            <a href="#promos" onclick="toggleMobileNav()" class="block text-gray-300 hover:text-brand-orange py-1">Promociones Especiales</a>
            <a href="#location" onclick="toggleMobileNav()" class="block text-gray-300 hover:text-brand-orange py-1">Ubicación y Contacto</a>
            <button onclick="toggleGithubModal(); toggleMobileNav();" class="w-full text-left text-xs text-gray-400 py-2 border-t border-gray-800 flex items-center gap-2">
                <i class="fa-brands fa-github"></i> Instrucciones Deploy GitHub Pages
            </button>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Section -->
        <section class="relative py-12 md:py-20 overflow-hidden">
            <div class="absolute inset-0 bg-gradient-to-r from-black via-brand-dark/95 to-transparent z-10"></div>
            <!-- Background Image with fallback -->
            <div class="absolute inset-0 bg-cover bg-center opacity-40 scale-105" style="background-image: url('https://images.unsplash.com/photo-1579871494447-9811cf80d66c?q=80&w=1600&auto=format&fit=crop');"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-20">
                <div class="max-w-2xl space-y-6">
                    <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-brand-orange/20 border border-brand-orange/40 text-brand-orange text-xs font-bold uppercase tracking-wider">
                        <span class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></span>
                        Abierto Ahora • Pedidos Online en Vivo
                    </div>
                    
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-black tracking-tight text-white leading-none">
                        Sabor <span class="bg-gradient-to-r from-brand-orange to-brand-accent bg-clip-text text-transparent">Auténtico</span> y Rolls Exclusivos
                    </h1>

                    <p class="text-gray-300 text-base sm:text-lg font-normal leading-relaxed">
                        Pide el mejor sushi fresco, rolls fritos al panko y combinaciones Nikkei directo a tu puerta o para retiro local. 
                    </p>

                    <div class="flex flex-wrap items-center gap-4 pt-2">
                        <a href="#menu" class="bg-gradient-to-r from-brand-orange to-brand-red text-white px-7 py-3.5 rounded-xl font-bold shadow-lg glow-orange hover:opacity-95 transition flex items-center gap-2">
                            <i class="fa-solid fa-utensils"></i> Explorar Menú
                        </a>
                        <a href="#builder" class="bg-brand-card hover:bg-gray-800 text-gray-200 border border-gray-700 px-6 py-3.5 rounded-xl font-semibold transition flex items-center gap-2">
                            <i class="fa-solid fa-wand-magic-sparkles text-brand-accent"></i> Crear mi Roll
                        </a>
                    </div>

                    <!-- Quick Info Badges -->
                    <div class="pt-6 grid grid-cols-3 gap-4 border-t border-gray-800/80 text-gray-400 text-xs sm:text-sm">
                        <div class="flex items-center gap-2">
                            <i class="fa-solid fa-motorcycle text-brand-orange text-base"></i>
                            <span>Delivery Rápido</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <i class="fa-solid fa-fish text-brand-orange text-base"></i>
                            <span>Pesca Fresca del Día</span>
                        </div>
                        <div class="flex items-center gap-2">
                            <i class="fa-brands fa-whatsapp text-green-400 text-base"></i>
                            <span>Pedido Express</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Promo Banners -->
        <section id="promos" class="py-8 bg-brand-surface border-y border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex items-center justify-between mb-6">
                    <h2 class="text-xl font-extrabold text-white flex items-center gap-2">
                        <i class="fa-solid fa-fire text-brand-orange"></i> Promociones de Hoy
                    </h2>
                    <span class="text-xs text-brand-accent font-semibold">Ofertas por tiempo limitado</span>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <!-- Promo 1 -->
                    <div class="bg-gradient-to-r from-red-950/60 to-brand-card border border-red-900/40 rounded-2xl p-5 flex flex-col sm:flex-row items-center gap-5 relative overflow-hidden group">
                        <img src="https://images.unsplash.com/photo-1611143669185-af224c5e3252?q=80&w=400&auto=format&fit=crop" alt="Promo 30 piezas" class="w-full sm:w-32 h-32 object-cover rounded-xl group-hover:scale-105 transition-transform">
                        <div class="space-y-2 text-center sm:text-left flex-grow">
                            <span class="bg-red-600 text-white text-[10px] font-black px-2.5 py-1 rounded-full uppercase">Super Combo</span>
                            <h3 class="text-lg font-bold text-white">Promo 30 Piezas Mixtas</h3>
                            <p class="text-xs text-gray-300">10 Panko Ebi + 10 California Salmon + 10 Hosomaki Palta</p>
                            <div class="flex items-center justify-between pt-1">
                                <span class="text-xl font-black text-brand-accent">$14.990 <span class="text-xs text-gray-500 line-through font-normal">$19.990</span></span>
                                <button onclick="addToCartDirect('Promo 30 Piezas Mixtas', 14990, 'https://images.unsplash.com/photo-1611143669185-af224c5e3252?q=80&w=400&auto=format&fit=crop')" class="bg-brand-orange hover:bg-orange-600 text-white px-4 py-2 rounded-lg text-xs font-bold transition">
                                    Pedir Promo
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Promo 2 -->
                    <div class="bg-gradient-to-r from-amber-950/60 to-brand-card border border-amber-900/40 rounded-2xl p-5 flex flex-col sm:flex-row items-center gap-5 relative overflow-hidden group">
                        <img src="https://images.unsplash.com/photo-1553621042-f6e147245754?q=80&w=400&auto=format&fit=crop" alt="Duo Nikkei" class="w-full sm:w-32 h-32 object-cover rounded-xl group-hover:scale-105 transition-transform">
                        <div class="space-y-2 text-center sm:text-left flex-grow">
                            <span class="bg-amber-600 text-white text-[10px] font-black px-2.5 py-1 rounded-full uppercase">Especial Parejas</span>
                            <h3 class="text-lg font-bold text-white">Duo Nikkei + Bebida 1.5L</h3>
                            <p class="text-xs text-gray-300">2 Rolls Nikkei Premium a elección + Coca Cola 1.5L</p>
                            <div class="flex items-center justify-between pt-1">
                                <span class="text-xl font-black text-brand-accent">$16.500 <span class="text-xs text-gray-500 line-through font-normal">$21.500</span></span>
                                <button onclick="addToCartDirect('Duo Nikkei + Bebida 1.5L', 16500, 'https://images.unsplash.com/photo-1553621042-f6e147245754?q=80&w=400&auto=format&fit=crop')" class="bg-brand-orange hover:bg-orange-600 text-white px-4 py-2 rounded-lg text-xs font-bold transition">
                                    Pedir Promo
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Menu Section -->
        <section id="menu" class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-8">
                <div>
                    <h2 class="text-3xl font-black text-white">Nuestro Menú</h2>
                    <p class="text-gray-400 text-sm mt-1">Selecciona tus favoritos y añádelos al carrito de compra</p>
                </div>

                <!-- Search Input -->
                <div class="relative w-full md:w-72">
                    <i class="fa-solid fa-magnifying-glass absolute left-3.5 top-1/2 -translate-y-1/2 text-gray-500 text-sm"></i>
                    <input type="text" id="menu-search" oninput="filterMenu()" placeholder="Buscar roll, ingrediente..." class="w-full bg-brand-surface border border-gray-700 rounded-xl pl-10 pr-4 py-2.5 text-sm text-white focus:outline-none focus:border-brand-orange transition">
                </div>
            </div>

            <!-- Category Filter Tabs -->
            <div class="flex items-center gap-2 overflow-x-auto pb-4 mb-8 scrollbar-none border-b border-gray-800" id="category-tabs">
                <!-- Javascript will populate category buttons -->
            </div>

            <!-- Menu Grid Container -->
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6" id="menu-grid">
                <!-- Javascript dynamically populates menu cards here -->
            </div>
        </section>

        <!-- Interactive Roll Builder Section -->
        <section id="builder" class="py-16 bg-gradient-to-b from-brand-surface to-brand-dark border-t border-gray-800 relative">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center max-w-2xl mx-auto mb-10 space-y-2">
                    <span class="text-brand-orange text-xs font-black uppercase tracking-widest bg-brand-orange/10 border border-brand-orange/30 px-3 py-1 rounded-full">Exclusivo Kurama</span>
                    <h2 class="text-3xl sm:text-4xl font-black text-white">Arma tu Roll a la Medida</h2>
                    <p class="text-gray-400 text-sm">Escoge tu envoltura, proteína, rellenos y salsa favorita. ¡Nosotros lo preparamos al instante!</p>
                </div>

                <div class="glass-panel rounded-3xl p-6 sm:p-8 max-w-4xl mx-auto border border-gray-700 shadow-2xl">
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                        
                        <!-- Configuration Steps -->
                        <div class="lg:col-span-2 space-y-6">
                            
                            <!-- Step 1: Envoltura -->
                            <div>
                                <label class="block text-sm font-extrabold text-brand-accent uppercase tracking-wider mb-2">1. Cobertura Exterior (1 opc.)</label>
                                <div class="grid grid-cols-2 sm:grid-cols-3 gap-2.5" id="opt-wrapper">
                                    <!-- Buttons injected by JS -->
                                </div>
                            </div>

                            <!-- Step 2: Proteína -->
                            <div>
                                <label class="block text-sm font-extrabold text-brand-accent uppercase tracking-wider mb-2">2. Proteína Principal (1 opc.)</label>
                                <div class="grid grid-cols-2 sm:grid-cols-3 gap-2.5" id="opt-protein">
                                    <!-- Buttons injected by JS -->
                                </div>
                            </div>

                            <!-- Step 3: Rellenos (hasta 2) -->
                            <div>
                                <label class="block text-sm font-extrabold text-brand-accent uppercase tracking-wider mb-2">3. Rellenos Interiores (Elige 2)</label>
                                <div class="grid grid-cols-2 sm:grid-cols-3 gap-2.5" id="opt-filling">
                                    <!-- Buttons injected by JS -->
                                </div>
                            </div>

                            <!-- Step 4: Salsa Topping -->
                            <div>
                                <label class="block text-sm font-extrabold text-brand-accent uppercase tracking-wider mb-2">4. Salsa / Topping Final</label>
                                <div class="grid grid-cols-2 sm:grid-cols-3 gap-2.5" id="opt-sauce">
                                    <!-- Buttons injected by JS -->
                                </div>
                            </div>

                        </div>

                        <!-- Live Summary Box -->
                        <div class="bg-brand-card rounded-2xl p-6 flex flex-col justify-between border border-gray-700">
                            <div>
                                <h3 class="text-lg font-bold text-white border-b border-gray-700 pb-3 flex items-center justify-between">
                                    <span>Resumen de tu Roll</span>
                                    <i class="fa-solid fa-sushi text-brand-orange"></i>
                                </h3>

                                <div class="space-y-3 py-4 text-xs sm:text-sm">
                                    <div class="flex justify-between text-gray-300">
                                        <span class="text-gray-400">Cobertura:</span>
                                        <span id="summary-wrapper" class="font-semibold text-white">No seleccionado</span>
                                    </div>
                                    <div class="flex justify-between text-gray-300">
                                        <span class="text-gray-400">Proteína:</span>
                                        <span id="summary-protein" class="font-semibold text-white">No seleccionado</span>
                                    </div>
                                    <div class="flex justify-between text-gray-300">
                                        <span class="text-gray-400">Rellenos:</span>
                                        <span id="summary-fillings" class="font-semibold text-white">Sin selección</span>
                                    </div>
                                    <div class="flex justify-between text-gray-300">
                                        <span class="text-gray-400">Salsa:</span>
                                        <span id="summary-sauce" class="font-semibold text-white">Sin salsa</span>
                                    </div>
                                </div>
                            </div>

                            <div class="border-t border-gray-700 pt-4 space-y-4">
                                <div class="flex items-center justify-between">
                                    <span class="text-sm font-semibold text-gray-400">Precio Total:</span>
                                    <span id="custom-roll-price" class="text-2xl font-black text-brand-accent">$7.990</span>
                                </div>

                                <button onclick="addCustomRollToCart()" id="btn-add-custom" class="w-full bg-gradient-to-r from-brand-orange to-brand-red text-white py-3 rounded-xl font-bold hover:shadow-lg hover:shadow-brand-orange/30 transition flex items-center justify-center gap-2">
                                    <i class="fa-solid fa-plus"></i> Agregar al Pedido
                                </button>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </section>

        <!-- Location & Information -->
        <section id="location" class="py-12 bg-brand-surface border-t border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                    <div class="space-y-4">
                        <span class="text-brand-orange text-xs font-bold uppercase tracking-widest">Encuéntranos</span>
                        <h2 class="text-3xl font-black text-white">Ubicación y Horarios de Atención</h2>
                        <p class="text-gray-400 text-sm">
                            Preparamos cada pieza al minuto con los más altos estándares de higiene y frescura. 
                        </p>

                        <div class="space-y-3 pt-2 text-sm text-gray-300">
                            <div class="flex items-start gap-3">
                                <i class="fa-solid fa-location-dot text-brand-orange mt-1"></i>
                                <div>
                                    <strong class="text-white block">Dirección Principal:</strong>
                                    <span>Las Heras 526, Concepción / El Chacay Km43</span>
                                </div>
                            </div>

                            <div class="flex items-start gap-3">
                                <i class="fa-solid fa-clock text-brand-orange mt-1"></i>
                                <div>
                                    <strong class="text-white block">Horario Delivery:</strong>
                                    <span>Lunes a Jueves: 16:00 - 23:00 hrs<br>Viernes a Sábado: 12:00 - 00:00 hrs</span>
                                </div>
                            </div>

                            <div class="flex items-start gap-3">
                                <i class="fa-brands fa-whatsapp text-green-400 text-lg mt-0.5"></i>
                                <div>
                                    <strong class="text-white block">Contacto Directo WhatsApp:</strong>
                                    <span>+56 9 4297 3749</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Interactive Info Box -->
                    <div class="bg-brand-card border border-gray-700 rounded-2xl p-6 space-y-4 shadow-xl">
                        <h3 class="text-lg font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-shield-halved text-brand-orange"></i> Garantía Kurama
                        </h3>
                        <ul class="space-y-2.5 text-xs sm:text-sm text-gray-300">
                            <li class="flex items-center gap-2">
                                <i class="fa-solid fa-check text-green-400"></i> Empaques térmicos ecológicos y herméticos
                            </li>
                            <li class="flex items-center gap-2">
                                <i class="fa-solid fa-check text-green-400"></i> Incluye palillos, soya, jengibre y wasabi
                            </li>
                            <li class="flex items-center gap-2">
                                <i class="fa-solid fa-check text-green-400"></i> Pago seguro vía transferencia o contra entrega
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Slide-over Cart Drawer -->
    <div id="cart-drawer-overlay" class="fixed inset-0 bg-black/70 backdrop-blur-sm z-50 hidden transition-opacity" onclick="toggleCart()"></div>
    
    <aside id="cart-drawer" class="fixed top-0 right-0 h-full w-full sm:w-96 bg-brand-surface border-l border-gray-800 z-50 transform translate-x-full cart-drawer flex flex-col justify-between shadow-2xl">
        <!-- Cart Header -->
        <div class="p-5 border-b border-gray-800 flex items-center justify-between bg-brand-card">
            <div class="flex items-center gap-2">
                <i class="fa-solid fa-bag-shopping text-brand-orange text-lg"></i>
                <h3 class="font-extrabold text-white text-lg">Tu Carrito de Compras</h3>
            </div>
            <button onclick="toggleCart()" class="text-gray-400 hover:text-white p-2 rounded-lg hover:bg-gray-800">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
        </div>

        <!-- Cart Items List -->
        <div id="cart-items-container" class="p-5 flex-grow overflow-y-auto space-y-4">
            <!-- Dynamically populated cart items or empty state -->
        </div>

        <!-- Cart Footer Checkout Form -->
        <div class="p-5 border-t border-gray-800 bg-brand-card space-y-4">
            
            <!-- Service Type Selector -->
            <div class="grid grid-cols-2 gap-2 p-1 bg-brand-dark rounded-xl text-xs font-semibold">
                <button onclick="setDeliveryType('delivery')" id="btn-type-delivery" class="py-2 rounded-lg bg-brand-orange text-white text-center transition">
                    <i class="fa-solid fa-motorcycle mr-1"></i> Delivery
                </button>
                <button onclick="setDeliveryType('pickup')" id="btn-type-pickup" class="py-2 rounded-lg text-gray-400 hover:text-white text-center transition">
                    <i class="fa-solid fa-store mr-1"></i> Retiro Local
                </button>
            </div>

            <!-- Customer Details Inputs -->
            <div class="space-y-2 text-xs">
                <input type="text" id="cust-name" placeholder="Tu Nombre completo *" class="w-full bg-brand-surface border border-gray-700 rounded-lg px-3 py-2 text-white focus:outline-none focus:border-brand-orange">
                <input type="text" id="cust-address" placeholder="Dirección de entrega y Sector *" class="w-full bg-brand-surface border border-gray-700 rounded-lg px-3 py-2 text-white focus:outline-none focus:border-brand-orange">
                <select id="cust-payment" class="w-full bg-brand-surface border border-gray-700 rounded-lg px-3 py-2 text-white focus:outline-none focus:border-brand-orange">
                    <option value="Transferencia Bancaria">Pago: Transferencia Bancaria</option>
                    <option value="Efectivo al repartidor">Pago: Efectivo al repartidor</option>
                    <option value="Tarjeta Débito/Crédito">Pago: Tarjeta (Máquina POS)</option>
                </select>
            </div>

            <!-- Price Breakdown -->
            <div class="space-y-1.5 text-xs text-gray-400 pt-2 border-t border-gray-800">
                <div class="flex justify-between">
                    <span>Subtotal Productos:</span>
                    <span id="cart-subtotal" class="font-semibold text-white">$0</span>
                </div>
                <div class="flex justify-between" id="row-delivery-fee">
                    <span>Costo Envío:</span>
                    <span id="cart-delivery-fee" class="font-semibold text-white">$2.000</span>
                </div>
                <div class="flex justify-between text-base font-extrabold text-white pt-2 border-t border-gray-800">
                    <span>Total a Pagar:</span>
                    <span id="cart-total" class="text-brand-accent">$0</span>
                </div>
            </div>

            <!-- Submit WhatsApp Order Button -->
            <button onclick="sendWhatsAppOrder()" class="w-full bg-green-600 hover:bg-green-500 text-white py-3 rounded-xl font-bold shadow-lg shadow-green-900/30 transition flex items-center justify-center gap-2">
                <i class="fa-brands fa-whatsapp text-lg"></i> Confirmar Pedido por WhatsApp
            </button>
        </div>
    </aside>

    <!-- Modal Instructions for GitHub Pages -->
    <div id="github-modal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
        <div class="bg-brand-surface border border-gray-700 rounded-2xl max-w-lg w-full p-6 space-y-4 relative shadow-2xl">
            <button onclick="toggleGithubModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            
            <div class="flex items-center gap-3 text-brand-orange">
                <i class="fa-brands fa-github text-3xl"></i>
                <h3 class="text-xl font-extrabold text-white">¿Cómo publicar en GitHub Pages?</h3>
            </div>

            <p class="text-xs sm:text-sm text-gray-300 leading-relaxed">
                Este archivo es un <strong class="text-white">Single File App</strong> 100% autocontenido. Sigue estos pasos para activarlo en tu repositorio:
            </p>

            <ol class="space-y-2.5 text-xs text-gray-300 list-decimal list-inside bg-brand-card p-4 rounded-xl border border-gray-800">
                <li>Nombra este archivo como <code class="bg-gray-800 text-brand-accent px-1.5 py-0.5 rounded">index.html</code>.</li>
                <li>Sube el archivo a la rama raíz (<code class="text-brand-accent">main</code> o <code class="text-brand-accent">master</code>) de tu repositorio en GitHub.</li>
                <li>En GitHub, ve a <strong class="text-white">Settings</strong> &rarr; <strong class="text-white">Pages</strong>.</li>
                <li>En <strong class="text-white">Source</strong>, selecciona la rama <code class="text-brand-accent">main</code> y carpeta <code class="text-brand-accent">/ (root)</code>.</li>
                <li>Haz clic en <strong class="text-white">Save</strong>. Tu sitio estará en línea en un par de minutos.</li>
            </ol>

            <div class="pt-2 text-right">
                <button onclick="toggleGithubModal()" class="bg-brand-orange text-white px-5 py-2 rounded-xl text-xs font-bold">
                    Entendido
                </button>
            </div>
        </div>
    </div>

    <!-- Floating Toast Notification -->
    <div id="toast-container" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-50 pointer-events-none flex flex-col gap-2"></div>

    <!-- Footer -->
    <footer class="bg-brand-dark border-t border-gray-800/80 py-8 text-center text-xs text-gray-500">
        <div class="max-w-7xl mx-auto px-4 space-y-3">
            <div class="flex items-center justify-center gap-2 text-white font-bold text-sm">
                <span class="text-brand-orange">KURAMA SUSHI</span> • Nikkei & Bar
            </div>
            <p>&copy; 2026 Kurama Sushi. Todos los derechos reservados. Desarrollado para GitHub Pages.</p>
        </div>
    </footer>

    <script>
        /* ==========================================================================
           1. MENU DATABASE
           ========================================================================== */
        const categories = [
            { id: 'all', name: 'Todos' },
            { id: 'promos', name: 'Promos & Combos' },
            { id: 'panko', name: 'Hot Rolls (Panko)' },
            { id: 'nikkei', name: 'Especiales Nikkei' },
            { id: 'hosomaki', name: 'Hosomaki & Nigiri' },
            { id: 'bebidas', name: 'Bebidas & Postres' }
        ];

        const menuItems = [
            {
                id: 1,
                name: "Ebi Panko Roll (10 pz)",
                category: "panko",
                price: 6490,
                description: "Camarón furai, queso crema, cebollín, empanizado en panko crujiente.",
                image: "https://images.unsplash.com/photo-1579871494447-9811cf80d66c?q=80&w=400&auto=format&fit=crop",
                badge: "Más Vendido"
            },
            {
                id: 2,
                name: "Chicken Supreme Panko (10 pz)",
                category: "panko",
                price: 5990,
                description: "Pollo teriyaki, queso crema y pimentón asado empanizado en panko caliente.",
                image: "https://images.unsplash.com/photo-1611143669185-af224c5e3252?q=80&w=400&auto=format&fit=crop",
                badge: "Hot"
            },
            {
                id: 3,
                name: "Sake Nikkei Special (10 pz)",
                category: "nikkei",
                price: 7490,
                description: "Salmón fresco, palta, envuelto en salmón flameado con salsa teriyaki y sésamo.",
                image: "https://images.unsplash.com/photo-1553621042-f6e147245754?q=80&w=400&auto=format&fit=crop",
                badge: "Chef Special"
            },
            {
                id: 4,
                name: "Tuna Avocado Crown (10 pz)",
                category: "nikkei",
                price: 7990,
                description: "Atún rojo, queso crema, cebollín, cubierto de palta madura y salsa acevichada.",
                image: "https://images.unsplash.com/photo-1563245372-f21724e3856d?q=80&w=400&auto=format&fit=crop",
                badge: "Premium"
            },
            {
                id: 5,
                name: "Hosomaki Sake (8 pz)",
                category: "hosomaki",
                price: 3990,
                description: "Roll delgado envuelto en alga nori relleno de fino salmón fresco.",
                image: "https://images.unsplash.com/photo-1617196034796-73dfa7b1fd56?q=80&w=400&auto=format&fit=crop",
                badge: "Clásico"
            },
            {
                id: 6,
                name: "Nigiri Trio Mix (6 pz)",
                category: "hosomaki",
                price: 5490,
                description: "Bocados de arroz shari cubiertos de salmón, camarón y atún fresco.",
                image: "https://images.unsplash.com/photo-1611143669185-af224c5e3252?q=80&w=400&auto=format&fit=crop",
                badge: "Fresco"
            },
            {
                id: 7,
                name: "Promo Mega Kurama 50 Piezas",
                category: "promos",
                price: 22990,
                description: "10 Ebi Panko + 10 Chicken Panko + 10 California Sake + 10 Hosomaki + 10 Nigiris.",
                image: "https://images.unsplash.com/photo-1579871494447-9811cf80d66c?q=80&w=400&auto=format&fit=crop",
                badge: "Super Ahorro"
            },
            {
                id: 8,
                name: "Gyoza de Camarón (5 pz)",
                category: "promos",
                price: 3990,
                description: "Empanaditas japonesas al vapor y doradas a la plancha con salsa ponzu.",
                image: "https://images.unsplash.com/photo-1541696432-82c6da8ce7bf?q=80&w=400&auto=format&fit=crop",
                badge: "Entrada"
            },
            {
                id: 9,
                name: "Bebida Lipton Ice Tea 1.5L",
                category: "bebidas",
                price: 2500,
                description: "Té frío refrescante sabor Limón o Durazno.",
                image: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?q=80&w=400&auto=format&fit=crop",
                badge: "Bebida"
            }
        ];

        /* ==========================================================================
           2. CUSTOM ROLL BUILDER OPTIONS
           ========================================================================== */
        const builderData = {
            wrappers: [
                { id: 'panko', name: 'Panko Frito', price: 0 },
                { id: 'palta', name: 'Envoltorio Palta', price: 500 },
                { id: 'salmon', name: 'Envoltorio Salmón', price: 900 },
                { id: 'sesamo', name: 'Sésamo / Cereal', price: 0 }
            ],
            proteins: [
                { id: 'salmon', name: 'Salmón Fresco', price: 500 },
                { id: 'camaron', name: 'Camarón Panko', price: 500 },
                { id: 'pollo', name: 'Pollo Teriyaki', price: 0 },
                { id: 'atun', name: 'Atún Rojo', price: 800 }
            ],
            fillings: [
                { id: 'queso', name: 'Queso Crema' },
                { id: 'palta', name: 'Palta' },
                { id: 'cebollin', name: 'Cebollín' },
                { id: 'pimenton', name: 'Pimentón Asado' }
            ],
            sauces: [
                { id: 'teriyaki', name: 'Salsa Teriyaki' },
                { id: 'acevichada', name: 'Salsa Acevichada' },
                { id: 'spicy', name: 'Salsa Spicy Mayo' },
                { id: 'sin_salsa', name: 'Sin Salsa Extra' }
            ]
        };

        // Custom Roll Selection State
        let customRollState = {
            wrapper: builderData.wrappers[0],
            protein: builderData.proteins[0],
            fillings: [builderData.fillings[0], builderData.fillings[1]],
            sauce: builderData.sauces[0],
            basePrice: 6990
        };

        /* ==========================================================================
           3. APPLICATION STATE & CART MANAGEMENT
           ========================================================================== */
        let cart = JSON.parse(localStorage.getItem('kurama_cart')) || [];
        let activeCategory = 'all';
        let deliveryType = 'delivery'; // 'delivery' or 'pickup'
        const WHATSAPP_PHONE = "56942973749";

        // Initialize application on DOM content loaded
        document.addEventListener('DOMContentLoaded', () => {
            renderCategories();
            renderMenu();
            initRollBuilder();
            updateCartUI();
        });

        /* ==========================================================================
           4. MENU RENDERING & FILTERING
           ========================================================================== */
        function renderCategories() {
            const container = document.getElementById('category-tabs');
            container.innerHTML = categories.map(cat => `
                <button onclick="setCategory('${cat.id}')" 
                        class="px-4 py-2 rounded-xl text-xs sm:text-sm font-bold whitespace-nowrap transition-all ${activeCategory === cat.id ? 'bg-brand-orange text-white shadow-lg shadow-brand-orange/20' : 'bg-brand-surface text-gray-400 hover:text-white hover:bg-brand-card'}">
                    ${cat.name}
                </button>
            `).join('');
        }

        function setCategory(catId) {
            activeCategory = catId;
            renderCategories();
            renderMenu();
        }

        function filterMenu() {
            renderMenu();
        }

        function renderMenu() {
            const grid = document.getElementById('menu-grid');
            const searchVal = document.getElementById('menu-search').value.toLowerCase();

            const filtered = menuItems.filter(item => {
                const matchesCat = activeCategory === 'all' || item.category === activeCategory;
                const matchesSearch = item.name.toLowerCase().includes(searchVal) || item.description.toLowerCase().includes(searchVal);
                return matchesCat && matchesSearch;
            });

            if (filtered.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full py-12 text-center text-gray-500 space-y-2">
                        <i class="fa-solid fa-magnifying-glass text-3xl"></i>
                        <p class="text-sm">No encontramos rolls que coincidan con tu búsqueda.</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = filtered.map(item => `
                <div class="bg-brand-card rounded-2xl overflow-hidden border border-gray-800 hover:border-gray-700 transition flex flex-col justify-between group">
                    <div>
                        <div class="relative h-48 overflow-hidden bg-gray-900">
                            <img src="${item.image}" alt="${item.name}" loading="lazy" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" onerror="this.src='https://placehold.co/400x300/1A1D24/FFFFFF?text=Kurama+Sushi'">
                            <span class="absolute top-3 right-3 bg-brand-dark/90 backdrop-blur-md border border-brand-orange/40 text-brand-orange text-[10px] font-extrabold px-2.5 py-1 rounded-full uppercase">
                                ${item.badge}
                            </span>
                        </div>
                        <div class="p-5 space-y-2">
                            <h3 class="font-bold text-white text-base group-hover:text-brand-orange transition-colors">${item.name}</h3>
                            <p class="text-xs text-gray-400 line-clamp-2 leading-relaxed">${item.description}</p>
                        </div>
                    </div>

                    <div class="p-5 pt-0 flex items-center justify-between border-t border-gray-800/60 mt-2">
                        <span class="text-lg font-black text-brand-accent">$${item.price.toLocaleString('es-CL')}</span>
                        <button onclick="addToCartDirect('${item.name.replace(/'/g, "\\'")}', ${item.price}, '${item.image}')" class="bg-brand-surface hover:bg-brand-orange hover:text-white text-gray-200 border border-gray-700 hover:border-brand-orange px-3.5 py-2 rounded-xl text-xs font-bold transition flex items-center gap-1.5">
                            <i class="fa-solid fa-plus"></i> Agregar
                        </button>
                    </div>
                </div>
            `).join('');
        }

        /* ==========================================================================
           5. ROLL BUILDER LOGIC
           ========================================================================== */
        function initRollBuilder() {
            // Render Wrappers
            document.getElementById('opt-wrapper').innerHTML = builderData.wrappers.map(w => `
                <button onclick="selectWrapper('${w.id}')" id="btn-w-${w.id}" class="opt-btn-wrapper p-2.5 rounded-xl border border-gray-700 text-xs font-semibold text-left transition hover:border-brand-orange">
                    ${w.name} ${w.price > 0 ? `<span class="text-brand-accent block text-[10px]">+$${w.price}</span>` : ''}
                </button>
            `).join('');

            // Render Proteins
            document.getElementById('opt-protein').innerHTML = builderData.proteins.map(p => `
                <button onclick="selectProtein('${p.id}')" id="btn-p-${p.id}" class="opt-btn-protein p-2.5 rounded-xl border border-gray-700 text-xs font-semibold text-left transition hover:border-brand-orange">
                    ${p.name} ${p.price > 0 ? `<span class="text-brand-accent block text-[10px]">+$${p.price}</span>` : ''}
                </button>
            `).join('');

            // Render Fillings
            document.getElementById('opt-filling').innerHTML = builderData.fillings.map(f => `
                <button onclick="toggleFilling('${f.id}')" id="btn-f-${f.id}" class="opt-btn-filling p-2.5 rounded-xl border border-gray-700 text-xs font-semibold text-left transition hover:border-brand-orange">
                    ${f.name}
                </button>
            `).join('');

            // Render Sauces
            document.getElementById('opt-sauce').innerHTML = builderData.sauces.map(s => `
                <button onclick="selectSauce('${s.id}')" id="btn-s-${s.id}" class="opt-btn-sauce p-2.5 rounded-xl border border-gray-700 text-xs font-semibold text-left transition hover:border-brand-orange">
                    ${s.name}
                </button>
            `).join('');

            updateBuilderUI();
        }

        function selectWrapper(id) {
            customRollState.wrapper = builderData.wrappers.find(w => w.id === id);
            updateBuilderUI();
        }

        function selectProtein(id) {
            customRollState.protein = builderData.proteins.find(p => p.id === id);
            updateBuilderUI();
        }

        function toggleFilling(id) {
            const fillingObj = builderData.fillings.find(f => f.id === id);
            const existsIndex = customRollState.fillings.findIndex(f => f.id === id);

            if (existsIndex > -1) {
                if (customRollState.fillings.length > 1) {
                    customRollState.fillings.splice(existsIndex, 1);
                } else {
                    showToast("Debes mantener al menos 1 relleno");
                }
            } else {
                if (customRollState.fillings.length < 2) {
                    customRollState.fillings.push(fillingObj);
                } else {
                    // Replace oldest filling
                    customRollState.fillings.shift();
                    customRollState.fillings.push(fillingObj);
                }
            }
            updateBuilderUI();
        }

        function selectSauce(id) {
            customRollState.sauce = builderData.sauces.find(s => s.id === id);
            updateBuilderUI();
        }

        function updateBuilderUI() {
            // Highlight Buttons
            document.querySelectorAll('.opt-btn-wrapper').forEach(b => b.className = b.className.replace('bg-brand-orange text-white border-brand-orange', 'bg-brand-surface text-gray-300'));
            document.querySelectorAll('.opt-btn-protein').forEach(b => b.className = b.className.replace('bg-brand-orange text-white border-brand-orange', 'bg-brand-surface text-gray-300'));
            document.querySelectorAll('.opt-btn-filling').forEach(b => b.className = b.className.replace('bg-brand-orange text-white border-brand-orange', 'bg-brand-surface text-gray-300'));
            document.querySelectorAll('.opt-btn-sauce').forEach(b => b.className = b.className.replace('bg-brand-orange text-white border-brand-orange', 'bg-brand-surface text-gray-300'));

            document.getElementById(`btn-w-${customRollState.wrapper.id}`)?.classList.add('bg-brand-orange', 'text-white', 'border-brand-orange');
            document.getElementById(`btn-p-${customRollState.protein.id}`)?.classList.add('bg-brand-orange', 'text-white', 'border-brand-orange');
            
            customRollState.fillings.forEach(f => {
                document.getElementById(`btn-f-${f.id}`)?.classList.add('bg-brand-orange', 'text-white', 'border-brand-orange');
            });

            document.getElementById(`btn-s-${customRollState.sauce.id}`)?.classList.add('bg-brand-orange', 'text-white', 'border-brand-orange');

            // Summary Texts
            document.getElementById('summary-wrapper').textContent = customRollState.wrapper.name;
            document.getElementById('summary-protein').textContent = customRollState.protein.name;
            document.getElementById('summary-fillings').textContent = customRollState.fillings.map(f => f.name).join(' + ');
            document.getElementById('summary-sauce').textContent = customRollState.sauce.name;

            // Price Calculation
            const totalPrice = customRollState.basePrice + customRollState.wrapper.price + customRollState.protein.price;
            document.getElementById('custom-roll-price').textContent = `$${totalPrice.toLocaleString('es-CL')}`;
        }

        function addCustomRollToCart() {
            const totalPrice = customRollState.basePrice + customRollState.wrapper.price + customRollState.protein.price;
            const rollTitle = `Custom Roll (${customRollState.wrapper.name} / ${customRollState.protein.name})`;
            const details = `${customRollState.fillings.map(f => f.name).join(', ')} | ${customRollState.sauce.name}`;

            const cartItem = {
                id: 'custom-' + Date.now(),
                name: rollTitle,
                details: details,
                price: totalPrice,
                quantity: 1,
                image: 'https://images.unsplash.com/photo-1579871494447-9811cf80d66c?q=80&w=200&auto=format&fit=crop'
            };

            cart.push(cartItem);
            saveCart();
            updateCartUI();
            showToast("Roll personalizado agregado al carrito");
        }

        /* ==========================================================================
           6. CART OPERATIONS
           ========================================================================== */
        function addToCartDirect(name, price, image) {
            const existing = cart.find(i => i.name === name);
            if (existing) {
                existing.quantity += 1;
            } else {
                cart.push({
                    id: 'item-' + Date.now() + Math.random(),
                    name: name,
                    price: price,
                    quantity: 1,
                    image: image
                });
            }
            saveCart();
            updateCartUI();
            showToast(`"${name}" añadido al carrito`);
        }

        function updateQuantity(id, change) {
            const item = cart.find(i => i.id === id);
            if (item) {
                item.quantity += change;
                if (item.quantity <= 0) {
                    cart = cart.filter(i => i.id !== id);
                }
            }
            saveCart();
            updateCartUI();
        }

        function saveCart() {
            localStorage.setItem('kurama_cart', JSON.stringify(cart));
        }

        function setDeliveryType(type) {
            deliveryType = type;
            const btnDelivery = document.getElementById('btn-type-delivery');
            const btnPickup = document.getElementById('btn-type-pickup');
            const feeRow = document.getElementById('row-delivery-fee');

            if (type === 'delivery') {
                btnDelivery.className = "py-2 rounded-lg bg-brand-orange text-white text-center transition";
                btnPickup.className = "py-2 rounded-lg text-gray-400 hover:text-white text-center transition";
                feeRow.classList.remove('hidden');
            } else {
                btnPickup.className = "py-2 rounded-lg bg-brand-orange text-white text-center transition";
                btnDelivery.className = "py-2 rounded-lg text-gray-400 hover:text-white text-center transition";
                feeRow.classList.add('hidden');
            }
            updateCartTotals();
        }

        function updateCartUI() {
            const badge = document.getElementById('cart-badge');
            const container = document.getElementById('cart-items-container');

            const totalItemsCount = cart.reduce((acc, curr) => acc + curr.quantity, 0);
            badge.textContent = totalItemsCount;

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-12 text-gray-500 space-y-3">
                        <i class="fa-solid fa-basket-shopping text-4xl"></i>
                        <p class="text-xs">Tu carrito está vacío.<br>¡Explora el menú y agrega tus rolls!</p>
                    </div>
                `;
            } else {
                container.innerHTML = cart.map(item => `
                    <div class="flex items-center gap-3 bg-brand-dark p-3 rounded-xl border border-gray-800">
                        <img src="${item.image}" alt="${item.name}" class="w-14 h-14 object-cover rounded-lg">
                        <div class="flex-grow min-w-0">
                            <h4 class="text-xs font-bold text-white truncate">${item.name}</h4>
                            ${item.details ? `<p class="text-[10px] text-gray-400 truncate">${item.details}</p>` : ''}
                            <span class="text-xs font-black text-brand-accent">$${(item.price * item.quantity).toLocaleString('es-CL')}</span>
                        </div>
                        <div class="flex items-center gap-2 bg-brand-surface border border-gray-700 px-2 py-1 rounded-lg">
                            <button onclick="updateQuantity('${item.id}', -1)" class="text-gray-400 hover:text-white text-xs px-1">-</button>
                            <span class="text-xs font-bold text-white">${item.quantity}</span>
                            <button onclick="updateQuantity('${item.id}', 1)" class="text-gray-400 hover:text-white text-xs px-1">+</button>
                        </div>
                    </div>
                `).join('');
            }

            updateCartTotals();
        }

        function updateCartTotals() {
            const subtotal = cart.reduce((acc, item) => acc + (item.price * item.quantity), 0);
            const deliveryFee = (deliveryType === 'delivery' && subtotal > 0) ? 2000 : 0;
            const total = subtotal + deliveryFee;

            document.getElementById('cart-subtotal').textContent = `$${subtotal.toLocaleString('es-CL')}`;
            document.getElementById('cart-delivery-fee').textContent = `$${deliveryFee.toLocaleString('es-CL')}`;
            document.getElementById('cart-total').textContent = `$${total.toLocaleString('es-CL')}`;
        }

        /* ==========================================================================
           7. WHATSAPP ORDER DISPATCHER
           ========================================================================== */
        function sendWhatsAppOrder() {
            if (cart.length === 0) {
                showToast("Agrega al menos 1 producto antes de enviar el pedido.");
                return;
            }

            const name = document.getElementById('cust-name').value.trim();
            const address = document.getElementById('cust-address').value.trim();
            const payment = document.getElementById('cust-payment').value;

            if (!name) {
                showToast("Por favor ingresa tu nombre.");
                document.getElementById('cust-name').focus();
                return;
            }

            if (deliveryType === 'delivery' && !address) {
                showToast("Por favor ingresa tu dirección para el delivery.");
                document.getElementById('cust-address').focus();
                return;
            }

            const subtotal = cart.reduce((acc, item) => acc + (item.price * item.quantity), 0);
            const deliveryFee = (deliveryType === 'delivery') ? 2000 : 0;
            const total = subtotal + deliveryFee;

            let message = `*¡NUEVO PEDIDO - KURAMA SUSHI!* 🍣\n\n`;
            message += `👤 *Cliente:* ${name}\n`;
            message += `📍 *Tipo:* ${deliveryType === 'delivery' ? 'Delivery a Domicilio' : 'Retiro en Local'}\n`;
            if (deliveryType === 'delivery') {
                message += `🏠 *Dirección:* ${address}\n`;
            }
            message += `💳 *Método de Pago:* ${payment}\n\n`;
            message += `*RESUMEN DEL PEDIDO:*\n`;

            cart.forEach((item, index) => {
                message += `${index + 1}. *${item.name}* (x${item.quantity}) - $${(item.price * item.quantity).toLocaleString('es-CL')}\n`;
                if (item.details) {
                    message += `   _Ingredientes: ${item.details}_\n`;
                }
            });

            message += `\n------------------------------\n`;
            message += `Subtotal: $${subtotal.toLocaleString('es-CL')}\n`;
            if (deliveryType === 'delivery') {
                message += `Envío: $${deliveryFee.toLocaleString('es-CL')}\n`;
            }
            message += `*TOTAL A PAGAR: $${total.toLocaleString('es-CL')}*\n\n`;
            message += `¡Muchas gracias! Quedo a la espera de la confirmación.`;

            const encodedURL = `https://wa.me/${WHATSAPP_PHONE}?text=${encodeURIComponent(message)}`;
            window.open(encodedURL, '_blank');
        }

        /* ==========================================================================
           8. UTILITY MODALS & TOAST NOTIFICATIONS
           ========================================================================== */
        function toggleCart() {
            const drawer = document.getElementById('cart-drawer');
            const overlay = document.getElementById('cart-drawer-overlay');
            const isHidden = drawer.classList.contains('translate-x-full');

            if (isHidden) {
                drawer.classList.remove('translate-x-full');
                overlay.classList.remove('hidden');
            } else {
                drawer.classList.add('translate-x-full');
                overlay.classList.add('hidden');
            }
        }

        function toggleMobileNav() {
            const nav = document.getElementById('mobile-nav');
            nav.classList.toggle('hidden');
        }

        function toggleGithubModal() {
            const modal = document.getElementById('github-modal');
            modal.classList.toggle('hidden');
        }

        function showToast(message) {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            toast.className = 'bg-brand-card text-white text-xs font-bold px-4 py-3 rounded-xl border border-brand-orange shadow-2xl flex items-center gap-2 transform translate-y-4 opacity-0 transition-all duration-300 pointer-events-auto';
            toast.innerHTML = `<i class="fa-solid fa-circle-check text-brand-orange"></i> ${message}`;

            container.appendChild(toast);

            setTimeout(() => {
                toast.classList.remove('translate-y-4', 'opacity-0');
            }, 10);

            setTimeout(() => {
                toast.classList.add('opacity-0', '-translate-y-2');
                setTimeout(() => toast.remove(), 300);
            }, 2500);
        }
    </script>
</body>
</html>
