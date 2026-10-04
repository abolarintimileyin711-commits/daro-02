<!DOCTYPE html>
<html lang="en" class="dark scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DARO — Future of Lifestyle & Technology</title>
    
    <!-- Fonts & Icons -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,400&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        daro: {
                            bg: '#08090e',
                            card: 'rgba(18, 22, 36, 0.65)',
                            border: 'rgba(255, 255, 255, 0.08)',
                            cyan: '#00f2fe',
                            blue: '#4facfe',
                            purple: '#7f00ff',
                            glow: 'rgba(0, 242, 254, 0.15)',
                        }
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-glow': 'pulseGlow 3s ease-in-out infinite',
                        'shimmer': 'shimmer 2.5s infinite linear',
                    },
                    keyframes: {
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-15px)' },
                        },
                        pulseGlow: {
                            '0%, 100%': { opacity: '0.4' },
                            '50%': { opacity: '0.8' },
                        },
                        shimmer: {
                            '0%': { backgroundPosition: '-200% 0' },
                            '100%': { backgroundPosition: '200% 0' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Ambient Mesh Backgrounds & Glassmorphism */
        body {
            background-color: #08090e;
            color: #f1f5f9;
            overflow-x: hidden;
        }

        .ambient-mesh {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            pointer-events: none;
            background: 
                radial-gradient(circle at 15% 20%, rgba(0, 242, 254, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 85% 70%, rgba(127, 0, 255, 0.08) 0%, transparent 40%),
                radial-gradient(circle at 50% 50%, rgba(79, 172, 254, 0.04) 0%, transparent 60%);
        }

        .glass-panel {
            background: rgba(15, 18, 28, 0.6);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glass-card {
            background: rgba(20, 25, 40, 0.5);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.07);
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .glass-card:hover {
            transform: translateY(-6px);
            border-color: rgba(0, 242, 254, 0.3);
            box-shadow: 0 12px 30px -10px rgba(0, 242, 254, 0.15);
        }

        /* Gradient Text Utility */
        .text-gradient-cyan {
            background: linear-gradient(135deg, #ffffff 0%, #00f2fe 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .text-gradient-purple {
            background: linear-gradient(135deg, #00f2fe 0%, #7f00ff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Scroll Reveal Effect Styles */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #08090e;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e293b;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #00f2fe;
        }
    </style>
</head>
<body class="selection:bg-cyan-500 selection:text-black">

    <!-- Ambient Glow Layer -->
    <div class="ambient-mesh"></div>

    <!-- Sticky Glass Header -->
    <header id="main-header" class="fixed top-0 left-0 right-0 z-40 transition-all duration-300 py-5">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="glass-panel rounded-2xl px-5 py-3.5 flex items-center justify-between shadow-2xl">
                <!-- Brand Logo -->
                <a href="#" class="flex items-center space-x-3 group">
                    <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-cyan-500 via-blue-600 to-purple-600 flex items-center justify-center font-extrabold text-white text-xl tracking-tighter shadow-lg shadow-cyan-500/20 group-hover:scale-105 transition-transform">
                        D
                    </div>
                    <span class="text-2xl font-black tracking-widest text-white group-hover:text-cyan-400 transition-colors">DARO</span>
                </a>

                <!-- Desktop Navigation Links -->
                <nav class="hidden md:flex items-center space-x-8 text-sm font-medium text-slate-300">
                    <a href="#hero" class="hover:text-cyan-400 transition-colors">Home</a>
                    <a href="#categories" class="hover:text-cyan-400 transition-colors">Categories</a>
                    <a href="#featured" class="hover:text-cyan-400 transition-colors">Shop</a>
                    <a href="#collection" class="hover:text-cyan-400 transition-colors">Collection</a>
                    <a href="#why-daro" class="hover:text-cyan-400 transition-colors">About</a>
                    <a href="#footer" class="hover:text-cyan-400 transition-colors">Contact</a>
                </nav>

                <!-- Actions (Search, Cart, Mobile Toggle) -->
                <div class="flex items-center space-x-4">
                    <!-- Search Trigger Button -->
                    <button id="search-btn" class="p-2.5 rounded-xl bg-slate-800/60 hover:bg-slate-700/60 text-slate-300 hover:text-cyan-400 border border-white/5 transition-all" aria-label="Search">
                        <i class="fa-solid fa-magnifying-glass text-lg"></i>
                    </button>

                    <!-- Shopping Cart Trigger -->
                    <button id="cart-btn" class="relative p-2.5 rounded-xl bg-slate-800/60 hover:bg-slate-700/60 text-slate-300 hover:text-cyan-400 border border-white/5 transition-all" aria-label="Shopping Cart">
                        <i class="fa-solid fa-bag-shopping text-lg"></i>
                        <span id="cart-badge" class="absolute -top-1.5 -right-1.5 w-5 h-5 bg-gradient-to-r from-cyan-500 to-blue-600 text-white text-xs font-bold rounded-full flex items-center justify-center shadow-lg">0</span>
                    </button>

                    <!-- Mobile Menu Hamburger Button -->
                    <button id="mobile-menu-btn" class="md:hidden p-2.5 rounded-xl bg-slate-800/60 hover:bg-slate-700/60 text-slate-300 border border-white/5" aria-label="Toggle Navigation Menu">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden max-w-7xl mx-auto px-4 mt-2">
            <div class="glass-panel rounded-2xl p-6 flex flex-col space-y-4 text-center">
                <a href="#hero" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">Home</a>
                <a href="#categories" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">Categories</a>
                <a href="#featured" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">Shop</a>
                <a href="#collection" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">Collection</a>
                <a href="#why-daro" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">About</a>
                <a href="#footer" class="mobile-nav-link text-slate-200 hover:text-cyan-400 font-medium py-2">Contact</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero" class="relative pt-36 pb-20 md:pt-48 md:pb-32 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                
                <!-- Left Hero Text Content -->
                <div class="lg:col-span-7 space-y-8 text-center lg:text-left reveal active">
                    <div class="inline-flex items-center space-x-2 px-3.5 py-1.5 rounded-full glass-panel border border-cyan-500/30 text-xs font-semibold tracking-wider text-cyan-300 uppercase">
                        <span class="w-2 h-2 rounded-full bg-cyan-400 animate-pulse"></span>
                        <span>FUTURE OF LIFESTYLE & TECH</span>
                    </div>

                    <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold tracking-tight text-white leading-tight">
                        DISCOVER <br>
                        <span class="text-gradient-cyan">WHAT’S NEXT.</span>
                    </h1>

                    <p class="text-lg sm:text-xl text-slate-400 max-w-2xl mx-auto lg:mx-0 font-normal leading-relaxed">
                        DARO merges futuristic design, high-performance technology, luxury apparel, and daily innovations into one unified, seamless shopping experience.
                    </p>

                    <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 pt-4">
                        <a href="#featured" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-gradient-to-r from-cyan-500 via-blue-600 to-purple-600 hover:from-cyan-400 hover:to-purple-500 text-white font-bold tracking-wide shadow-lg shadow-cyan-500/25 hover:shadow-cyan-500/40 transition-all text-center flex items-center justify-center space-x-3">
                            <span>SHOP NOW</span>
                            <i class="fa-solid fa-arrow-right text-sm"></i>
                        </a>
                        <a href="#collection" class="w-full sm:w-auto px-8 py-4 rounded-xl glass-panel text-slate-200 hover:text-white hover:border-cyan-500/50 font-bold tracking-wide transition-all text-center flex items-center justify-center">
                            EXPLORE COLLECTION
                        </a>
                    </div>

                    <!-- Trust Stats -->
                    <div class="pt-8 border-t border-white/10 grid grid-cols-3 gap-4 max-w-md mx-auto lg:mx-0">
                        <div>
                            <div class="text-2xl font-black text-white">100%</div>
                            <div class="text-xs text-slate-400 uppercase tracking-wider">Original Design</div>
                        </div>
                        <div>
                            <div class="text-2xl font-black text-white">24/7</div>
                            <div class="text-xs text-slate-400 uppercase tracking-wider">Global Support</div>
                        </div>
                        <div>
                            <div class="text-2xl font-black text-white">4.9★</div>
                            <div class="text-xs text-slate-400 uppercase tracking-wider">User Rating</div>
                        </div>
                    </div>
                </div>

                <!-- Right Hero Floating Product Card -->
                <div class="lg:col-span-5 relative reveal active">
                    <div class="relative mx-auto max-w-md lg:max-w-none">
                        <!-- Background Glow Halo -->
                        <div class="absolute -inset-4 rounded-3xl bg-gradient-to-r from-cyan-500 to-purple-600 opacity-20 blur-2xl animate-pulse-glow"></div>
                        
                        <div class="relative glass-card rounded-3xl p-6 sm:p-8 overflow-hidden animate-float">
                            <div class="flex justify-between items-start mb-6">
                                <span class="px-3 py-1 bg-cyan-500/20 text-cyan-300 text-xs font-bold rounded-lg border border-cyan-500/30">FLAGSHIP CONCEPT</span>
                                <span class="text-slate-400 text-sm font-semibold">$1,299.00</span>
                            </div>

                            <div class="relative aspect-square rounded-2xl overflow-hidden mb-6 bg-slate-900/80 flex items-center justify-center group">
                                <img src="https://images.unsplash.com/photo-1622979135225-d2ba269bc1bd?w=800&q=80" alt="DARO Horizon VR" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700">
                                <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-transparent to-transparent opacity-60"></div>
                            </div>

                            <div class="space-y-2">
                                <h3 class="text-xl font-bold text-white">DARO Horizon VR Headset</h3>
                                <p class="text-sm text-slate-400">Next-generation spatial computing with 8K OLED micro-displays.</p>
                            </div>

                            <button onclick="quickAddToCart(1)" class="w-full mt-6 py-3 rounded-xl bg-white/10 hover:bg-cyan-500 hover:text-black text-white font-bold text-sm transition-all flex items-center justify-center space-x-2">
                                <i class="fa-solid fa-cart-plus"></i>
                                <span>Quick Add to Cart</span>
                            </button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Product Categories Section -->
    <section id="categories" class="py-20 relative border-t border-white/5">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 reveal">
                <h2 class="text-xs font-bold tracking-widest text-cyan-400 uppercase mb-3">CURATED CATALOG</h2>
                <p class="text-3xl sm:text-5xl font-black text-white tracking-tight">EXPLORE CATEGORIES</p>
                <p class="text-slate-400 mt-4 text-base">Select a category to filter our next-gen lineup engineered for modern living.</p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Category 1 -->
                <div onclick="filterByCategory('Smartphones')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=800&q=80" alt="Smartphones" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">01 / TECH</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Smartphones</h3>
                        <p class="text-xs text-slate-400 mt-1">Foldable OLED & Quantum Processors</p>
                    </div>
                </div>

                <!-- Category 2 -->
                <div onclick="filterByCategory('Laptops')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?w=800&q=80" alt="Laptops" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">02 / COMPUTING</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Laptops & PCs</h3>
                        <p class="text-xs text-slate-400 mt-1">Ultra-sleek titanium workstations</p>
                    </div>
                </div>

                <!-- Category 3 -->
                <div onclick="filterByCategory('Gaming')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1587829741301-dc798b83add3?w=800&q=80" alt="Gaming" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">03 / IMMERSION</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Gaming Gear</h3>
                        <p class="text-xs text-slate-400 mt-1">Tactile mechanicals & low-latency VR</p>
                    </div>
                </div>

                <!-- Category 4 -->
                <div onclick="filterByCategory('Fashion')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=800&q=80" alt="Fashion" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">04 / STYLE</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Fashion</h3>
                        <p class="text-xs text-slate-400 mt-1">Futuristic apparel & footwear</p>
                    </div>
                </div>

                <!-- Category 5 -->
                <div onclick="filterByCategory('Beauty')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1522337360788-8b13dee7a37e?w=800&q=80" alt="Beauty & Grooming" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">05 / LUXURY</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Beauty & Grooming</h3>
                        <p class="text-xs text-slate-400 mt-1">Signature scents & skincare</p>
                    </div>
                </div>

                <!-- Category 6 -->
                <div onclick="filterByCategory('Fitness')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1576243345690-4e4b79b63288?w=800&q=80" alt="Fitness" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">06 / PERFORMANCE</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Fitness</h3>
                        <p class="text-xs text-slate-400 mt-1">Biometric monitors & recovery tools</p>
                    </div>
                </div>

                <!-- Category 7 -->
                <div onclick="filterByCategory('Home')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1545454675-3531b543be5d?w=800&q=80" alt="Home Appliances" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">07 / LIVING</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Home Appliances</h3>
                        <p class="text-xs text-slate-400 mt-1">Acoustic speakers & smart home nodes</p>
                    </div>
                </div>

                <!-- Category 8 -->
                <div onclick="filterByCategory('Accessories')" class="group relative rounded-2xl overflow-hidden glass-card cursor-pointer reveal">
                    <div class="h-64 overflow-hidden relative">
                        <img src="https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=800&q=80" alt="Accessories" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700 opacity-70 group-hover:opacity-90">
                        <div class="absolute inset-0 bg-gradient-to-t from-slate-950 via-slate-950/40 to-transparent"></div>
                    </div>
                    <div class="absolute bottom-0 inset-x-0 p-6 flex flex-col justify-end">
                        <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest mb-1">08 / ESSENTIALS</span>
                        <h3 class="text-xl font-bold text-white group-hover:text-cyan-300 transition-colors">Accessories</h3>
                        <p class="text-xs text-slate-400 mt-1">Timepieces, earbuds & power cells</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products Section with Interactive Filtering -->
    <section id="featured" class="py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-12 reveal">
                <div>
                    <h2 class="text-xs font-bold tracking-widest text-cyan-400 uppercase mb-3">SELECTION 2026</h2>
                    <p class="text-3xl sm:text-5xl font-black text-white tracking-tight">FEATURED INNOVATIONS</p>
                </div>

                <!-- Filter Tabs -->
                <div class="flex items-center space-x-2 overflow-x-auto pb-2 mt-6 md:mt-0 no-scrollbar">
                    <button onclick="filterProducts('All')" class="filter-tab active-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap bg-cyan-500 text-black shadow-lg shadow-cyan-500/20" data-category="All">All Items</button>
                    <button onclick="filterProducts('Smartphones')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Smartphones">Smartphones</button>
                    <button onclick="filterProducts('Laptops')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Laptops">Laptops</button>
                    <button onclick="filterProducts('Gaming')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Gaming">Gaming</button>
                    <button onclick="filterProducts('Fashion')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Fashion">Fashion</button>
                    <button onclick="filterProducts('Fitness')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Fitness">Fitness</button>
                    <button onclick="filterProducts('Accessories')" class="filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white" data-category="Accessories">Accessories</button>
                </div>
            </div>

            <!-- Products Grid Container -->
            <div id="product-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                <!-- Injected via JavaScript -->
            </div>
        </div>
    </section>

    <!-- Special Collection Spotlight Section -->
    <section id="collection" class="py-24 relative overflow-hidden my-12 border-y border-white/5 bg-slate-950/50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                <!-- Large Dramatic Image Card -->
                <div class="lg:col-span-7 relative reveal">
                    <div class="relative rounded-3xl overflow-hidden glass-card p-2">
                        <img src="https://images.unsplash.com/photo-1508739773434-c26b3d09e071?w=1200&q=80" alt="The DARO Collection" class="w-full h-[450px] sm:h-[550px] object-cover rounded-2xl filter brightness-90">
                        <div class="absolute inset-0 bg-gradient-to-r from-slate-950/80 via-transparent to-slate-950/80 rounded-2xl"></div>
                        <div class="absolute top-8 left-8">
                            <span class="px-3.5 py-1.5 rounded-full bg-purple-500/30 text-purple-300 border border-purple-500/40 text-xs font-extrabold uppercase tracking-widest">LIMITED DROP 2026</span>
                        </div>
                    </div>
                </div>

                <!-- Text Content & Highlights -->
                <div class="lg:col-span-5 space-y-6 reveal">
                    <h2 class="text-xs font-bold tracking-widest text-cyan-400 uppercase">EXCLUSIVE CURATION</h2>
                    <h3 class="text-3xl sm:text-5xl font-black text-white leading-tight">THE DARO BLACK EDITION</h3>
                    <p class="text-slate-400 text-base leading-relaxed">
                        Crafted from aerospace-grade titanium and finished in absolute matte dark obsidian. A hyper-limited collection built for individuals who demand uncompromising precision.
                    </p>

                    <div class="space-y-4 py-4">
                        <div class="flex items-start space-x-4">
                            <div class="w-10 h-10 rounded-xl bg-cyan-500/10 border border-cyan-500/20 flex items-center justify-center text-cyan-400 flex-shrink-0">
                                <i class="fa-solid fa-atom"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-bold text-sm">Titanium Grade 5 Alloy Body</h4>
                                <p class="text-xs text-slate-400">Extreme durability with featherlight ergonomic feel.</p>
                            </div>
                        </div>

                        <div class="flex items-start space-x-4">
                            <div class="w-10 h-10 rounded-xl bg-purple-500/10 border border-purple-500/20 flex items-center justify-center text-purple-400 flex-shrink-0">
                                <i class="fa-solid fa-microchip"></i>
                            </div>
                            <div>
                                <h4 class="text-white font-bold text-sm">Neural Sync Connectivity</h4>
                                <p class="text-xs text-slate-400">Instant multi-device sync with zero latency processing.</p>
                            </div>
                        </div>
                    </div>

                    <div class="pt-4">
                        <button onclick="filterProducts('All'); document.getElementById('featured').scrollIntoView();" class="px-8 py-4 rounded-xl bg-white text-black hover:bg-cyan-400 transition-all font-black text-sm tracking-widest uppercase shadow-xl">
                            EXPLORE COLLECTION
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- "Why DARO" Section -->
    <section id="why-daro" class="py-20 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16 reveal">
                <h2 class="text-xs font-bold tracking-widest text-cyan-400 uppercase mb-3">THE DARO DIFFERENCE</h2>
                <p class="text-3xl sm:text-5xl font-black text-white tracking-tight">ENGINEERED FOR EXCELLENCE</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-5 gap-6">
                <!-- Pillar 1 -->
                <div class="glass-card rounded-2xl p-6 space-y-4 reveal">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-cyan-500/20 to-blue-500/20 text-cyan-400 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-shield-halved"></i>
                    </div>
                    <h3 class="text-white font-bold text-lg">Quality-Focused</h3>
                    <p class="text-slate-400 text-xs leading-relaxed">Every product undergoes rigorous testing to ensure durability and top tier performance.</p>
                </div>

                <!-- Pillar 2 -->
                <div class="glass-card rounded-2xl p-6 space-y-4 reveal">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-cyan-500/20 to-blue-500/20 text-cyan-400 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-compass"></i>
                    </div>
                    <h3 class="text-white font-bold text-lg">Modern Curation</h3>
                    <p class="text-slate-400 text-xs leading-relaxed">We bring technology and lifestyle together in a clean, thoughtfully designed catalog.</p>
                </div>

                <!-- Pillar 3 -->
                <div class="glass-card rounded-2xl p-6 space-y-4 reveal">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-cyan-500/20 to-blue-500/20 text-cyan-400 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-bolt"></i>
                    </div>
                    <h3 class="text-white font-bold text-lg">Effortless Flow</h3>
                    <p class="text-slate-400 text-xs leading-relaxed">Fast browsing, instant search, and intuitive checkout built directly into the core platform.</p>
                </div>

                <!-- Pillar 4 -->
                <div class="glass-card rounded-2xl p-6 space-y-4 reveal">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-cyan-500/20 to-blue-500/20 text-cyan-400 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-headset"></i>
                    </div>
                    <h3 class="text-white font-bold text-lg">Dedicated Support</h3>
                    <p class="text-slate-400 text-xs leading-relaxed">Our support team is available round-the-clock to assist with inquiries and order updates.</p>
                </div>

                <!-- Pillar 5 -->
                <div class="glass-card rounded-2xl p-6 space-y-4 reveal">
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-tr from-cyan-500/20 to-blue-500/20 text-cyan-400 flex items-center justify-center text-xl font-bold">
                        <i class="fa-solid fa-truck-fast"></i>
                    </div>
                    <h3 class="text-white font-bold text-lg">Global Express</h3>
                    <p class="text-slate-400 text-xs leading-relaxed">Tracked express shipping delivered securely directly to your doorstep worldwide.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer Section -->
    <footer id="footer" class="pt-20 pb-12 border-t border-white/10 bg-slate-950/80 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-10 pb-16 border-b border-white/10">
                <!-- Brand Info -->
                <div class="lg:col-span-2 space-y-4">
                    <div class="flex items-center space-x-3">
                        <div class="w-9 h-9 rounded-xl bg-gradient-to-tr from-cyan-500 to-purple-600 flex items-center justify-center font-extrabold text-white text-lg">D</div>
                        <span class="text-2xl font-black tracking-widest text-white">DARO</span>
                    </div>
                    <p class="text-slate-400 text-sm max-w-sm">
                        DARO is a forward-thinking lifestyle & technology brand dedicated to elevated essentials, performance tech, and timeless modern style.
                    </p>
                    <!-- Social Placeholders -->
                    <div class="flex space-x-3 pt-2">
                        <a href="#" class="w-9 h-9 rounded-lg glass-panel flex items-center justify-center text-slate-300 hover:text-cyan-400 hover:border-cyan-500/50 transition-all"><i class="fa-brands fa-x-twitter"></i></a>
                        <a href="#" class="w-9 h-9 rounded-lg glass-panel flex items-center justify-center text-slate-300 hover:text-cyan-400 hover:border-cyan-500/50 transition-all"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-9 h-9 rounded-lg glass-panel flex items-center justify-center text-slate-300 hover:text-cyan-400 hover:border-cyan-500/50 transition-all"><i class="fa-brands fa-discord"></i></a>
                        <a href="#" class="w-9 h-9 rounded-lg glass-panel flex items-center justify-center text-slate-300 hover:text-cyan-400 hover:border-cyan-500/50 transition-all"><i class="fa-brands fa-youtube"></i></a>
                    </div>
                </div>

                <!-- Quick Links -->
                <div>
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase mb-4">Quick Links</h4>
                    <ul class="space-y-2.5 text-xs text-slate-400 font-medium">
                        <li><a href="#hero" class="hover:text-cyan-400 transition-colors">Home</a></li>
                        <li><a href="#featured" class="hover:text-cyan-400 transition-colors">Shop All Products</a></li>
                        <li><a href="#categories" class="hover:text-cyan-400 transition-colors">Categories</a></li>
                        <li><a href="#collection" class="hover:text-cyan-400 transition-colors">Limited Drop</a></li>
                    </ul>
                </div>

                <!-- Customer Support -->
                <div>
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase mb-4">Customer Support</h4>
                    <ul class="space-y-2.5 text-xs text-slate-400 font-medium">
                        <li><a href="#" class="hover:text-cyan-400 transition-colors">Shipping & Delivery</a></li>
                        <li><a href="#" class="hover:text-cyan-400 transition-colors">Returns & Guarantee</a></li>
                        <li><a href="#" class="hover:text-cyan-400 transition-colors">Track Order</a></li>
                        <li><a href="#" class="hover:text-cyan-400 transition-colors">FAQs & Help Center</a></li>
                    </ul>
                </div>

                <!-- Newsletter Signup -->
                <div>
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase mb-4">Join The Insider</h4>
                    <p class="text-xs text-slate-400 mb-3">Subscribe for early release notifications and exclusive drops.</p>
                    <form onsubmit="handleNewsletter(event)" class="space-y-2">
                        <input type="email" id="newsletter-email" required placeholder="Enter your email address..." class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white placeholder-slate-500 focus:outline-none focus:border-cyan-500 transition-all">
                        <button type="submit" class="w-full py-2.5 rounded-xl bg-gradient-to-r from-cyan-500 to-blue-600 text-white font-bold text-xs uppercase tracking-wider hover:opacity-90 transition-opacity">
                            Subscribe
                        </button>
                    </form>
                </div>
            </div>

            <!-- Bottom Copyright Bar -->
            <div class="pt-8 flex flex-col sm:flex-row items-center justify-between text-xs text-slate-500 space-y-4 sm:space-y-0">
                <p>&copy; 2026 DARO Inc. All rights reserved.</p>
                <div class="flex space-x-6">
                    <a href="#" class="hover:text-slate-400 transition-colors">Privacy Policy</a>
                    <a href="#" class="hover:text-slate-400 transition-colors">Terms of Service</a>
                    <a href="#" class="hover:text-slate-400 transition-colors">Security</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Shopping Cart Drawer Overlay -->
    <div id="cart-drawer-backdrop" class="fixed inset-0 bg-slate-950/80 backdrop-blur-sm z-50 hidden transition-opacity duration-300"></div>
    <div id="cart-drawer" class="fixed top-0 right-0 bottom-0 w-full max-w-md bg-slate-900 border-l border-white/10 z-50 transform translate-x-full transition-transform duration-300 flex flex-col shadow-2xl">
        <!-- Drawer Header -->
        <div class="p-6 border-b border-white/10 flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <i class="fa-solid fa-bag-shopping text-cyan-400"></i>
                <h3 class="text-lg font-bold text-white">Your Shopping Bag</h3>
                <span id="cart-count-title" class="text-xs text-slate-400">(0 items)</span>
            </div>
            <button onclick="toggleCartDrawer(false)" class="text-slate-400 hover:text-white p-2">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
        </div>

        <!-- Cart Items Scroll Area -->
        <div id="cart-items-container" class="flex-1 overflow-y-auto p-6 space-y-4">
            <!-- Injected dynamically -->
        </div>

        <!-- Drawer Footer -->
        <div class="p-6 border-t border-white/10 bg-slate-950/60 space-y-4">
            <!-- Free Shipping Progress -->
            <div class="space-y-1">
                <div class="flex justify-between text-xs font-semibold">
                    <span id="shipping-text" class="text-slate-300">Add $150.00 for Free Shipping</span>
                    <span id="shipping-percentage" class="text-cyan-400">0%</span>
                </div>
                <div class="w-full h-1.5 bg-slate-800 rounded-full overflow-hidden">
                    <div id="shipping-bar" class="h-full bg-gradient-to-r from-cyan-500 to-blue-500 transition-all duration-300" style="width: 0%"></div>
                </div>
            </div>

            <div class="flex justify-between items-center text-lg font-bold text-white pt-2">
                <span>Subtotal</span>
                <span id="cart-subtotal">$0.00</span>
            </div>

            <button onclick="openCheckoutModal()" class="w-full py-4 rounded-xl bg-gradient-to-r from-cyan-500 via-blue-600 to-purple-600 hover:from-cyan-400 hover:to-purple-500 text-white font-bold text-sm uppercase tracking-wider shadow-lg shadow-cyan-500/20 transition-all">
                Proceed to Checkout
            </button>
        </div>
    </div>

    <!-- Product Quick View Modal -->
    <div id="quickview-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-950/80 backdrop-blur-md">
        <div class="glass-panel max-w-3xl w-full rounded-3xl p-6 sm:p-8 relative max-h-[90vh] overflow-y-auto border border-white/10 shadow-2xl">
            <button onclick="closeQuickView()" class="absolute top-6 right-6 text-slate-400 hover:text-white p-2">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>

            <div id="quickview-content" class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <!-- Dynamic Quick View Injection -->
            </div>
        </div>
    </div>

    <!-- Live Search Overlay Modal -->
    <div id="search-modal" class="fixed inset-0 z-50 hidden p-4 sm:p-8 bg-slate-950/90 backdrop-blur-lg">
        <div class="max-w-4xl mx-auto space-y-6 pt-12">
            <div class="flex items-center justify-between">
                <span class="text-xs font-bold text-cyan-400 uppercase tracking-widest">LIVE CATALOG SEARCH</span>
                <button onclick="closeSearchModal()" class="text-slate-400 hover:text-white p-2">
                    <i class="fa-solid fa-xmark text-2xl"></i>
                </button>
            </div>

            <div class="relative">
                <input type="text" id="search-input" oninput="handleSearchInput(event)" placeholder="Search products by title or category..." class="w-full px-6 py-4 rounded-2xl glass-panel text-lg text-white placeholder-slate-500 focus:outline-none focus:border-cyan-500 transition-all">
                <i class="fa-solid fa-magnifying-glass absolute right-6 top-5 text-slate-400 text-xl"></i>
            </div>

            <div id="search-results-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 max-h-[60vh] overflow-y-auto pr-2">
                <!-- Search results injected here -->
            </div>
        </div>
    </div>

    <!-- Front-End Checkout Modal -->
    <div id="checkout-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-slate-950/85 backdrop-blur-md overflow-y-auto">
        <div class="glass-panel max-w-xl w-full rounded-3xl p-6 sm:p-8 relative border border-white/10 my-8">
            <button onclick="closeCheckoutModal()" class="absolute top-6 right-6 text-slate-400 hover:text-white p-2">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>

            <div id="checkout-form-step">
                <h3 class="text-2xl font-black text-white mb-2">COMPLETE YOUR ORDER</h3>
                <p class="text-slate-400 text-xs mb-6">Enter your shipping details below to place your order with DARO.</p>

                <form onsubmit="processCheckout(event)" class="space-y-4">
                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">First Name</label>
                            <input type="text" required placeholder="Alex" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">Last Name</label>
                            <input type="text" required placeholder="Vance" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                        </div>
                    </div>

                    <div>
                        <label class="block text-xs font-semibold text-slate-300 mb-1">Email Address</label>
                        <input type="email" required placeholder="alex.vance@example.com" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                    </div>

                    <div>
                        <label class="block text-xs font-semibold text-slate-300 mb-1">Shipping Street Address</label>
                        <input type="text" required placeholder="777 Cyber Way, Suite 10" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                    </div>

                    <div class="grid grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">City</label>
                            <input type="text" required placeholder="Neo Tokyo" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-slate-300 mb-1">Postal Code</label>
                            <input type="text" required placeholder="90210" class="w-full px-3.5 py-2.5 rounded-xl glass-panel text-xs text-white focus:border-cyan-500 outline-none">
                        </div>
                    </div>

                    <div class="pt-4 border-t border-white/10 flex justify-between items-center">
                        <div>
                            <span class="block text-xs text-slate-400">Total Payable</span>
                            <span id="checkout-total-price" class="text-xl font-extrabold text-white">$0.00</span>
                        </div>
                        <button type="submit" class="px-8 py-3.5 rounded-xl bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold text-xs uppercase tracking-wider transition-all">
                            Place Order
                        </button>
                    </div>
                </form>
            </div>

            <!-- Confirmation Step (Initially Hidden) -->
            <div id="checkout-success-step" class="hidden text-center space-y-6 py-8">
                <div class="w-20 h-20 rounded-full bg-cyan-500/20 border border-cyan-500/40 text-cyan-400 flex items-center justify-center text-4xl mx-auto">
                    <i class="fa-solid fa-check"></i>
                </div>
                <h3 class="text-3xl font-black text-white">ORDER CONFIRMED</h3>
                <p class="text-slate-300 text-sm max-w-sm mx-auto">
                    Thank you for shopping with DARO. Your order <span id="confirmed-order-id" class="text-cyan-400 font-mono font-bold">#DARO-9082</span> has been placed successfully.
                </p>
                <button onclick="closeCheckoutModal()" class="px-8 py-3.5 rounded-xl bg-white text-black font-bold text-xs uppercase tracking-wider">
                    Return to Shopping
                </button>
            </div>
        </div>
    </div>

    <!-- Notification Toast System -->
    <div id="toast-container" class="fixed bottom-6 right-6 z-50 flex flex-col space-y-3 pointer-events-none"></div>

    <script>
        /* Product Database */
        const PRODUCTS = [
            {
                id: 1,
                title: "DARO Horizon VR Headset",
                category: "Gaming",
                price: 1299.00,
                rating: 4.9,
                reviews: 128,
                badge: "FLAGSHIP",
                image: "https://images.unsplash.com/photo-1622979135225-d2ba269bc1bd?w=800&q=80",
                description: "Next-generation spatial computing headset with twin 8K micro-OLED displays and zero-latency neural tracking."
            },
            {
                id: 2,
                title: "DARO Pulse Phone Ultra",
                category: "Smartphones",
                price: 1199.00,
                rating: 4.8,
                reviews: 94,
                badge: "NEW",
                image: "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=800&q=80",
                description: "Seamless foldable smartphone with Quantum Silicon chip, edge-to-edge curved screen, and glass titanium chassis."
            },
            {
                id: 3,
                title: "DARO Book Pro Workstation",
                category: "Laptops",
                price: 2499.00,
                rating: 5.0,
                reviews: 210,
                badge: "BESTSELLER",
                image: "https://images.unsplash.com/photo-1517336714731-489689fd1ca8?w=800&q=80",
                description: "Featherlight titanium laptop engineered with 128GB unified neural memory and 22-hour battery lifecycle."
            },
            {
                id: 4,
                title: "DARO Chrono Titan Watch",
                category: "Accessories",
                price: 499.00,
                rating: 4.7,
                reviews: 86,
                badge: "TRENDING",
                image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?w=800&q=80",
                description: "Biometric smartwatch with continuous hydration monitoring, sapphire glass face, and cellular independence."
            },
            {
                id: 5,
                title: "DARO Stealth Matrix Sneakers",
                category: "Fashion",
                price: 280.00,
                rating: 4.6,
                reviews: 62,
                badge: "LIMITED",
                image: "https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=800&q=80",
                description: "Self-cushioning kinetic footwear created with recycled carbon fibers and adaptive arch support technology."
            },
            {
                id: 6,
                title: "DARO CyberBlade RGB Keyboard",
                category: "Gaming",
                price: 199.00,
                rating: 4.9,
                reviews: 145,
                badge: "NEW",
                image: "https://images.unsplash.com/photo-1587829741301-dc798b83add3?w=800&q=80",
                description: "Hall-effect magnetic key switches with customizable actuation distance and solid aluminum unibody."
            },
            {
                id: 7,
                title: "DARO Essence Obsidian Perfume",
                category: "Beauty",
                price: 150.00,
                rating: 4.8,
                reviews: 49,
                badge: "EXCLUSIVE",
                image: "https://images.unsplash.com/photo-1522337360788-8b13dee7a37e?w=800&q=80",
                description: "A bold luxury fragrance blending rare dark amber, bergamot, smoke notes, and futuristic synthetic accords."
            },
            {
                id: 8,
                title: "DARO Core Smart Fitness Roller",
                category: "Fitness",
                price: 220.00,
                rating: 4.7,
                reviews: 38,
                badge: "HOT",
                image: "https://images.unsplash.com/photo-1576243345690-4e4b79b63288?w=800&q=80",
                description: "High-frequency vibrating massage roller with real-time muscle recovery feedback via mobile connectivity."
            },
            {
                id: 9,
                title: "DARO Aura Spatial Smart Speaker",
                category: "Home",
                price: 349.00,
                rating: 4.9,
                reviews: 112,
                badge: "POPULAR",
                image: "https://images.unsplash.com/photo-1545454675-3531b543be5d?w=800&q=80",
                description: "360-degree acoustic room calibration speaker with lossless wireless streaming and dynamic mood illumination."
            },
            {
                id: 10,
                title: "DARO Obsidian Cyber Hoodie",
                category: "Fashion",
                price: 180.00,
                rating: 4.5,
                reviews: 73,
                badge: "ESSENTIAL",
                image: "https://images.unsplash.com/photo-1556905055-8f358a7a47b2?w=800&q=80",
                description: "Heavyweight organic cotton hoodie with waterproof thermal lining and subtle reflective branding."
            },
            {
                id: 11,
                title: "DARO SoundSphere ANC Earbuds",
                category: "Accessories",
                price: 249.00,
                rating: 4.8,
                reviews: 167,
                badge: "BESTSELLER",
                image: "https://images.unsplash.com/photo-1590658268037-6bf12165a8df?w=800&q=80",
                description: "Active noise canceling earbuds with spatial audio tracking, clear-call mics, and 30-hour total battery playback."
            }
        ];

        /* Application State */
        let cart = [];
        let activeCategoryFilter = "All";

        // Load cart from LocalStorage on load
        function initCart() {
            const savedCart = localStorage.getItem('daro_cart');
            if (savedCart) {
                try {
                    cart = JSON.parse(savedCart);
                } catch(e) {
                    cart = [];
                }
            }
            updateCartUI();
        }

        function saveCart() {
            localStorage.setItem('daro_cart', JSON.stringify(cart));
            updateCartUI();
        }

        function quickAddToCart(productId) {
            const product = PRODUCTS.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    id: product.id,
                    title: product.title,
                    price: product.price,
                    image: product.image,
                    quantity: 1
                });
            }

            saveCart();
            showToast(`Added "${product.title}" to your bag.`);
        }

        function updateQuantity(productId, delta) {
            const item = cart.find(i => i.id === productId);
            if (!item) return;

            item.quantity += delta;
            if (item.quantity <= 0) {
                cart = cart.filter(i => i.id !== productId);
            }
            saveCart();
        }

        function removeFromCart(productId) {
            cart = cart.filter(i => i.id !== productId);
            saveCart();
            showToast("Item removed from bag.");
        }

        function updateCartUI() {
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);

            // Update Header Cart Badge
            document.getElementById('cart-badge').textContent = totalItems;
            document.getElementById('cart-count-title').textContent = `(${totalItems} items)`;

            // Render Items in Drawer
            const container = document.getElementById('cart-items-container');
            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-12 space-y-3">
                        <i class="fa-solid fa-bag-shopping text-4xl text-slate-700"></i>
                        <p class="text-slate-400 text-sm">Your shopping bag is empty.</p>
                    </div>
                `;
            } else {
                container.innerHTML = cart.map(item => `
                    <div class="glass-card rounded-2xl p-4 flex items-center space-x-4">
                        <img src="${item.image}" alt="${item.title}" class="w-16 h-16 rounded-xl object-cover bg-slate-900">
                        <div class="flex-1 min-w-0">
                            <h4 class="text-sm font-bold text-white truncate">${item.title}</h4>
                            <p class="text-xs text-cyan-400 font-semibold mt-0.5">$${item.price.toFixed(2)}</p>
                            
                            <div class="flex items-center space-x-3 mt-2">
                                <button onclick="updateQuantity(${item.id}, -1)" class="w-6 h-6 rounded-md glass-panel flex items-center justify-center text-xs text-slate-300 hover:text-white">-</button>
                                <span class="text-xs font-bold text-white">${item.quantity}</span>
                                <button onclick="updateQuantity(${item.id}, 1)" class="w-6 h-6 rounded-md glass-panel flex items-center justify-center text-xs text-slate-300 hover:text-white">+</button>
                            </div>
                        </div>
                        <button onclick="removeFromCart(${item.id})" class="text-slate-500 hover:text-red-400 p-2 transition-colors">
                            <i class="fa-solid fa-trash-can text-sm"></i>
                        </button>
                    </div>
                `).join('');
            }

            // Subtotal
            document.getElementById('cart-subtotal').textContent = `$${subtotal.toFixed(2)}`;
            document.getElementById('checkout-total-price').textContent = `$${subtotal.toFixed(2)}`;

            // Free Shipping Bar Progress ($150 target)
            const freeShippingThreshold = 150;
            const progress = Math.min(100, (subtotal / freeShippingThreshold) * 100);
            document.getElementById('shipping-bar').style.width = `${progress}%`;
            document.getElementById('shipping-percentage').textContent = `${Math.round(progress)}%`;

            if (subtotal >= freeShippingThreshold) {
                document.getElementById('shipping-text').textContent = "You unlocked FREE express shipping!";
            } else {
                const diff = freeShippingThreshold - subtotal;
                document.getElementById('shipping-text').textContent = `Add $${diff.toFixed(2)} for Free Shipping`;
            }
        }

        /* Render Featured Product Cards */
        function renderProducts(category = "All") {
            const grid = document.getElementById('product-grid');
            const filtered = category === "All" ? PRODUCTS : PRODUCTS.filter(p => p.category === category);

            grid.innerHTML = filtered.map(p => `
                <div class="glass-card rounded-3xl p-5 flex flex-col justify-between group reveal">
                    <div>
                        <!-- Product Image & Badges -->
                        <div class="relative aspect-square rounded-2xl overflow-hidden bg-slate-900/80 mb-4 flex items-center justify-center">
                            <img src="${p.image}" alt="${p.title}" class="w-full h-full object-cover group-hover:scale-108 transition-transform duration-500">
                            <span class="absolute top-3 left-3 px-2.5 py-1 rounded-lg bg-slate-950/70 backdrop-blur-md text-cyan-300 border border-cyan-500/20 text-[10px] font-extrabold uppercase tracking-wider">
                                ${p.badge}
                            </span>
                            
                            <!-- Quick View Overlay Button -->
                            <button onclick="openQuickView(${p.id})" class="absolute bottom-3 right-3 p-2.5 rounded-xl glass-panel text-white opacity-0 group-hover:opacity-100 transition-opacity hover:bg-cyan-500 hover:text-black">
                                <i class="fa-solid fa-eye text-xs"></i>
                            </button>
                        </div>

                        <!-- Info -->
                        <div class="space-y-1 mb-4">
                            <div class="flex items-center justify-between text-xs">
                                <span class="text-slate-400">${p.category}</span>
                                <span class="text-amber-400 font-semibold"><i class="fa-solid fa-star text-[10px] mr-1"></i>${p.rating}</span>
                            </div>
                            <h3 class="text-base font-bold text-white group-hover:text-cyan-300 transition-colors truncate">${p.title}</h3>
                            <p class="text-xs text-slate-400 line-clamp-2">${p.description}</p>
                        </div>
                    </div>

                    <!-- Price & CTA -->
                    <div class="pt-3 border-t border-white/5 flex items-center justify-between">
                        <span class="text-lg font-black text-white">$${p.price.toFixed(2)}</span>
                        <button onclick="quickAddToCart(${p.id})" class="px-3.5 py-2 rounded-xl bg-cyan-500/10 hover:bg-cyan-500 text-cyan-400 hover:text-black font-bold text-xs border border-cyan-500/30 transition-all flex items-center space-x-1.5">
                            <i class="fa-solid fa-plus text-[10px]"></i>
                            <span>Add</span>
                        </button>
                    </div>
                </div>
            `).join('');

            // Re-trigger reveal animations for new items
            observeScrollReveals();
        }

        /* Filter Tab Handler */
        function filterProducts(category) {
            activeCategoryFilter = category;
            
            // Highlight Tab Buttons
            document.querySelectorAll('.filter-tab').forEach(tab => {
                if (tab.getAttribute('data-category') === category) {
                    tab.className = "filter-tab active-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap bg-cyan-500 text-black shadow-lg shadow-cyan-500/20";
                } else {
                    tab.className = "filter-tab px-4 py-2 rounded-xl text-xs font-bold transition-all whitespace-nowrap glass-panel text-slate-300 hover:text-white";
                }
            });

            renderProducts(category);
        }

        function filterByCategory(cat) {
            document.getElementById('featured').scrollIntoView({ behavior: 'smooth' });
            filterProducts(cat);
        }

        /* Drawer Controllers */
        function toggleCartDrawer(open) {
            const drawer = document.getElementById('cart-drawer');
            const backdrop = document.getElementById('cart-drawer-backdrop');

            if (open) {
                backdrop.classList.remove('hidden');
                drawer.classList.remove('translate-x-full');
            } else {
                backdrop.classList.add('hidden');
                drawer.classList.add('translate-x-full');
            }
        }

        /* Quick View Modal */
        function openQuickView(productId) {
            const p = PRODUCTS.find(item => item.id === productId);
            if (!p) return;

            const modal = document.getElementById('quickview-modal');
            const content = document.getElementById('quickview-content');

            content.innerHTML = `
                <div class="aspect-square rounded-2xl overflow-hidden bg-slate-900">
                    <img src="${p.image}" alt="${p.title}" class="w-full h-full object-cover">
                </div>
                <div class="flex flex-col justify-between space-y-4">
                    <div class="space-y-2">
                        <span class="px-2.5 py-1 rounded-lg bg-cyan-500/20 text-cyan-300 text-xs font-bold uppercase tracking-wider">${p.category}</span>
                        <h3 class="text-2xl font-black text-white mt-1">${p.title}</h3>
                        <div class="flex items-center space-x-2 text-xs text-slate-400">
                            <span class="text-amber-400 font-bold">★ ${p.rating}</span>
                            <span>•</span>
                            <span>${p.reviews} Verified Reviews</span>
                        </div>
                        <p class="text-sm text-slate-300 pt-2 leading-relaxed">${p.description}</p>
                    </div>

                    <div class="space-y-4 pt-4 border-t border-white/10">
                        <div class="flex items-center justify-between">
                            <span class="text-xs text-slate-400 uppercase font-semibold">Unit Price</span>
                            <span class="text-2xl font-black text-white">$${p.price.toFixed(2)}</span>
                        </div>

                        <button onclick="quickAddToCart(${p.id}); closeQuickView();" class="w-full py-3.5 rounded-xl bg-gradient-to-r from-cyan-500 to-blue-600 hover:from-cyan-400 hover:to-blue-500 text-white font-bold text-xs uppercase tracking-wider shadow-lg shadow-cyan-500/20 transition-all">
                            Add To Bag
                        </button>
                    </div>
                </div>
            `;

            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeQuickView() {
            const modal = document.getElementById('quickview-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        /* Search Overlay Modal */
        function openSearchModal() {
            const modal = document.getElementById('search-modal');
            modal.classList.remove('hidden');
            document.getElementById('search-input').focus();
            handleSearchInput();
        }

        function closeSearchModal() {
            document.getElementById('search-modal').classList.add('hidden');
        }

        function handleSearchInput(e) {
            const query = e ? e.target.value.toLowerCase().trim() : '';
            const grid = document.getElementById('search-results-grid');

            const matches = PRODUCTS.filter(p => 
                p.title.toLowerCase().includes(query) || 
                p.category.toLowerCase().includes(query)
            );

            if (matches.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-8">
                        <p class="text-slate-400 text-sm">No products found matching "${query}".</p>
                    </div>
                `;
            } else {
                grid.innerHTML = matches.map(p => `
                    <div onclick="openQuickView(${p.id}); closeSearchModal();" class="glass-card rounded-2xl p-3 flex items-center space-x-3 cursor-pointer hover:border-cyan-500/40">
                        <img src="${p.image}" class="w-12 h-12 rounded-xl object-cover">
                        <div class="min-w-0 flex-1">
                            <h4 class="text-xs font-bold text-white truncate">${p.title}</h4>
                            <span class="text-[10px] text-cyan-400">$${p.price.toFixed(2)}</span>
                        </div>
                    </div>
                `).join('');
            }
        }

        /* Checkout Modal */
        function openCheckoutModal() {
            if (cart.length === 0) {
                showToast("Your bag is empty. Add items first!");
                return;
            }
            toggleCartDrawer(false);
            document.getElementById('checkout-form-step').classList.remove('hidden');
            document.getElementById('checkout-success-step').classList.add('hidden');
            document.getElementById('checkout-modal').classList.remove('hidden');
            document.getElementById('checkout-modal').classList.add('flex');
        }

        function closeCheckoutModal() {
            const modal = document.getElementById('checkout-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        function processCheckout(e) {
            e.preventDefault();
            // Generate dummy order ID
            const orderId = '#DARO-' + Math.floor(1000 + Math.random() * 9000);
            document.getElementById('confirmed-order-id').textContent = orderId;

            // Clear Cart
            cart = [];
            saveCart();

            // Toggle Step View
            document.getElementById('checkout-form-step').classList.add('hidden');
            document.getElementById('checkout-success-step').classList.remove('hidden');
        }

        /* Newsletter Submit */
        function handleNewsletter(e) {
            e.preventDefault();
            const emailInput = document.getElementById('newsletter-email');
            showToast("Thank you for subscribing to DARO Insider!");
            emailInput.value = '';
        }

        /* Toast Notification Helper */
        function showToast(message) {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            toast.className = 'glass-panel rounded-xl px-4 py-3 text-xs font-semibold text-white border border-cyan-500/30 shadow-2xl flex items-center space-x-2 pointer-events-auto transform translate-y-2 opacity-0 transition-all duration-300';
            toast.innerHTML = `<i class="fa-solid fa-circle-check text-cyan-400"></i><span>${message}</span>`;
            
            container.appendChild(toast);

            setTimeout(() => {
                toast.classList.remove('translate-y-2', 'opacity-0');
            }, 10);

            setTimeout(() => {
                toast.classList.add('opacity-0', 'translate-y-2');
                setTimeout(() => toast.remove(), 300);
            }, 3000);
        }

        /* IntersectionObserver Scroll Reveals */
        function observeScrollReveals() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, { threshold: 0.1 });

            document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
        }

        /* Header Dynamic Backdrop on Scroll */
        window.addEventListener('scroll', () => {
            const header = document.getElementById('main-header');
            if (window.scrollY > 40) {
                header.classList.add('py-3');
                header.classList.remove('py-5');
            } else {
                header.classList.add('py-5');
                header.classList.remove('py-3');
            }
        });

        /* DOM Content Loaded Initializer */
        document.addEventListener('DOMContentLoaded', () => {
            initCart();
            renderProducts();
            observeScrollReveals();

            // Register Event Listeners
            document.getElementById('cart-btn').addEventListener('click', () => toggleCartDrawer(true));
            document.getElementById('cart-drawer-backdrop').addEventListener('click', () => toggleCartDrawer(false));
            document.getElementById('search-btn').addEventListener('click', openSearchModal);

            // Mobile menu toggle
            const mobileBtn = document.getElementById('mobile-menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');
            mobileBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });

            document.querySelectorAll('.mobile-nav-link').forEach(link => {
                link.addEventListener('click', () => {
                    mobileMenu.classList.add('hidden');
                });
            });
        });
    </script>
</body>
</html>