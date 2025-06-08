# Launch.web
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alex store - Your Favorite Food, Delivered Fast!</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Google Fonts: Inter & Pacifico -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=Pacifico&display=swap" rel="stylesheet">

    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide-react@latest/dist/umd/lucide-react.js"></script>
    
    <style>
        /* Custom styles to integrate the fonts */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #FFF8F0; /* A warm, light cream background */
        }
        .font-pacifico {
            font-family: 'Pacifico', cursive;
        }
        /* Style for scroll-to-top button */
        #scrollTopBtn {
            transition: opacity 0.3s, transform 0.3s;
        }
        /* Simple animation for elements on scroll */
        .reveal-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.6s ease-out;
        }
        .reveal-on-scroll.is-visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body class="text-gray-800">

    <!-- ===== HEADER & NAVIGATION ===== -->
    <header id="header" class="bg-white/80 backdrop-blur-lg shadow-md sticky top-0 z-50 transition-all duration-300">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo -->
                <a href="#" class="flex items-center space-x-2">
                    <span class="font-pacifico text-3xl text-orange-500">GourmetGo</span>
                </a>

                <!-- Desktop Navigation -->
                <nav class="hidden lg:flex items-center space-x-8">
                    <a href="#" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-semibold">Home</a>
                    <a href="#menu" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">Menu</a>
                    <a href="#deals" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">Deals</a>
                    <a href="#about" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">About Us</a>
                </nav>

                <!-- Action Icons & Buttons -->
                <div class="flex items-center space-x-4">
                    <button class="text-gray-500 hover:text-orange-500 transition-colors duration-300">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
                    </button>
                    <a href="#" class="relative text-gray-500 hover:text-orange-500 transition-colors duration-300">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6 2 3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4z"></path><line x1="3" y1="6" x2="21" y2="6"></line><path d="M16 10a4 4 0 0 1-8 0"></path></svg>
                        <span id="cart-count" class="absolute -top-2 -right-2 bg-orange-500 text-white text-xs w-5 h-5 rounded-full flex items-center justify-center">2</span>
                    </a>
                    <button class="hidden sm:inline-block bg-orange-500 hover:bg-orange-600 text-white font-bold py-2 px-6 rounded-full transition-transform duration-300 ease-in-out transform hover:scale-105">
                        Sign In
                    </button>
                    <!-- Mobile Menu Button -->
                    <button id="mobile-menu-btn" class="lg:hidden text-gray-600 hover:text-orange-500">
                        <svg id="menu-open-icon" xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="4" x2="20" y1="12" y2="12"/><line x1="4" x2="20" y1="6" y2="6"/><line x1="4" x2="20" y1="18" y2="18"/></svg>
                        <svg id="menu-close-icon" xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="hidden"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
                    </button>
                </div>
            </div>
        </div>
        <!-- Mobile Navigation Menu -->
        <div id="mobile-menu" class="hidden lg:hidden bg-white border-t border-gray-200">
            <nav class="flex flex-col items-center space-y-4 py-6">
                <a href="#" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-semibold">Home</a>
                <a href="#menu" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">Menu</a>
                <a href="#deals" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">Deals</a>
                <a href="#about" class="text-gray-600 hover:text-orange-500 transition-colors duration-300 font-medium">About Us</a>
                <button class="sm:hidden bg-orange-500 hover:bg-orange-600 text-white font-bold py-2 px-8 rounded-full transition-transform duration-300 ease-in-out transform hover:scale-105">
                    Sign In
                </button>
            </nav>
        </div>
    </header>

    <main>
        <!-- ===== HERO SECTION ===== -->
        <section class="relative h-[calc(100vh-80px)] min-h-[500px] flex items-center">
            <div class="absolute inset-0 bg-black/50 z-10"></div>
            <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?q=80&w=2070&auto=format&fit=crop" 
                 alt="Delicious spread of food" 
                 class="absolute inset-0 w-full h-full object-cover"
                 onerror="this.onerror=null;this.src='https://placehold.co/1920x1080/fef2e2/4c2a0a?text=Gourmet+Food';">
            
            <div class="container mx-auto px-4 sm:px-6 lg:px-8 relative z-20 text-center text-white reveal-on-scroll">
                <h1 class="text-4xl md:text-6xl lg:text-7xl font-extrabold mb-4 tracking-tight" style="text-shadow: 2px 2px 8px rgba(0,0,0,0.7);">
                    Craving Something <span class="text-orange-400">Delicious?</span>
                </h1>
                <p class="text-lg md:text-xl max-w-3xl mx-auto mb-8 font-light" style="text-shadow: 1px 1px 4px rgba(0,0,0,0.7);">
                    From piping hot pizzas to sizzling steaks, get your favorite meals delivered to your doorstep, faster than ever.
                </p>
                <a href="#menu" class="bg-orange-500 hover:bg-orange-600 text-white font-bold py-4 px-10 rounded-full text-lg transition-all duration-300 ease-in-out transform hover:scale-110 shadow-lg hover:shadow-xl">
                    Explore Our Menu
                </a>
            </div>
        </section>

        <!-- ===== FEATURED CATEGORIES ===== -->
        <section id="menu" class="py-20 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12 reveal-on-scroll">
                    <h2 class="text-4xl font-bold text-gray-800">Explore by <span class="text-orange-500">Category</span></h2>
                    <p class="text-gray-500 mt-2 max-w-xl mx-auto">Find your next favorite meal from our curated selections.</p>
                </div>
                <div class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-8">
                    <!-- Category Item 1 -->
                    <div class="group text-center reveal-on-scroll">
                        <div class="relative overflow-hidden rounded-full aspect-square shadow-lg transform group-hover:scale-105 transition-transform duration-300">
                            <img src="https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?q=80&w=1981&auto=format&fit=crop" 
                                 alt="Pizza" class="w-full h-full object-cover"
                                 onerror="this.onerror=null;this.src='https://placehold.co/400x400/f87171/ffffff?text=Pizza';">
                            <div class="absolute inset-0 bg-black/30 group-hover:bg-black/10 transition-colors duration-300"></div>
                        </div>
                        <h3 class="mt-4 text-xl font-semibold text-gray-700 group-hover:text-orange-500 transition-colors">Pizza</h3>
                    </div>
                    <!-- Category Item 2 -->
                    <div class="group text-center reveal-on-scroll" style="transition-delay: 100ms;">
                        <div class="relative overflow-hidden rounded-full aspect-square shadow-lg transform group-hover:scale-105 transition-transform duration-300">
                             <img src="https://images.unsplash.com/photo-1571091718767-18b5b1457add?q=80&w=2072&auto=format&fit=crop" 
                                 alt="Burgers" class="w-full h-full object-cover"
                                 onerror="this.onerror=null;this.src='https://placehold.co/400x400/fb923c/ffffff?text=Burgers';">
                            <div class="absolute inset-0 bg-black/30 group-hover:bg-black/10 transition-colors duration-300"></div>
                        </div>
                        <h3 class="mt-4 text-xl font-semibold text-gray-700 group-hover:text-orange-500 transition-colors">Burgers</h3>
                    </div>
                    <!-- Category Item 3 -->
                    <div class="group text-center reveal-on-scroll" style="transition-delay: 200ms;">
                        <div class="relative overflow-hidden rounded-full aspect-square shadow-lg transform group-hover:scale-105 transition-transform duration-300">
                             <img src="https://images.unsplash.com/photo-1590987337625-144b09b0d61a?q=80&w=1974&auto=format&fit=crop"
                                 alt="Sushi" class="w-full h-full object-cover"
                                 onerror="this.onerror=null;this.src='https://placehold.co/400x400/fbbf24/ffffff?text=Sushi';">
                            <div class="absolute inset-0 bg-black/30 group-hover:bg-black/10 transition-colors duration-300"></div>
                        </div>
                        <h3 class="mt-4 text-xl font-semibold text-gray-700 group-hover:text-orange-500 transition-colors">Sushi</h3>
                    </div>
                    <!-- Category Item 4 -->
                    <div class="group text-center reveal-on-scroll" style="transition-delay: 300ms;">
                        <div class="relative overflow-hidden rounded-full aspect-square shadow-lg transform group-hover:scale-105 transition-transform duration-300">
                             <img src="https://images.unsplash.com/photo-1551024601-bec78aea704b?q=80&w=1964&auto=format&fit=crop" 
                                 alt="Desserts" class="w-full h-full object-cover"
                                 onerror="this.onerror=null;this.src='https://placehold.co/400x400/f472b6/ffffff?text=Desserts';">
                            <div class="absolute inset-0 bg-black/30 group-hover:bg-black/10 transition-colors duration-300"></div>
                        </div>
                        <h3 class="mt-4 text-xl font-semibold text-gray-700 group-hover:text-orange-500 transition-colors">Desserts</h3>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- ===== TRENDING PRODUCTS ===== -->
        <section class="py-20">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12 reveal-on-scroll">
                    <h2 class="text-4xl font-bold text-gray-800">This Week's <span class="text-orange-500">Bestsellers</span></h2>
                    <p class="text-gray-500 mt-2 max-w-xl mx-auto">Hand-picked by our customers. You can't go wrong with these!</p>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
                    <!-- Product Card -->
                    <div class="bg-white rounded-xl shadow-lg overflow-hidden group transform hover:-translate-y-2 transition-all duration-300 reveal-on-scroll">
                        <div class="relative">
                            <img class="w-full h-56 object-cover" src="https://images.unsplash.com/photo-1593560704563-f176a2eb61db?q=80&w=1954&auto=format&fit=crop" alt="Margherita Pizza" onerror="this.onerror=null;this.src='https://placehold.co/600x400/f87171/ffffff?text=Classic+Pizza';">
                            <div class="absolute top-3 right-3 bg-yellow-400 text-yellow-900 px-2 py-1 rounded-full text-xs font-semibold">Bestseller</div>
                        </div>
                        <div class="p-6">
                            <h3 class="font-semibold text-xl text-gray-800 mb-2">Classic Margherita</h3>
                            <p class="text-gray-500 text-sm mb-4">Fresh mozzarella, basil, and san marzano tomato sauce.</p>
                            <div class="flex items-center justify-between">
                                <span class="text-2xl font-bold text-orange-500">$12.99</span>
                                <button class="bg-gray-800 text-white w-10 h-10 rounded-full flex items-center justify-center group-hover:bg-orange-500 transition-colors duration-300">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
                                </button>
                            </div>
                        </div>
                    </div>
                    <!-- Repeat Product Card for other items -->
                    <div class="bg-white rounded-xl shadow-lg overflow-hidden group transform hover:-translate-y-2 transition-all duration-300 reveal-on-scroll" style="transition-delay: 100ms;">
                         <div class="relative">
                            <img class="w-full h-56 object-cover" src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?q=80&w=1998&auto=format&fit=crop" alt="Double Cheeseburger" onerror="this.onerror=null;this.src='https://placehold.co/600x400/fb923c/ffffff?text=Juicy+Burger';">
                        </div>
                        <div class="p-6">
                            <h3 class="font-semibold text-xl text-gray-800 mb-2">The Ultimate Burger</h3>
                            <p class="text-gray-500 text-sm mb-4">Double beef patty, cheddar, bacon, and our secret sauce.</p>
                            <div class="flex items-center justify-between">
                                <span class="text-2xl font-bold text-orange-500">$14.50</span>
                                <button class="bg-gray-800 text-white w-10 h-10 rounded-full flex items-center justify-center group-hover:bg-orange-500 transition-colors duration-300">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="bg-white rounded-xl shadow-lg overflow-hidden group transform hover:-translate-y-2 transition-all duration-300 reveal-on-scroll" style="transition-delay: 200ms;">
                         <div class="relative">
                            <img class="w-full h-56 object-cover" src="https://images.unsplash.com/photo-1579871494447-9811cf80d66c?q=80&w=2070&auto=format&fit=crop" alt="Spicy Tuna Roll" onerror="this.onerror=null;this.src='https://placehold.co/600x400/fbbf24/ffffff?text=Sushi+Platter';">
                        </div>
                        <div class="p-6">
                            <h3 class="font-semibold text-xl text-gray-800 mb-2">Spicy Tuna Roll</h3>
                            <p class="text-gray-500 text-sm mb-4">Premium tuna, spicy mayo, and cucumber, topped with roe.</p>
                            <div class="flex items-center justify-between">
                                <span class="text-2xl font-bold text-orange-500">$16.00</span>
                                <button class="bg-gray-800 text-white w-10 h-10 rounded-full flex items-center justify-center group-hover:bg-orange-500 transition-colors duration-300">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
                                </button>
                            </div>
                        </div>
                    </div>
                     <div class="bg-white rounded-xl shadow-lg overflow-hidden group transform hover:-translate-y-2 transition-all duration-300 reveal-on-scroll" style="transition-delay: 300ms;">
                         <div class="relative">
                            <img class="w-full h-56 object-cover" src="https://images.unsplash.com/photo-1621996346565-e326b20f545a?q=80&w=1964&auto=format&fit=crop" alt="Caesar Salad" onerror="this.onerror=null;this.src='https://placehold.co/600x400/4ade80/ffffff?text=Fresh+Salad';">
                        </div>
                        <div class="p-6">
                            <h3 class="font-semibold text-xl text-gray-800 mb-2">Grilled Chicken Salad</h3>
                            <p class="text-gray-500 text-sm mb-4">Crisp romaine, grilled chicken, croutons, and parmesan.</p>
                            <div class="flex items-center justify-between">
                                <span class="text-2xl font-bold text-orange-500">$11.75</span>
                                <button class="bg-gray-800 text-white w-10 h-10 rounded-full flex items-center justify-center group-hover:bg-orange-500 transition-colors duration-300">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===== DEALS SECTION ===== -->
        <section id="deals" class="py-20 bg-orange-50">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex flex-col md:flex-row items-center bg-white rounded-2xl shadow-xl overflow-hidden">
                    <div class="w-full md:w-1/2 h-64 md:h-auto reveal-on-scroll">
                        <img src="https://images.unsplash.com/photo-1606131731446-5568d87113aa?q=80&w=1964&auto=format&fit=crop" 
                             alt="Taco deal" class="w-full h-full object-cover"
                             onerror="this.onerror=null;this.src='https://placehold.co/800x600/f59e0b/ffffff?text=Special+Deal!';">
                    </div>
                    <div class="w-full md:w-1/2 p-8 md:p-12 text-center md:text-left reveal-on-scroll" style="transition-delay: 150ms;">
                        <span class="text-orange-500 font-semibold">Deal of the Day</span>
                        <h2 class="text-4xl lg:text-5xl font-bold text-gray-800 mt-2 mb-4">Taco Tuesday!</h2>
                        <p class="text-gray-600 mb-6">Get <span class="font-bold text-orange-600">50% OFF</span> on all taco orders every Tuesday. Don't miss out on this crunchy, savory goodness!</p>
                        <a href="#" class="inline-block bg-gray-800 hover:bg-black text-white font-bold py-3 px-8 rounded-full transition-all duration-300 transform hover:scale-105">
                            Claim Deal
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===== HOW IT WORKS SECTION ===== -->
        <section id="about" class="py-20 bg-white">
            <div class="container mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16 reveal-on-scroll">
                    <h2 class="text-4xl font-bold text-gray-800">Order in 3 Easy Steps</span></h2>
                    <p class="text-gray-500 mt-2 max-w-xl mx-auto">Getting your favorite food is as simple as 1, 2, 3.</p>
                </div>
                <div class="relative">
                    <!-- Dashed line for desktop -->
                    <div class="hidden lg:block absolute top-1/2 left-0 w-full h-0.5 border-t-2 border-dashed border-gray-300" style="margin-top: -1px;"></div>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-12 lg:gap-8 relative">
                        <!-- Step 1 -->
                        <div class="text-center reveal-on-scroll">
                            <div class="relative inline-block">
                                <div class="bg-orange-100 text-orange-500 w-24 h-24 rounded-full flex items-center justify-center mx-auto shadow-lg">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect width="14" height="20" x="5" y="2" rx="2" ry="2"/><path d="M12 18h.01"/></svg>
                                </div>
                            </div>
                            <h3 class="text-2xl font-semibold mt-6 mb-2">Browse & Choose</h3>
                            <p class="text-gray-500">Explore our diverse menu and pick your desired items.</p>
                        </div>
                        <!-- Step 2 -->
                        <div class="text-center reveal-on-scroll" style="transition-delay: 150ms;">
                            <div class="relative inline-block">
                                <div class="bg-orange-100 text-orange-500 w-24 h-24 rounded-full flex items-center justify-center mx-auto shadow-lg">
                                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>
                                </div>
                            </div>
                            <h3 class="text-2xl font-semibold mt-6 mb-2">Place Your Order</h3>
                            <p class="text-gray-500">Confirm your cart and securely check out in seconds.</p>
                        </div>
                        <!-- Step 3 -->
                        <div class="text-center reveal-on-scroll" style="transition-delay: 300ms;">
                             <div class="relative inline-block">
                                <div class="bg-orange-100 text-orange-500 w-24 h-24 rounded-full flex items-center justify-center mx-auto shadow-lg">
                                   <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 16.5a3.5 3.5 0 0 0-7 0"/><path d="M21.29 12.7a6.24 6.24 0 0 0-8.58-8.58 6.24 6.24 0 0 0-8.58 8.58c.52.52.99 1.05 1.41 1.59a2 2 0 0 0 2.82 0l.04-.04a2 2 0 0 1 2.82 0l.04.04a2 2 0 0 0 2.82 0l.04-.04a2 2 0 0 1 2.82 0l.04.04a2 2 0 0 0 2.82 0c.42-.54.89-1.07 1.41-1.59z"/><path d="m11.5 13.5-1-1-1 1"/></svg>
                                </div>
                            </div>
                            <h3 class="text-2xl font-semibold mt-6 mb-2">Fast Delivery</h3>
                            <p class="text-gray-500">Sit back and relax while we deliver your hot meal right to you.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- ===== FOOTER ===== -->
    <footer class="bg-gray-800 text-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12">
                <!-- About -->
                <div class="col-span-1 md:col-span-2 lg:col-span-1">
                    <a href="#" class="font-pacifico text-3xl text-orange-500 mb-4 inline-block">GourmetGo</a>
                    <p class="text-gray-400">Your one-stop shop for the most delicious food delivered with speed and care. Quality you can taste.</p>
                </div>
                <!-- Quick Links -->
                <div>
                    <h4 class="font-bold text-lg mb-4 tracking-wider">Quick Links</h4>
                    <ul class="space-y-3">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Home</a></li>
                        <li><a href="#menu" class="text-gray-400 hover:text-white transition-colors">Our Menu</a></li>
                        <li><a href="#deals" class="text-gray-400 hover:text-white transition-colors">Special Offers</a></li>
                        <li><a href="#about" class="text-gray-400 hover:text-white transition-colors">About Us</a></li>
                    </ul>
                </div>
                <!-- Legal -->
                <div>
                    <h4 class="font-bold text-lg mb-4 tracking-wider">Legal</h4>
                    <ul class="space-y-3">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Terms of Service</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Privacy Policy</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-colors">Cookie Policy</a></li>
                    </ul>
                </div>
                <!-- Newsletter -->
                <div>
                    <h4 class="font-bold text-lg mb-4 tracking-wider">Join Our Newsletter</h4>
                    <p class="text-gray-400 mb-4">Get exclusive deals and updates straight to your inbox.</p>
                    <form class="flex">
                        <input type="email" placeholder="Your Email" class="w-full rounded-l-md px-4 py-2 text-gray-800 focus:outline-none focus:ring-2 focus:ring-orange-500">
                        <button type="submit" class="bg-orange-500 hover:bg-orange-600 text-white font-bold py-2 px-4 rounded-r-md transition-colors">
                           Go
                        </button>
                    </form>
                </div>
            </div>
            <div class="mt-12 pt-8 border-t border-gray-700 flex flex-col sm:flex-row justify-between items-center">
                <p class="text-gray-500 text-sm">&copy; 2024 GourmetGo. All Rights Reserved.</p>
                <div class="flex space-x-4 mt-4 sm:mt-0">
                    <a href="#" class="text-gray-400 hover:text-white transition-colors"><svg viewBox="0 0 24 24" class="w-6 h-6" fill="currentColor"><path d="M12 2.04c-5.5 0-10 4.49-10 10.02 0 5 3.66 9.15 8.44 9.9v-7.02h-2.53v-2.89h2.53v-2.09c0-2.5 1.49-3.88 3.75-3.88 1.09 0 2.23.19 2.23.19v2.47h-1.26c-1.24 0-1.63.77-1.63 1.56v1.85h2.78l-.45 2.89h-2.33v7.02c4.78-.75 8.44-4.9 8.44-9.9C22 6.53 17.5 2.04 12 2.04z"></path></svg></a>
                    <a href="#" class="text-gray-400 hover:text-white transition-colors"><svg viewBox="0 0 24 24" class="w-6 h-6" fill="currentColor"><path d="M22.46 6c-.77.35-1.6.58-2.46.67.88-.53 1.56-1.37 1.88-2.38-.83.49-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29 0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15 0 1.49.75 2.81 1.91 3.56-.71 0-1.37-.22-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.94.07 4.28 4.28 0 0 0 4 2.98 8.52 8.52 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21 16 21 20.33 14.5 20.33 8.79c0-.19 0-.37-.01-.56.84-.6 1.56-1.36 2.14-2.23z"></path></svg></a>
                    <a href="#" class="text-gray-400 hover:text-white transition-colors"><svg viewBox="0 0 24 24" class="w-6 h-6" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm4.72 14.41c-.2.12-.46.18-.72.18-.42 0-.83-.17-1.14-.48l-2.86-2.86c-.63-.63-.63-1.65 0-2.28.63-.63 1.65-.63 2.28 0l2.86 2.86c.63.63.63 1.65 0 2.28zm-6.03-3.12c-.2.12-.46.18-.72.18-.42 0-.83-.17-1.14-.48l-2.86-2.86c-.63-.63-.63-1.65 0-2.28.63-.63 1.65-.63 2.28 0l2.86 2.86c.63.63.63 1.65 0 2.28z"></path></svg></a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Scroll to Top Button -->
    <button id="scrollTopBtn" class="fixed bottom-5 right-5 bg-orange-500 hover:bg-orange-600 text-white w-12 h-12 rounded-full flex items-center justify-center shadow-lg opacity-0 pointer-events-none transform translate-y-4">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m18 15-6-6-6 6"/></svg>
    </button>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            // --- Mobile Menu Toggle ---
            const mobileMenuBtn = document.getElementById('mobile-menu-btn');
            const mobileMenu = document.getElementById('mobile-menu');
            const menuOpenIcon = document.getElementById('menu-open-icon');
            const menuCloseIcon = document.getElementById('menu-close-icon');

            mobileMenuBtn.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
                menuOpenIcon.classList.toggle('hidden');
                menuCloseIcon.classList.toggle('hidden');
            });

            // --- Sticky Header on Scroll ---
            const header = document.getElementById('header');
            let lastScrollY = window.scrollY;
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    header.classList.add('py-2', 'h-16');
                    header.classList.remove('h-20');
                } else {
                    header.classList.remove('py-2', 'h-16');
                    header.classList.add('h-20');
                }
                lastScrollY = window.scrollY;
            });
            
            // --- Scroll-to-Top Button ---
            const scrollTopBtn = document.getElementById('scrollTopBtn');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 300) {
                    scrollTopBtn.classList.remove('opacity-0', 'pointer-events-none', 'translate-y-4');
                } else {
                    scrollTopBtn.classList.add('opacity-0', 'pointer-events-none', 'translate-y-4');
                }
            });

            scrollTopBtn.addEventListener('click', () => {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            });
            
            // --- Scroll Reveal Animation ---
            const revealElements = document.querySelectorAll('.reveal-on-scroll');
            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('is-visible');
                        observer.unobserve(entry.target);
                    }
                });
            }, {
                rootMargin: '0px 0px -50px 0px' // Trigger a little before it's fully in view
            });

            revealElements.forEach(el => {
                revealObserver.observe(el);
            });

        });
    </script>
</body>
</html>

