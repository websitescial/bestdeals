<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Best deals on Amazon products. Shop now for great discounts!">
    <title>Amazon Affiliate Store - Best Deals Online</title>
    <style>
        /* Global Styles */
        :root {
            --amazon-orange: #FF9900;
            --amazon-dark: #232F3E;
            --amazon-black: #000000;
            --amazon-white: #FFFFFF;
            --amazon-light-gray: #EAEDED;
            --amazon-text: #131921;
            --shadow: 0 2px 5px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Amazon Ember', Arial, sans-serif;
        }

        body {
            background-color: var(--amazon-light-gray);
            color: var(--amazon-text);
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* Header Styles */
        header {
            background-color: var(--amazon-dark);
            color: var(--amazon-white);
            padding: 1rem 2rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: var(--shadow);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--amazon-orange);
        }

        .logo span {
            color: var(--amazon-white);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 1.5rem;
        }

        .nav-links a {
            font-weight: 500;
            transition: var(--transition);
            padding: 0.5rem;
        }

        .nav-links a:hover {
            color: var(--amazon-orange);
            border-bottom: 2px solid var(--amazon-orange);
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            height: 60vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--amazon-white);
            padding: 0 1rem;
        }

        .hero-content {
            max-width: 800px;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        /* Search Section */
        .search-section {
            background-color: var(--amazon-white);
            padding: 2rem;
            margin: 2rem auto;
            max-width: 1200px;
            border-radius: 8px;
            box-shadow: var(--shadow);
        }

        .search-container {
            display: flex;
            justify-content: center;
        }

        .search-input {
            width: 70%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
            font-size: 1rem;
        }

        .search-btn {
            background-color: var(--amazon-orange);
            color: var(--amazon-white);
            border: none;
            padding: 0 1.5rem;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
        }

        .search-btn:hover {
            background-color: #e68a00;
        }

        /* Products Section */
        .products-section {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--amazon-dark);
            font-size: 2rem;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: var(--amazon-white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .product-image {
            height: 200px;
            width: 100%;
            object-fit: contain;
            background-color: #f7f7f7;
            padding: 1rem;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }

        .product-description {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-price {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--amazon-orange);
            margin-bottom: 1rem;
        }

        .shop-now-btn {
            display: block;
            width: 100%;
            padding: 0.8rem;
            background-color: var(--amazon-orange);
            color: var(--amazon-white);
            border: none;
            border-radius: 4px;
            font-weight: bold;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
        }

        .shop-now-btn:hover {
            background-color: #e68a00;
            transform: scale(1.02);
        }

        /* Categories Section */
        .categories-section {
            background-color: var(--amazon-dark);
            padding: 3rem 1rem;
            margin: 2rem 0;
        }

        .categories-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .categories-title {
            color: var(--amazon-white);
            text-align: center;
            margin-bottom: 2rem;
            font-size: 2rem;
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
        }

        .category-card {
            background-color: var(--amazon-white);
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            transition: var(--transition);
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .category-icon {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--amazon-orange);
        }

        .category-name {
            font-weight: bold;
            color: var(--amazon-dark);
        }

        /* Ad Overlay */
        .ad-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .ad-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .ad-container {
            background-color: var(--amazon-white);
            padding: 1rem;
            border-radius: 8px;
            max-width: 800px;
            width: 90%;
            position: relative;
        }

        .close-ad {
            position: absolute;
            top: -15px;
            right: -15px;
            background-color: var(--amazon-orange);
            color: var(--amazon-white);
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            font-weight: bold;
            border: none;
        }

        .ad-frame {
            width: 100%;
            height: 500px;
            border: none;
            border-radius: 4px;
        }

        /* Footer */
        footer {
            background-color: var(--amazon-dark);
            color: var(--amazon-white);
            padding: 3rem 1rem;
        }

        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            color: var(--amazon-orange);
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section li {
            margin-bottom: 0.8rem;
        }

        .footer-section a:hover {
            color: var(--amazon-orange);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: inline-block;
            width: 40px;
            height: 40px;
            background-color: var(--amazon-orange);
            color: var(--amazon-white);
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: var(--transition);
        }

        .social-links a:hover {
            transform: translateY(-3px);
            background-color: var(--amazon-white);
            color: var(--amazon-orange);
        }

        .copyright {
            text-align: center;
            margin-top: 2rem;
            padding-top: 1rem;
            border-top: 1px solid #444;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                background-color: var(--amazon-dark);
                width: 100%;
                flex-direction: column;
                align-items: center;
                padding: 1rem 0;
                transition: var(--transition);
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 1rem 0;
            }

            .hamburger {
                display: block;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .search-input {
                width: 100%;
            }
        }

        @media (max-width: 480px) {
            .header-container {
                padding: 1rem;
            }

            .hero {
                height: 50vh;
            }

            .hero h1 {
                font-size: 1.8rem;
            }

            .ad-container {
                width: 95%;
            }

            .ad-frame {
                height: 300px;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">Amazon<span>Affiliate</span></div>
            <div class="hamburger" id="hamburger">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#">Home</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#products">Deals</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Best Deals on Amazon Products</h1>
            <p>Shop the hottest products at discounted prices with our exclusive affiliate links</p>
            <a href="#products" class="shop-now-btn">Shop Now</a>
        </div>
    </section>

    <!-- Search Section -->
    <section class="search-section">
        <div class="search-container">
            <input type="text" class="search-input" placeholder="Search for products..." id="searchInput">
            <button class="search-btn" id="searchBtn">Search</button>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products-section" id="products">
        <h2 class="section-title">Featured Products</h2>
        <div class="products-grid" id="productsGrid">
            <!-- Products will be dynamically inserted here -->
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories-section" id="categories">
        <div class="categories-container">
            <h2 class="categories-title">Shop by Category</h2>
            <div class="categories-grid">
                <div class="category-card" data-category="electronics">
                    <div class="category-icon">
                        <i class="fas fa-laptop"></i>
                    </div>
                    <h3 class="category-name">Electronics</h3>
                </div>
                <div class="category-card" data-category="home">
                    <div class="category-icon">
                        <i class="fas fa-home"></i>
                    </div>
                    <h3 class="category-name">Home & Kitchen</h3>
                </div>
                <div class="category-card" data-category="fashion">
                    <div class="category-icon">
                        <i class="fas fa-tshirt"></i>
                    </div>
                    <h3 class="category-name">Fashion</h3>
                </div>
                <div class="category-card" data-category="beauty">
                    <div class="category-icon">
                        <i class="fas fa-spa"></i>
                    </div>
                    <h3 class="category-name">Beauty</h3>
                </div>
                <div class="category-card" data-category="sports">
                    <div class="category-icon">
                        <i class="fas fa-running"></i>
                    </div>
                    <h3 class="category-name">Sports & Outdoors</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Ad Overlay -->
    <div class="ad-overlay" id="adOverlay">
        <div class="ad-container">
            <button class="close-ad" id="closeAd">
                <i class="fas fa-times"></i>
            </button>
            <iframe class="ad-frame" id="adFrame" frameborder="0"></iframe>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-section">
                <h3>About Us</h3>
                <p>We are an Amazon Affiliate store providing the best deals on quality products from Amazon.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-pinterest"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#products">Products</a></li>
                    <li><a href="#categories">Categories</a></li>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </div>
            <div class="footer-section" id="contact">
                <h3>Contact Us</h3>
                <ul>
                    <li><i class="fas fa-map-marker-alt"></i> 123 Store St, City, Country</li>
                    <li><i class="fas fa-phone"></i> +1 234 567 890</li>
                    <li><i class="fas fa-envelope"></i> contact@amazonaffiliate.com</li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Policies</h3>
                <ul>
                    <li><a href="#">Privacy Policy</a></li>
                    <li><a href="#">Terms of Service</a></li>
                    <li><a href="#">Affiliate Disclosure</a></li>
                    <li><a href="#">Shipping Policy</a></li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 Amazon Affiliate Store. All rights reserved.</p>
            <p>This site contains affiliate links. We may earn a commission for purchases made through these links.</p>
        </div>
    </footer>

    <script>
        // Product Data - Can be replaced with JSON from an API
        // ADMIN NOTE: To add/edit products, update this array
        const products = [
            {
                id: 1,
                title: "Wireless Bluetooth Headphones",
                description: "Premium noise cancelling headphones with 30-hour battery life and deep bass.",
                price: "$79.99",
                image: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "electronics",
                affiliateLink: "https://www.amazon.com/dp/B07XRCYFBS" // Replace with your actual affiliate link
            },
            {
                id: 2,
                title: "Smart Fitness Tracker",
                description: "Track your heart rate, steps, sleep and more with this stylish fitness band.",
                price: "$49.99",
                image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "sports",
                affiliateLink: "https://www.amazon.com/dp/B07XWGWQD5" // Replace with your actual affiliate link
            },
            {
                id: 3,
                title: "Stainless Steel Water Bottle",
                description: "Keep your drinks hot or cold for hours with this durable insulated bottle.",
                price: "$24.95",
                image: "https://images.unsplash.com/photo-1602143407151-7111542de6e8?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "home",
                affiliateLink: "https://www.amazon.com/dp/B07XWGWQD6" // Replace with your actual affiliate link
            },
            {
                id: 4,
                title: "Organic Skincare Set",
                description: "Natural and cruelty-free skincare products for glowing skin.",
                price: "$39.99",
                image: "https://images.unsplash.com/photo-1571781926291-c477ebfd024b?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "beauty",
                affiliateLink: "https://www.amazon.com/dp/B07XWGWQD7" // Replace with your actual affiliate link
            },
            {
                id: 5,
                title: "Wireless Charging Pad",
                description: "Fast charging pad compatible with all Qi-enabled devices.",
                price: "$19.99",
                image: "https://images.unsplash.com/photo-1585771724684-38269d6639fd?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "electronics",
                affiliateLink: "https://www.amazon.com/dp/B07XWGWQD8" // Replace with your actual affiliate link
            },
            {
                id: 6,
                title: "Men's Running Shoes",
                description: "Lightweight and breathable running shoes with cushioned soles.",
                price: "$59.99",
                image: "https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
                category: "fashion",
                affiliateLink: "https://www.amazon.com/dp/B07XWGWQD9" // Replace with your actual affiliate link
            }
        ];

        // Configuration Variables - Easy to update
        // ADMIN NOTE: Update these values as needed
        const config = {
            adLink: "https://www.profitableratecpm.com/mxwvpffp0n?key=fc7e79075620650c6d87", // Adsterra ad link
            adDelay: 7000, // Delay in milliseconds before redirect (7000ms = 7 seconds)
            adEnabled: true // Set to false to disable ads and redirect directly
        };

        // DOM Elements
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');
        const productsGrid = document.getElementById('productsGrid');
        const searchInput = document.getElementById('searchInput');
        const searchBtn = document.getElementById('searchBtn');
        const adOverlay = document.getElementById('adOverlay');
        const closeAd = document.getElementById('closeAd');
        const adFrame = document.getElementById('adFrame');
        const categoryCards = document.querySelectorAll('.category-card');

        // Current product to redirect to after ad
        let currentProductLink = '';

        // Mobile Menu Toggle
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Display Products
        function displayProducts(productsToDisplay) {
            productsGrid.innerHTML = '';
            
            productsToDisplay.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.title}" class="product-image">
                    <div class="product-info">
                        <h3 class="product-title">${product.title}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-price">${product.price}</div>
                        <button class="shop-now-btn" data-id="${product.id}">Shop Now</button>
                    </div>
                `;
                productsGrid.appendChild(productCard);
            });

            // Add event listeners to shop now buttons
            document.querySelectorAll('.shop-now-btn').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.getAttribute('data-id'));
                    const product = products.find(p => p.id === productId);
                    if (product) {
                        currentProductLink = product.affiliateLink;
                        if (config.adEnabled) {
                            showAd();
                        } else {
                            window.open(currentProductLink, '_blank');
                        }
                    }
                });
            });
        }

        // Show Ad Overlay
        function showAd() {
            adFrame.src = config.adLink;
            adOverlay.classList.add('active');
            
            // Set timeout for automatic redirect
            setTimeout(() => {
                if (currentProductLink) {
                    window.open(currentProductLink, '_blank');
                }
                hideAd();
            }, config.adDelay);
        }

        // Hide Ad Overlay
        function hideAd() {
            adOverlay.classList.remove('active');
            adFrame.src = '';
        }

        // Close Ad Overlay
        closeAd.addEventListener('click', () => {
            hideAd();
            if (currentProductLink) {
                window.open(currentProductLink, '_blank');
            }
        });

        // Search Functionality
        function searchProducts() {
            const searchTerm = searchInput.value.toLowerCase();
            const filteredProducts = products.filter(product => 
                product.title.toLowerCase().includes(searchTerm) || 
                product.description.toLowerCase().includes(searchTerm) ||
                product.category.toLowerCase().includes(searchTerm)
            );
            displayProducts(filteredProducts);
        }

        searchBtn.addEventListener('click', searchProducts);
        searchInput.addEventListener('keyup', (e) => {
            if (e.key === 'Enter') {
                searchProducts();
            }
        });

        // Filter by Category
        categoryCards.forEach(card => {
            card.addEventListener('click', () => {
                const category = card.getAttribute('data-category');
                const filteredProducts = products.filter(product => 
                    product.category === category
                );
                displayProducts(filteredProducts);
                window.scrollTo({
                    top: document.getElementById('products').offsetTop - 100,
                    behavior: 'smooth'
                });
            });
        });

        // Initialize by displaying all products
        displayProducts(products);
    </script>
</body>
</html>
