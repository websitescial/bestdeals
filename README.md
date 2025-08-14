<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Premium Amazon Affiliate Store - Find the best products at great prices">
    <title>PrimeSelect | Premium Amazon Affiliate Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* CSS will be placed here for single-file deployment */
        :root {
            --primary: #131A22;
            --secondary: #232F3E;
            --accent: #FF9900;
            --accent-dark: #e68a00;
            --text-light: #f5f5f5;
            --text-muted: #cccccc;
            --transition: all 0.3s ease;
            --radius: 8px;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --glow: 0 0 10px rgba(255, 153, 0, 0.5);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: var(--primary);
            color: var(--text-light);
            line-height: 1.6;
        }

        /* Header Styles */
        header {
            background-color: var(--secondary);
            padding: 1rem 2rem;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 1000;
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
            font-weight: 700;
            color: var(--text-light);
            text-decoration: none;
            display: flex;
            align-items: center;
        }

        .logo span {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--accent);
            bottom: -4px;
            left: 0;
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1555529669-e69e7aa0ba9a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1600&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            align-items: center;
            text-align: center;
            padding: 0 2rem;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: var(--text-muted);
        }

        /* Search Section */
        .search-section {
            padding: 2rem;
            background-color: var(--secondary);
        }

        .search-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .search-form {
            display: flex;
            gap: 1rem;
        }

        .search-input {
            flex: 1;
            padding: 0.8rem 1rem;
            border: none;
            border-radius: var(--radius);
            font-size: 1rem;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--text-light);
        }

        .search-input:focus {
            outline: none;
            box-shadow: 0 0 0 2px var(--accent);
        }

        .search-btn {
            padding: 0.8rem 1.5rem;
            background: linear-gradient(to right, #000000, var(--accent-dark));
            color: white;
            border: none;
            border-radius: var(--radius);
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }

        .search-btn:hover {
            background: linear-gradient(to right, #000000, var(--accent));
            transform: translateY(-2px);
            box-shadow: var(--glow);
        }

        /* Products Section */
        .products {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.2rem;
            display: inline-block;
            color: var(--accent);
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 50px;
            height: 3px;
            background: var(--accent);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
        }

        .product-card {
            background-color: var(--secondary);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .product-img {
            height: 200px;
            overflow: hidden;
        }

        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .product-card:hover .product-img img {
            transform: scale(1.05);
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-title {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--text-light);
        }

        .product-desc {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-bottom: 1rem;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 1rem;
        }

        .product-btn {
            display: inline-block;
            padding: 0.7rem 1.5rem;
            background: linear-gradient(to right, #000000, var(--accent-dark));
            color: white;
            border: none;
            border-radius: var(--radius);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            cursor: pointer;
            width: 100%;
            text-align: center;
        }

        .product-btn:hover {
            background: linear-gradient(to right, #000000, var(--accent));
            box-shadow: var(--glow);
            transform: translateY(-2px);
        }

        /* Ad Overlay */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .ad-container {
            width: 90%;
            max-width: 800px;
            height: 80vh;
            background-color: var(--secondary);
            border-radius: var(--radius);
            overflow: hidden;
            position: relative;
        }

        .ad-iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        .close-ad {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            font-size: 1rem;
            z-index: 10;
            transition: var(--transition);
        }

        .close-ad:hover {
            background-color: var(--accent);
            transform: rotate(90deg);
        }

        .timer-display {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: var(--radius);
            font-size: 0.9rem;
        }

        /* Footer */
        footer {
            background-color: var(--secondary);
            padding: 3rem 2rem 1rem;
            margin-top: 3rem;
        }

        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-col h3 {
            color: var(--accent);
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }

        .footer-col p, .footer-col a {
            color: var(--text-muted);
            margin-bottom: 0.8rem;
            display: block;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-col a:hover {
            color: var(--accent);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
        }

        .social-links a:hover {
            background-color: var(--accent);
            color: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            margin-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: var(--secondary);
                flex-direction: column;
                align-items: center;
                padding-top: 2rem;
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
                font-size: 2.2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .search-form {
                flex-direction: column;
            }

            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in {
            animation: fadeIn 0.6s ease forwards;
        }

        .delay-1 { animation-delay: 0.2s; }
        .delay-2 { animation-delay: 0.4s; }
        .delay-3 { animation-delay: 0.6s; }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <a href="#" class="logo">Prime<span>Select</span></a>
            <div class="hamburger">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#categories">Categories</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content fade-in">
            <h1 class="delay-1">Premium Products Curated Just For You</h1>
            <p class="delay-2">Discover the best Amazon deals handpicked by our experts</p>
            <a href="#products" class="product-btn delay-3">Shop Now</a>
        </div>
    </section>

    <!-- Search Section -->
    <section class="search-section">
        <div class="search-container">
            <form class="search-form">
                <input type="text" class="search-input" placeholder="Search for products...">
                <button type="submit" class="search-btn">Search</button>
            </form>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="section-title">
            <h2>Featured Products</h2>
        </div>
        <div class="product-grid" id="product-grid">
            <!-- Products will be dynamically inserted here -->
        </div>
    </section>

    <!-- Ad Overlay -->
    <div class="overlay" id="adOverlay">
        <div class="ad-container">
            <button class="close-ad" id="closeAd">
                <i class="fas fa-times"></i>
            </button>
            <iframe class="ad-iframe" id="adIframe" frameborder="0"></iframe>
            <div class="timer-display" id="timerDisplay">
                Redirecting in <span id="countdown">10</span> seconds...
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-col">
                <h3>About Us</h3>
                <p>PrimeSelect is a premium Amazon affiliate store dedicated to bringing you the best products at competitive prices.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </div>
            </div>
            <div class="footer-col">
                <h3>Quick Links</h3>
                <a href="#">Home</a>
                <a href="#products">Products</a>
                <a href="#categories">Categories</a>
                <a href="#about">About</a>
                <a href="#contact">Contact</a>
            </div>
            <div class="footer-col">
                <h3>Information</h3>
                <a href="#">Privacy Policy</a>
                <a href="#">Terms & Conditions</a>
                <a href="#">Affiliate Disclosure</a>
                <a href="#">Shipping Policy</a>
            </div>
            <div class="footer-col">
                <h3>Contact Us</h3>
                <p><i class="fas fa-envelope"></i> support@primeselect.com</p>
                <p><i class="fas fa-phone"></i> +1 (555) 123-4567</p>
            </div>
        </div>
        <div class="copyright">
            <p>&copy; 2023 PrimeSelect. All Rights Reserved.</p>
            <p>As an Amazon Associate we earn from qualifying purchases.</p>
        </div>
    </footer>

    <script>
        // =============================================
        // CONFIGURATION - EDIT THESE VALUES AS NEEDED
        // =============================================

        // Adsterra Ad Link - Replace with your actual Adsterra link
        const ADSTERRA_LINK = "https://www.profitableratecpm.com/mxwvpffp0n?key=fc7e79075620650c6d87";

        // Redirect delay in seconds (5-10 seconds recommended)
        const REDIRECT_DELAY = 10;

        // Amazon Affiliate Tag - Replace with your actual Amazon affiliate tag
        const AMAZON_AFFILIATE_TAG = "yourtag-20";

        // Product Data - Add/Edit products here
        const products = [
            {
                id: 1,
                title: "Wireless Bluetooth Earbuds",
                description: "Premium sound quality with noise cancellation and 30-hour battery life. Perfect for music lovers on the go.",
                price: "$79.99",
                image: "https://images.unsplash.com/photo-1590658268037-6bf12165a8df?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "electronics"
            },
            {
                id: 2,
                title: "Smart Fitness Watch",
                description: "Track your heart rate, steps, sleep, and more with this advanced fitness smartwatch.",
                price: "$129.99",
                image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "electronics"
            },
            {
                id: 3,
                title: "Ergonomic Office Chair",
                description: "Comfortable and supportive chair designed for long hours of work with adjustable features.",
                price: "$249.99",
                image: "https://images.unsplash.com/photo-1517705008128-361805f42e86?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "home"
            },
            {
                id: 4,
                title: "Stainless Steel Water Bottle",
                description: "Keep your drinks hot or cold for hours with this durable, eco-friendly water bottle.",
                price: "$29.99",
                image: "https://images.unsplash.com/photo-1602143407151-7111542de6e8?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "home"
            },
            {
                id: 5,
                title: "Wireless Charging Station",
                description: "Charge multiple devices simultaneously with this sleek and efficient charging station.",
                price: "$49.99",
                image: "https://images.unsplash.com/photo-1583394838336-acd977736f90?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "electronics"
            },
            {
                id: 6,
                title: "Premium Coffee Maker",
                description: "Brew barista-quality coffee at home with this advanced programmable coffee maker.",
                price: "$199.99",
                image: "https://images.unsplash.com/photo-1550583724-b2692b85b150?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80",
                amazonLink: "https://www.amazon.com/dp/B08C5FWQVD/?tag=" + AMAZON_AFFILIATE_TAG,
                category: "home"
            }
        ];

        // =============================================
        // MAIN APPLICATION CODE
        // =============================================

        document.addEventListener('DOMContentLoaded', function() {
            // Mobile menu toggle
            const hamburger = document.querySelector('.hamburger');
            const navLinks = document.querySelector('.nav-links');
            
            hamburger.addEventListener('click', function() {
                navLinks.classList.toggle('active');
                hamburger.innerHTML = navLinks.classList.contains('active') ? 
                    '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
            });

            // Display products
            const productGrid = document.getElementById('product-grid');
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card fade-in';
                productCard.innerHTML = `
                    <div class="product-img">
                        <img src="${product.image}" alt="${product.title}">
                    </div>
                    <div class="product-info">
                        <h3 class="product-title">${product.title}</h3>
                        <p class="product-desc">${product.description}</p>
                        <div class="product-price">${product.price}</div>
                        <button class="product-btn" data-id="${product.id}">Shop Now</button>
                    </div>
                `;
                productGrid.appendChild(productCard);
            });

            // Ad overlay functionality
            const overlay = document.getElementById('adOverlay');
            const closeAd = document.getElementById('closeAd');
            const adIframe = document.getElementById('adIframe');
            const timerDisplay = document.getElementById('timerDisplay');
            const countdownElement = document.getElementById('countdown');
            
            let countdown;
            let redirectUrl = '';
            
            // Set up shop now buttons
            document.querySelectorAll('.product-btn').forEach(button => {
                if (button.dataset.id) {
                    button.addEventListener('click', function(e) {
                        e.preventDefault();
                        const productId = parseInt(this.dataset.id);
                        const product = products.find(p => p.id === productId);
                        
                        if (product) {
                            redirectUrl = product.amazonLink;
                            showAdOverlay();
                        }
                    });
                }
            });
            
            function showAdOverlay() {
                overlay.classList.add('active');
                adIframe.src = ADSTERRA_LINK;
                
                let secondsLeft = REDIRECT_DELAY;
                countdownElement.textContent = secondsLeft;
                
                countdown = setInterval(() => {
                    secondsLeft--;
                    countdownElement.textContent = secondsLeft;
                    
                    if (secondsLeft <= 0) {
                        clearInterval(countdown);
                        redirectToAmazon();
                    }
                }, 1000);
            }
            
            function redirectToAmazon() {
                overlay.classList.remove('active');
                window.location.href = redirectUrl;
            }
            
            closeAd.addEventListener('click', function() {
                clearInterval(countdown);
                redirectToAmazon();
            });
            
            // Search functionality
            const searchForm = document.querySelector('.search-form');
            const searchInput = document.querySelector('.search-input');
            
            searchForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const searchTerm = searchInput.value.toLowerCase();
                
                if (searchTerm.trim() === '') {
                    // If search is empty, show all products
                    document.querySelectorAll('.product-card').forEach(card => {
                        card.style.display = 'block';
                    });
                    return;
                }
                
                // Filter products
                document.querySelectorAll('.product-card').forEach(card => {
                    const title = card.querySelector('.product-title').textContent.toLowerCase();
                    const desc = card.querySelector('.product-desc').textContent.toLowerCase();
                    
                    if (title.includes(searchTerm) || desc.includes(searchTerm)) {
                        card.style.display = 'block';
                    } else {
                        card.style.display = 'none';
                    }
                });
            });
        });
    </script>
</body>
</html>
