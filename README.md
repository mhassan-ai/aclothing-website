# aclothing-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MALIK_TAI | The Desi Drip</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;700&family=Teko:wght@400;600;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- VARIABLES & THEME --- */
        :root {
            /* Pakistan Flag Inspired Premium Palette */
            --primary-green: #0F5132; /* Deep Emerald */
            --primary-dark: #082f1d;
            --accent-gold: #D4AF37; /* Premium Gold */
            --bg-light: #F8F9FA;
            --white: #FFFFFF;
            --text-dark: #212529;
            --text-grey: #6C757D;
            --danger: #dc3545;
            --shadow: 0 10px 30px rgba(0,0,0,0.08);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--text-dark);
            background-color: var(--bg-light);
            overflow-x: hidden;
        }

        h1, h2, h3, h4, .brand-font {
            font-family: 'Teko', sans-serif;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        a { text-decoration: none; color: inherit; transition: var(--transition); }
        ul { list-style: none; }
        img { width: 100%; display: block; }
        button { cursor: pointer; border: none; outline: none; font-family: 'Poppins', sans-serif; }

        /* --- UTILITIES --- */
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        .section-padding { padding: 80px 0; }
        .text-center { text-align: center; }
        .flex { display: flex; align-items: center; }
        .justify-between { justify-content: space-between; }
        .grid { display: grid; gap: 30px; }
        
        .btn {
            display: inline-block;
            padding: 12px 35px;
            background-color: var(--primary-green);
            color: var(--white);
            font-weight: 600;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
            transition: var(--transition);
            clip-path: polygon(10% 0, 100% 0, 100% 80%, 90% 100%, 0 100%, 0 20%);
        }

        .btn:hover {
            background-color: var(--accent-gold);
            color: var(--primary-dark);
            transform: translateY(-2px);
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--white);
            color: var(--white);
            clip-path: polygon(10% 0, 100% 0, 100% 80%, 90% 100%, 0 100%, 0 20%);
        }

        .btn-outline:hover {
            background: var(--white);
            color: var(--primary-green);
        }

        .section-title {
            font-size: 3rem;
            margin-bottom: 10px;
            color: var(--primary-green);
            position: relative;
            display: inline-block;
        }

        /* --- HEADER --- */
        header { background: var(--white); box-shadow: var(--shadow); position: sticky; top: 0; z-index: 1000; }
        
        .top-bar {
            background: var(--primary-dark);
            color: var(--white);
            font-size: 0.8rem;
            padding: 8px 0;
            text-align: center;
        }

        .navbar { height: 80px; display: flex; justify-content: space-between; align-items: center; }

        .logo {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary-green);
            line-height: 1;
            font-family: 'Teko', sans-serif;
        }
        
        .logo span { color: var(--accent-gold); }

        .nav-links { display: flex; gap: 30px; }
        .nav-links a {
            font-weight: 500;
            font-size: 0.95rem;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--accent-gold);
            transition: var(--transition);
        }

        .nav-links a:hover::after { width: 100%; }

        .nav-icons { display: flex; gap: 20px; font-size: 1.2rem; }
        .cart-icon { position: relative; }
        .cart-count {
            position: absolute;
            top: -8px;
            right: -10px;
            background: var(--accent-gold);
            color: var(--primary-dark);
            font-size: 0.7rem;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .mobile-toggle { display: none; font-size: 1.5rem; color: var(--primary-green); }

        /* --- HERO --- */
        #hero {
            height: 90vh;
            background: linear-gradient(rgba(15, 81, 50, 0.8), rgba(8, 47, 29, 0.7)), url('https://images.unsplash.com/photo-1507680434567-5739c80be1ac?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
        }

        .hero-content h1 {
            font-size: 5rem;
            line-height: 0.9;
            margin-bottom: 20px;
            text-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .hero-content p { font-size: 1.2rem; margin-bottom: 30px; letter-spacing: 2px; }
        
        .location-selector {
            background: rgba(255,255,255,0.15);
            backdrop-filter: blur(5px);
            padding: 10px 20px;
            border-radius: 30px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 30px;
            border: 1px solid rgba(255,255,255,0.3);
        }

        /* --- COLLECTIONS --- */
        .collection-grid {
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .collection-card {
            height: 400px;
            position: relative;
            overflow: hidden;
            border-radius: 5px;
            cursor: pointer;
        }

        .collection-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .collection-card:hover img { transform: scale(1.1); }

        .collection-overlay {
            position: absolute;
            inset: 0;
            background: rgba(15, 81, 50, 0.4);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            color: var(--white);
            transition: background 0.3s;
        }

        .collection-card:hover .collection-overlay { background: rgba(15, 81, 50, 0.2); }
        .collection-overlay h3 { font-size: 2.5rem; color: var(--white); margin-bottom: 5px; }

        /* --- PRODUCTS --- */
        .filter-nav {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 8px 25px;
            border: 1px solid var(--primary-green);
            background: transparent;
            color: var(--primary-green);
            border-radius: 5px;
            font-weight: 600;
            transition: var(--transition);
        }

        .filter-btn.active, .filter-btn:hover {
            background: var(--primary-green);
            color: var(--white);
        }

        .product-grid {
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
        }

        .product-card {
            background: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            transition: var(--transition);
            position: relative;
        }

        .product-card:hover { transform: translateY(-5px); box-shadow: var(--shadow); }

        .product-img-box {
            position: relative;
            height: 320px;
            overflow: hidden;
            background: #f0f0f0;
        }

        .product-img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .product-card:hover .product-img-box img { transform: scale(1.05); }

        .tag {
            position: absolute;
            top: 10px;
            left: 10px;
            background: var(--accent-gold);
            color: var(--primary-dark);
            padding: 2px 10px;
            font-size: 0.7rem;
            font-weight: 700;
            text-transform: uppercase;
            border-radius: 3px;
        }

        .add-btn-overlay {
            position: absolute;
            bottom: -50px;
            left: 0;
            width: 100%;
            background: var(--primary-green);
            color: var(--white);
            text-align: center;
            padding: 12px;
            font-weight: 600;
            transition: bottom 0.3s ease;
            cursor: pointer;
        }

        .product-card:hover .add-btn-overlay { bottom: 0; }

        .product-details { padding: 15px; text-align: center; }
        .product-cat { font-size: 0.75rem; color: var(--text-grey); text-transform: uppercase; letter-spacing: 1px; }
        .product-name { font-size: 1rem; margin: 5px 0; font-weight: 600; }
        .product-price { color: var(--primary-green); font-weight: 700; font-size: 1.1rem; }

        /* --- ABOUT & DESI DRIP --- */
        .about-section { background: var(--white); }
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            align-items: center;
            gap: 50px;
        }
        
        .about-text h2 { color: var(--primary-green); font-size: 3rem; margin-bottom: 20px; }
        .about-text p { margin-bottom: 20px; color: var(--text-grey); line-height: 1.8; }
        
        .stat-box {
            display: flex;
            gap: 30px;
            margin-top: 30px;
        }
        .stat-item h3 { font-size: 2.5rem; color: var(--accent-gold); margin: 0; line-height: 1; }
        .stat-item p { font-size: 0.9rem; text-transform: uppercase; font-weight: 600; }

        /* --- CART SIDEBAR --- */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -400px;
            width: 380px;
            height: 100vh;
            background: var(--white);
            z-index: 2000;
            box-shadow: -5px 0 30px rgba(0,0,0,0.1);
            transition: right 0.4s ease;
            display: flex;
            flex-direction: column;
            padding: 20px;
        }

        .cart-sidebar.open { right: 0; }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #eee;
            padding-bottom: 15px;
            margin-bottom: 20px;
        }

        .cart-items { flex: 1; overflow-y: auto; }
        
        .cart-item {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
        }

        .cart-item img { width: 70px; height: 90px; object-fit: cover; border-radius: 4px; }
        
        .item-info h4 { font-size: 0.9rem; font-family: 'Poppins', sans-serif; margin-bottom: 5px; }
        .item-price { color: var(--primary-green); font-weight: 600; font-size: 0.9rem; }
        .remove-btn { color: var(--danger); font-size: 0.8rem; cursor: pointer; margin-top: 5px; display: block; }

        .cart-footer { border-top: 1px solid #eee; padding-top: 20px; }
        .total-row { display: flex; justify-content: space-between; font-size: 1.2rem; font-weight: 700; margin-bottom: 20px; color: var(--primary-green); }

        .whatsapp-btn {
            background: #25D366;
            color: white;
            width: 100%;
            padding: 12px;
            border-radius: 5px;
            font-weight: 600;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: var(--transition);
        }

        .whatsapp-btn:hover { background: #128C7E; }

        .overlay {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.6);
            z-index: 1500;
            display: none;
        }
        .overlay.active { display: block; }

        /* --- TOAST --- */
        .toast {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--primary-dark);
            color: var(--white);
            padding: 12px 25px;
            border-radius: 4px;
            z-index: 3000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .toast.show { opacity: 1; visibility: visible; bottom: 50px; }

        /* --- FOOTER --- */
        footer {
            background: var(--primary-dark);
            color: #ccc;
            padding: 60px 0 20px;
        }
        
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 { color: var(--white); font-size: 1.5rem; margin-bottom: 20px; }
        .footer-col ul li { margin-bottom: 10px; }
        .footer-col ul li a:hover { color: var(--accent-gold); padding-left: 5px; }

        .payment-icons i { font-size: 1.5rem; margin-right: 15px; color: var(--white); }
        
        .copyright {
            border-top: 1px solid rgba(255,255,255,0.1);
            text-align: center;
            padding-top: 20px;
            font-size: 0.8rem;
        }

        /* --- PAGE DISPLAY --- */
        .page-section { display: none; animation: fadeIn 0.5s ease; }
        .page-section.active { display: block; }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .navbar { padding: 0 20px; }
            .mobile-toggle { display: block; }
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: var(--white);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                transition: left 0.4s ease;
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            }
            .nav-links.active { left: 0; }
            .hero-content h1 { font-size: 3rem; }
            .about-content { grid-template-columns: 1fr; }
            .cart-sidebar { width: 90%; right: -100%; }
        }
    </style>
</head>
<body>

    <!-- Toast Notification -->
    <div id="toast" class="toast"><i class="fas fa-check-circle"></i> Added to Bag!</div>
    <div class="overlay" id="overlay" onclick="toggleCart()"></div>

    <!-- Header -->
    <header>
        <div class="top-bar">
            FREE DELIVERY IN LAHORE | KARACHI | ISLAMABAD
        </div>
        <div class="container navbar">
            <div class="logo">MALIK_<span>TAI</span></div>
            
            <nav>
                <ul class="nav-links" id="navLinks">
                    <li><a href="#" class="nav-item active" data-target="home">Home</a></li>
                    <li><a href="#" class="nav-item" data-target="shop">Collection</a></li>
                    <li><a href="#" class="nav-item" data-target="about">The Drip</a></li>
                    <li><a href="#" class="nav-item" data-target="contact">Contact</a></li>
                </ul>
            </nav>

            <div class="nav-icons">
                <i class="fas fa-search"></i>
                <div class="cart-icon" onclick="toggleCart()">
                    <i class="fas fa-shopping-bag"></i>
                    <span class="cart-count" id="cartCount">0</span>
                </div>
                <div class="mobile-toggle" onclick="toggleMenu()">
                    <i class="fas fa-bars"></i>
                </div>
            </div>
        </div>
    </header>

    <main>
        <!-- HOME SECTION -->
        <section id="home" class="page-section active">
            <div id="hero">
                <div class="hero-content">
                    <div class="location-selector">
                        <i class="fas fa-map-marker-alt"></i> <span id="cityDisplay">Shipping to Lahore</span>
                    </div>
                    <h1>DES DRIP<br>ONLY.</h1>
                    <p>Where Eastern Tradition Meets Western Street.</p>
                    <button class="btn" onclick="navigateTo('shop')">Shop The Collection</button>
                </div>
            </div>

            <section class="section-padding container">
                <div class="text-center">
                    <h2 class="section-title">Kategoris</h2>
                    <p style="color: var(--text-grey);">Curated styles for the modern Pakistani man</p>
                </div>
                <div class="grid collection-grid" style="margin-top: 40px;">
                    <div class="collection-card" onclick="filterProducts('eastern')">
                        <img src="https://images.unsplash.com/photo-1558171813-4c088753af8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Eastern">
                        <div class="collection-overlay">
                            <h3>EASTERN</h3>
                            <p>Kurtas & Shalwar Kameez</p>
                        </div>
                    </div>
                    <div class="collection-card" onclick="filterProducts('western')">
                        <img src="https://images.unsplash.com/photo-1552374196-1ab2a1c593e8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Western">
                        <div class="collection-overlay">
                            <h3>STREET</h3>
                            <p>Hoodies & Denim</p>
                        </div>
                    </div>
                    <div class="collection-card" onclick="filterProducts('fusion')">
                        <img src="https://images.unsplash.com/photo-1617137968427-85924c809a10?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Fusion">
                        <div class="collection-overlay">
                            <h3>FUSION</h3>
                            <p>Waistcoats & Modest Wear</p>
                        </div>
                    </div>
                </div>
            </section>
        </section>

        <!-- SHOP SECTION -->
        <section id="shop" class="page-section section-padding container">
            <div class="text-center">
                <h2 class="section-title">The Drop</h2>
                <p style="margin-bottom: 30px; color: var(--text-grey);">Limited stock. Sahi quality.</p>
            </div>

            <div class="filter-nav">
                <button class="filter-btn active" onclick="filterProducts('all', this)">All</button>
                <button class="filter-btn" onclick="filterProducts('eastern', this)">Eastern Drip</button>
                <button class="filter-btn" onclick="filterProducts('western', this)">Western Street</button>
                <button class="filter-btn" onclick="filterProducts('fusion', this)">Fusion</button>
            </div>

            <div class="grid product-grid" id="productGrid">
                <!-- Products injected via JS -->
            </div>
        </section>

        <!-- ABOUT SECTION -->
        <section id="about" class="page-section section-padding about-section">
            <div class="container about-content">
                <div>
                    <img src="https://images.unsplash.com/photo-1509631179647-0177331693ae?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" style="border-radius: 5px; box-shadow: 20px 20px 0 var(--accent-gold);" alt="About">
                </div>
                <div class="about-text">
                    <h2>The Story of<br>MALIK_TAI</h2>
                    <p>Started in the streets of Lahore, MALIK_TAI isn't just a brand—it's a movement. We saw a gap in the market: guys wanted to wear traditional clothes but with the swagger of modern streetwear.</p>
                    <p>We use premium fabrics sourced from Faisalabad, stitched with the precision of Karachi's tailoring, and designed for the youth of Islamabad. <strong>Desi Drip.</strong></p>
                    
                    <div class="stat-box">
                        <div class="stat-item">
                            <h3>3</h3>
                            <p>Cities</p>
                        </div>
                        <div class="stat-item">
                            <h3>10k+</h3>
                            <p>Orders</p>
                        </div>
                        <div class="stat-item">
                            <h3>100%</h3>
                            <p>Original</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- CONTACT SECTION -->
        <section id="contact" class="page-section section-padding container">
            <div class="text-center" style="margin-bottom: 40px;">
                <h2 class="section-title">Contact Us</h2>
                <p>Have questions? Hit us up.</p>
            </div>
            
            <div style="max-width: 600px; margin: 0 auto; background: var(--white); padding: 40px; border-radius: 8px; box-shadow: var(--shadow);">
                <form onsubmit="event.preventDefault(); showToast('Message Sent!');">
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 5px; font-weight: 500;">Name</label>
                        <input type="text" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 4px;" required>
                    </div>
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 5px; font-weight: 500;">Phone / WhatsApp</label>
                        <input type="text" placeholder="0300-1234567" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 4px;" required>
                    </div>
                    <div style="margin-bottom: 20px;">
                        <label style="display: block; margin-bottom: 5px; font-weight: 500;">Message</label>
                        <textarea rows="4" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 4px;"></textarea>
                    </div>
                    <button class="btn" style="width: 100%;">Send Message</button>
                </form>
                
                <div style="margin-top: 30px; text-align: center;">
                    <p><strong>Customer Care:</strong> +92 300 1234567</p>
                    <p><strong>Email:</strong> support@maliktai.pk</p>
                    <div style="margin-top: 15px; font-size: 1.5rem;">
                        <i class="fab fa-instagram" style="color: #C13584; margin: 0 10px;"></i>
                        <i class="fab fa-facebook" style="color: #1877F2; margin: 0 10px;"></i>
                        <i class="fab fa-tiktok" style="margin: 0 10px;"></i>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <div class="logo" style="color: var(--white); margin-bottom: 15px;">MALIK_<span>TAI</span></div>
                    <p>Redefining men's fashion in Pakistan. One Kurta, one Hoodie at a time.</p>
                </div>
                <div class="footer-col">
                    <h4>Quick Links</h4>
                    <ul>
                        <li><a href="#" onclick="navigateTo('home')">Home</a></li>
                        <li><a href="#" onclick="navigateTo('shop')">Shop</a></li>
                        <li><a href="#" onclick="navigateTo('about')">About</a></li>
                        <li><a href="#" onclick="navigateTo('contact')">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h4>We Accept</h4>
                    <div class="payment-icons">
                        <i class="fas fa-money-bill-wave" title="Cash on Delivery"></i>
                        <i class="fas fa-mobile-alt" title="JazzCash/EasyPaisa"></i>
                        <i class="fab fa-cc-visa" title="Visa/Card"></i>
                    </div>
                    <p style="margin-top: 10px; font-size: 0.8rem;">Cash on Delivery Available Nationwide.</p>
                </div>
            </div>
            <div class="copyright">
                &copy; 2023 MALIK_TAI. All Rights Reserved. Made in Pakistan.
            </div>
        </div>
    </footer>

    <!-- Cart Sidebar -->
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h3>Your Bag</h3>
            <i class="fas fa-times" style="cursor: pointer; font-size: 1.2rem;" onclick="toggleCart()"></i>
        </div>
        <div class="cart-items" id="cartItemsContainer">
            <!-- Items Injected Here -->
        </div>
        <div class="cart-footer">
            <div class="total-row">
                <span>Total</span>
                <span id="cartTotal">PKR 0</span>
            </div>
            <button class="whatsapp-btn" onclick="checkoutWhatsApp()">
                <i class="fab fa-whatsapp"></i> Order via WhatsApp
            </button>
            <p style="text-align: center; font-size: 0.7rem; margin-top: 10px; color: #777;">We will confirm your order details.</p>
        </div>
    </div>

    <!-- JavaScript Logic -->
    <script>
        // --- DATA ---
        const products = [
            { id: 1, name: "Black Silk Kurta", price: 4500, category: "eastern", image: "https://images.unsplash.com/photo-1589810635657-2399de990378?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 2, name: "Lahori Street Hoodie", price: 3500, category: "western", image: "https://images.unsplash.com/photo-1556905055-8f358a7a47b2?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 3, name: "Gold Embroidery Kameez", price: 5500, category: "eastern", image: "https://images.unsplash.com/photo-1594938298603-c8148c47e356?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 4, name: "Denim Jacket", price: 4200, category: "western", image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 5, name: "Fusion Waistcoat", price: 3800, category: "fusion", image: "https://images.unsplash.com/photo-1614252235316-8c857d38b5f4?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 6, name: "Oversized Graphic Tee", price: 1800, category: "western", image: "https://images.unsplash.com/photo-1583743814966-8936f5b7be1a?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 7, name: "White Cotton Kurta", price: 2500, category: "eastern", image: "https://images.unsplash.com/photo-1558171813-4c088753af8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" },
            { id: 8, name: "Cargo Joggers", price: 2900, category: "western", image: "https://images.unsplash.com/photo-1624378439575-d8705ad7ae80?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" }
        ];

        let cart = [];

        // --- NAVIGATION ---
        const navLinks = document.querySelectorAll('.nav-item');
        const sections = document.querySelectorAll('.page-section');

        function navigateTo(targetId) {
            navLinks.forEach(link => link.classList.remove('active'));
            sections.forEach(sec => sec.classList.remove('active'));
            
            document.querySelector(`[data-target="${targetId}"]`).classList.add('active');
            document.getElementById(targetId).classList.add('active');
            
            // Close mobile menu
            document.getElementById('navLinks').classList.remove('active');
            window.scrollTo(0, 0);
        }

        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                navigateTo(link.dataset.target);
            });
        });

        function toggleMenu() {
            document.getElementById('navLinks').classList.toggle('active');
        }

        // --- PRODUCT RENDERING ---
        function renderProducts(filter = 'all') {
            const grid = document.getElementById('productGrid');
            grid.innerHTML = '';

            const filtered = filter === 'all' ? products : products.filter(p => p.category === filter);

            filtered.forEach(p => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <div class="product-img-box">
                        <span class="tag">New</span>
                        <img src="${p.image}" alt="${p.name}">
                        <div class="add-btn-overlay" onclick="addToCart(${p.id})">
                            ADD TO BAG
                        </div>
                    </div>
                    <div class="product-details">
                        <div class="product-cat">${p.category}</div>
                        <div class="product-name">${p.name}</div>
                        <div class="product-price">PKR ${p.price.toLocaleString()}</div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function filterProducts(cat, btn) {
            if(btn) {
                document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
            }
            renderProducts(cat);
            if(cat !== 'all') navigateTo('shop');
        }

        // --- CART LOGIC ---
        function toggleCart() {
            const sidebar = document.getElementById('cartSidebar');
            const overlay = document.getElementById('overlay');
            sidebar.classList.toggle('open');
            overlay.classList.toggle('active');
        }

        function addToCart(id) {
            const product = products.find(p => p.id === id);
            const existing = cart.find(i => i.id === id);

            if(existing) existing.qty++;
            else cart.push({...product, qty: 1});

            updateCartUI();
            showToast(`${product.name} added to bag!`);
            
            // Auto open cart
            const sidebar = document.getElementById('cartSidebar');
            if(!sidebar.classList.contains('open')) toggleCart();
        }

        function removeFromCart(id) {
            cart = cart.filter(i => i.id !== id);
            updateCartUI();
        }

        function updateCartUI() {
            const container = document.getElementById('cartItemsContainer');
            const count = document.getElementById('cartCount');
            const total = document.getElementById('cartTotal');

            count.innerText = cart.reduce((acc, item) => acc + item.qty, 0);

            if(cart.length === 0) {
                container.innerHTML = '<p style="text-align:center; padding: 20px; color: #777;">Your bag is empty, bhai.</p>';
                total.innerText = 'PKR 0';
                return;
            }

            container.innerHTML = '';
            let totalAmount = 0;

            cart.forEach(item => {
                totalAmount += item.price * item.qty;
                const div = document.createElement('div');
                div.className = 'cart-item';
                div.innerHTML = `
                    <img src="${item.image}" alt="${item.name}">
                    <div class="item-info">
                        <h4>${item.name}</h4>
                        <div class="item-price">PKR ${item.price.toLocaleString()} x ${item.qty}</div>
                        <span class="remove-btn" onclick="removeFromCart(${item.id})">Remove</span>
                    </div>
                `;
                container.appendChild(div);
            });

            total.innerText = 'PKR ' + totalAmount.toLocaleString();
        }

        function checkoutWhatsApp() {
            if(cart.length === 0) return;
            
            let msg = "Salam Malik_TAI! I want to place an order:%0A";
            let total = 0;
            
            cart.forEach(item => {
                msg += `- ${item.name} (x${item.qty}): PKR ${item.price * item.qty}%0A`;
                total += item.price * item.qty;
            });

            msg += `%0A*Total Bill: PKR ${total}*`;
            msg += "%0A%0APlease confirm availability.";
            
            // Demo number
            window.open(`https://wa.me/923001234567?text=${msg}`, '_blank');
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            toast.innerHTML = `<i class="fas fa-check-circle"></i> ${msg}`;
            toast.classList.add('show');
            setTimeout(() => toast.classList.remove('show'), 3000);
        }

        // Initialize
        renderProducts();

        // City Selector Logic (Simple visual)
        const cities = ['Lahore', 'Karachi', 'Islamabad', 'Rawalpindi', 'Multan'];
        let currentCityIndex = 0;
        setInterval(() => {
            currentCityIndex = (currentCityIndex + 1) % cities.length;
            document.getElementById('cityDisplay').innerText = `Shipping to ${cities[currentCityIndex]}`;
        }, 3000);

    </script>
</body>
</html>
