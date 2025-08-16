<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PrimeDeals - Best Amazon Products</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #ff9900;
            --secondary: #146eb4;
            --dark: #131921;
            --light: #ffffff;
            --gray: #f3f3f3;
            --text: #333333;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Amazon Ember', Arial, sans-serif;
        }
        
        body {
            background-color: var(--gray);
            color: var(--text);
            line-height: 1.6;
        }
        
        /* Header Styles */
        header {
            background-color: var(--dark);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .header-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }
        
        .logo {
            color: var(--light);
            font-size: 24px;
            font-weight: bold;
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        
        .logo span {
            color: var(--primary);
        }
        
        .search-bar {
            flex-grow: 1;
            margin: 0 20px;
            display: flex;
        }
        
        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: none;
            border-radius: 4px 0 0 4px;
            font-size: 16px;
        }
        
        .search-bar button {
            background-color: var(--primary);
            border: none;
            padding: 10px 15px;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            color: var(--dark);
            font-weight: bold;
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
        }
        
        .social-icons a {
            color: var(--light);
            font-size: 20px;
            transition: color 0.3s;
        }
        
        .social-icons a:hover {
            color: var(--primary);
        }
        
        /* Hero Section */
        .hero {
            background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80');
            background-size: cover;
            background-position: center;
            height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--light);
            margin-bottom: 40px;
        }
        
        .hero-content {
            max-width: 800px;
            padding: 20px;
        }
        
        .hero h1 {
            font-size: 48px;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
        }
        
        /* Products Section */
        .products {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px 40px;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            font-size: 32px;
            color: var(--dark);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--primary);
            margin: 10px auto 0;
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background-color: var(--light);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .product-image {
            height: 200px;
            overflow: hidden;
            position: relative;
        }
        
        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .product-card:hover .product-image img {
            transform: scale(1.05);
        }
        
        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--primary);
            color: var(--dark);
            padding: 5px 10px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 14px;
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-title {
            font-size: 18px;
            margin-bottom: 10px;
            height: 50px;
            overflow: hidden;
        }
        
        .product-rating {
            color: var(--primary);
            margin-bottom: 10px;
            display: flex;
            align-items: center;
        }
        
        .product-rating span {
            color: var(--text);
            margin-left: 5px;
            font-size: 14px;
        }
        
        .product-price {
            font-size: 22px;
            font-weight: bold;
            color: var(--secondary);
            margin-bottom: 15px;
        }
        
        .product-price .old-price {
            text-decoration: line-through;
            font-size: 16px;
            color: #999;
            margin-left: 5px;
        }
        
        .btn {
            display: inline-block;
            padding: 10px 20px;
            background-color: var(--primary);
            color: var(--dark);
            text-decoration: none;
            border-radius: 4px;
            font-weight: bold;
            text-align: center;
            cursor: pointer;
            border: none;
            transition: background-color 0.3s;
            width: 100%;
        }
        
        .btn:hover {
            background-color: #e68a00;
        }
        
        /* Ad Modal */
        .ad-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.9);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        
        .ad-container {
            width: 90%;
            max-width: 800px;
            background-color: var(--light);
            border-radius: 8px;
            overflow: hidden;
            position: relative;
        }
        
        .ad-content {
            padding: 20px;
            text-align: center;
        }
        
        .ad-video {
            width: 100%;
            height: 450px;
            background-color: #000;
        }
        
        .skip-ad {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: rgba(0,0,0,0.5);
            color: var(--light);
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            z-index: 1001;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: var(--light);
            padding: 40px 0 20px;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
        }
        
        .footer-column h3 {
            font-size: 18px;
            margin-bottom: 20px;
            color: var(--primary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            color: var(--light);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column ul li a:hover {
            color: var(--primary);
        }
        
        .copyright {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 14px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 15px;
            }
            
            .search-bar {
                width: 100%;
                margin: 15px 0;
            }
            
            .hero h1 {
                font-size: 36px;
            }
            
            .hero p {
                font-size: 18px;
            }
            
            .ad-video {
                height: 300px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <a href="#" class="logo">Prime<span>Deals</span></a>
            
            <div class="search-bar">
                <input type="text" placeholder="Search for products...">
                <button type="submit"><i class="fas fa-search"></i></button>
            </div>
            
            <div class="social-icons">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-youtube"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
            </div>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Discover Amazing Amazon Deals</h1>
            <p>We find the best products so you don't have to. Shop our curated selection of top-rated items at unbeatable prices.</p>
        </div>
    </section>
    
    <!-- Products Section -->
    <section class="products">
        <h2 class="section-title">Featured Products</h2>
        
        <div class="products-grid">
            <!-- Product 1 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="https://m.media-amazon.com/images/I/71WkDp--uqL._AC_SL1500_.jpg" alt="Wireless Earbuds">
                    <span class="product-badge">Bestseller</span>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Wireless Earbuds, Bluetooth 5.3 Headphones with 60H Playtime</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>12,458</span>
                    </div>
                    <div class="product-price">
                        $39.99 <span class="old-price">$59.99</span>
                    </div>
                    <button class="btn shop-now" data-affiliate-link="https://www.amazon.com/dp/B0C5WK8K52/?tag=yourtag-20">Shop Now</button>
                </div>
            </div>
            
            <!-- Product 2 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="https://m.media-amazon.com/images/I/61L1ItFgFHL._AC_SL1500_.jpg" alt="Smart Watch">
                    <span class="product-badge">Trending</span>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Smart Watch for Men Women, Fitness Tracker with Heart Rate Monitor</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>8,742</span>
                    </div>
                    <div class="product-price">
                        $49.99 <span class="old-price">$79.99</span>
                    </div>
                    <button class="btn shop-now" data-affiliate-link="https://www.amazon.com/dp/B0C5R8BZGD/?tag=yourtag-20">Shop Now</button>
                </div>
            </div>
            
            <!-- Product 3 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="https://m.media-amazon.com/images/I/71geVdy6-OS._AC_SL1500_.jpg" alt="Air Fryer">
                    <span class="product-badge">Limited Deal</span>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Air Fryer, 6QT XL Capacity, 1800W Electric Hot Air Fryers Oven</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>23,156</span>
                    </div>
                    <div class="product-price">
                        $79.99 <span class="old-price">$129.99</span>
                    </div>
                    <button class="btn shop-now" data-affiliate-link="https://www.amazon.com/dp/B0C5R8BZGD/?tag=yourtag-20">Shop Now</button>
                </div>
            </div>
            
            <!-- Product 4 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="https://m.media-amazon.com/images/I/71OZY036QVL._AC_SL1500_.jpg" alt="Robot Vacuum">
                    <span class="product-badge">New</span>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Robot Vacuum and Mop Combo, Self-Charging, Wi-Fi Connected</h3>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>5,328</span>
                    </div>
                    <div class="product-price">
                        $249.99 <span class="old-price">$399.99</span>
                    </div>
                    <button class="btn shop-now" data-affiliate-link="https://www.amazon.com/dp/B0C5R8BZGD/?tag=yourtag-20">Shop Now</button>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Ad Modal -->
    <div class="ad-modal" id="adModal">
        <div class="ad-container">
            <button class="skip-ad" id="skipAd">Skip Ad</button>
            <div class="ad-video" id="adVideo">
                <!-- Adstera ad will be loaded here -->
                <div style="width:100%;height:100%;display:flex;justify-content:center;align-items:center;color:white;font-size:24px;">
                    Adstera Ad Playing... (Simulation)
                </div>
            </div>
        </div>
    </div>
    
    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-column">
                <h3>Shop</h3>
                <ul>
                    <li><a href="#">All Products</a></li>
                    <li><a href="#">Best Sellers</a></li>
                    <li><a href="#">New Arrivals</a></li>
                    <li><a href="#">Deals</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Customer Service</h3>
                <ul>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">FAQs</a></li>
                    <li><a href="#">Shipping Policy</a></li>
                    <li><a href="#">Returns</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>About Us</h3>
                <ul>
                    <li><a href="#">Our Story</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Careers</a></li>
                    <li><a href="#">Press</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Connect</h3>
                <ul>
                    <li><a href="#"><i class="fab fa-facebook"></i> Facebook</a></li>
                    <li><a href="#"><i class="fab fa-instagram"></i> Instagram</a></li>
                    <li><a href="#"><i class="fab fa-youtube"></i> YouTube</a></li>
                    <li><a href="#"><i class="fab fa-pinterest"></i> Pinterest</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 PrimeDeals. All rights reserved. As an Amazon Associate we earn from qualifying purchases.</p>
        </div>
    </footer>
    
    <script>
        // Ad Modal Functionality
        const adModal = document.getElementById('adModal');
        const skipAdBtn = document.getElementById('skipAd');
        const adVideo = document.getElementById('adVideo');
        let currentAffiliateLink = '';
        
        // Get all Shop Now buttons
        const shopNowButtons = document.querySelectorAll('.shop-now');
        
        // Add click event to each button
        shopNowButtons.forEach(button => {
            button.addEventListener('click', function() {
                // Store the affiliate link
                currentAffiliateLink = this.getAttribute('data-affiliate-link');
                
                // Show the ad modal
                adModal.style.display = 'flex';
                
                // In a real implementation, you would load the Adstera ad here
                // For simulation, we'll just set a timeout
                
                // Simulate ad play time (5 seconds)
                setTimeout(() => {
                    // After ad completes, redirect to Amazon
                    window.location.href = currentAffiliateLink;
                }, 5000);
            });
        });
        
        // Skip ad button
        skipAdBtn.addEventListener('click', function() {
            // Redirect immediately to Amazon
            window.location.href = currentAffiliateLink;
        });
        
        // Close modal if clicked outside
        adModal.addEventListener('click', function(e) {
            if (e.target === adModal) {
                window.location.href = currentAffiliateLink;
            }
        });
        
        // Search functionality
        const searchInput = document.querySelector('.search-bar input');
        const searchButton = document.querySelector('.search-bar button');
        
        searchButton.addEventListener('click', function() {
            performSearch();
        });
        
        searchInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                performSearch();
            }
        });
        
        function performSearch() {
            const searchTerm = searchInput.value.trim();
            if (searchTerm) {
                alert(`Searching for: ${searchTerm}\nIn a real implementation, this would filter products.`);
            }
        }
    </script>
</body>
</html>
