<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Premium Amazon Affiliate Store - Trending Products, Deals & More!">
  <title>PrimePicksHub - Amazon Affiliate Store</title>
  
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  
  <style>
    /* RESET */
    * { margin:0; padding:0; box-sizing:border-box; font-family: 'Roboto', sans-serif; }
    body { background: #f9f9f9; color: #000; }

    /* HEADER */
    header {
      background: #fff;
      padding: 15px 50px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    header .logo { font-size: 24px; font-weight: 700; color: #146EB4; }
    nav a {
      text-decoration: none;
      color: #146EB4;
      margin-left: 20px;
      font-weight: 500;
    }
    nav a:hover { color: #FF9900; }

    /* HERO */
    .hero {
      background: linear-gradient(to right, #FF9900, #146EB4);
      color: #fff;
      text-align: center;
      padding: 80px 20px;
    }
    .hero h1 { font-size: 48px; margin-bottom: 20px; }
    .hero p { font-size: 20px; margin-bottom: 30px; }
    .hero button {
      background: #FF9900;
      color: #fff;
      border: none;
      padding: 15px 30px;
      font-size: 18px;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .hero button:hover { background: #146EB4; }

    /* SEARCH */
    .search-bar {
      max-width: 600px;
      margin: 30px auto;
      display: flex;
      justify-content: center;
    }
    .search-bar input {
      width: 100%;
      padding: 10px 15px;
      border-radius: 5px 0 0 5px;
      border: 1px solid #ccc;
      outline: none;
      font-size: 16px;
    }
    .search-bar button {
      padding: 10px 15px;
      border: none;
      background: #FF9900;
      color: #fff;
      font-size: 16px;
      cursor: pointer;
      border-radius: 0 5px 5px 0;
      transition: all 0.3s ease;
    }
    .search-bar button:hover { background: #146EB4; }

    /* PRODUCT GRID */
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      padding: 20px 50px;
    }
    .product-card {
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      overflow: hidden;
      transition: all 0.3s ease;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .product-card:hover { transform: scale(1.05); box-shadow: 0 5px 20px rgba(0,0,0,0.2); }
    .product-card img { width: 100%; object-fit: cover; }
    .product-card .content { padding: 15px; }
    .product-card h3 { color: #146EB4; margin-bottom: 10px; }
    .product-card p { font-size: 14px; margin-bottom: 10px; }
    .product-card .price { font-weight: bold; margin-bottom: 10px; }
    .product-card button {
      background: #FF9900;
      color: #fff;
      border: none;
      padding: 10px;
      width: 100%;
      border-radius: 5px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    .product-card button:hover { background: #146EB4; }

    /* FOOTER */
    footer {
      background: #fff;
      padding: 40px 50px;
      margin-top: 50px;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      box-shadow: 0 -2px 5px rgba(0,0,0,0.1);
    }
    footer div { margin-bottom: 20px; }
    footer h4 { color: #146EB4; margin-bottom: 10px; }
    footer a { text-decoration: none; color: #146EB4; }
    footer a:hover { color: #FF9900; }

    /* POPUP AD */
    .ad-popup {
      position: fixed;
      top:0; left:0;
      width:100%; height:100%;
      background: rgba(0,0,0,0.7);
      display: flex;
      align-items: center;
      justify-content: center;
      visibility: hidden;
      opacity: 0;
      transition: all 0.3s ease;
      z-index: 2000;
    }
    .ad-popup.active { visibility: visible; opacity: 1; }
    .ad-popup iframe {
      width: 80%;
      height: 80%;
      border: none;
      border-radius: 10px;
    }
    .ad-popup button {
      position: absolute;
      top: 20px; right: 20px;
      background: #FF9900;
      border: none;
      color: #fff;
      padding: 10px 15px;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
    .ad-popup button:hover { background: #146EB4; }

    /* MOBILE */
    @media(max-width:768px){
      header { flex-direction: column; align-items: flex-start; }
      .hero h1 { font-size: 36px; }
      .hero p { font-size: 16px; }
      .products { padding: 20px; }
      footer { flex-direction: column; align-items: flex-start; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <div class="logo">PrimePicksHub</div>
    <nav>
      <a href="#">Home</a>
      <a href="#">Categories</a>
      <a href="#">About</a>
      <a href="#">Contact</a>
    </nav>
  </header>

  <!-- HERO SECTION -->
  <section class="hero">
    <h1>Discover Trending Products</h1>
    <p>Your ultimate destination for smart shopping & amazing deals!</p>
    <button onclick="window.scrollTo({top: document.querySelector('.products').offsetTop, behavior:'smooth'})">Shop Now</button>
  </section>

  <!-- SEARCH BAR -->
  <div class="search-bar">
    <input type="text" id="searchInput" placeholder="Search products...">
    <button onclick="filterProducts()">Search</button>
  </div>

  <!-- PRODUCTS GRID -->
  <div class="products" id="productGrid">
    <!-- Product cards inserted by JS -->
  </div>

  <!-- FOOTER -->
  <footer>
    <div>
      <h4>About</h4>
      <p>PrimePicksHub brings you trending products & best deals. Shop smartly with our curated selections.</p>
    </div>
    <div>
      <h4>Links</h4>
      <a href="#">Privacy Policy</a><br>
      <a href="#">Facebook Page</a><br>
      <a href="#">Contact Us</a>
    </div>
  </footer>

  <!-- POPUP AD -->
  <div class="ad-popup" id="adPopup">
    <iframe src="" id="adIframe"></iframe>
    <button onclick="closeAd()">Close Ad</button>
  </div>

  <!-- SCRIPT -->
  <script>
    // ======== CONFIG ========
    const adLink = "https://www.profitableratecpm.com/mxwvpffp0n?key=fc7e79075620650c6d87"; // Adsterra ad link
    const adDelay = 7000; // Delay in milliseconds before redirect (7000ms = 7s)
    
    // ======== SAMPLE PRODUCTS ========
    const products = [
      {
        title: "Wireless Bluetooth Headphones",
        description: "High-quality sound with long battery life.",
        price: "$59.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example1",
        category: "Electronics"
      },
      {
        title: "Smart Fitness Watch",
        description: "Track your workouts, heart rate & sleep.",
        price: "$79.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example2",
        category: "Wearables"
      },
      {
        title: "Portable Air Fryer",
        description: "Cook your favorite meals with less oil.",
        price: "$89.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example3",
        category: "Kitchen"
      },
      {
        title: "Gaming Mouse",
        description: "Precision sensor & ergonomic design.",
        price: "$39.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example4",
        category: "Gaming"
      },
      {
        title: "LED Desk Lamp",
        description: "Adjustable brightness and color temperature.",
        price: "$29.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example5",
        category: "Home"
      },
      {
        title: "Waterproof Bluetooth Speaker",
        description: "Enjoy music anywhere, even by the pool.",
        price: "$49.99",
        image: "https://via.placeholder.com/300x200",
        affiliateLink: "https://www.amazon.com/dp/example6",
        category: "Audio"
      }
    ];

    // ======== RENDER PRODUCTS ========
    const productGrid = document.getElementById('productGrid');

    function renderProducts(list) {
      productGrid.innerHTML = '';
      list.forEach((product, index) => {
        const card = document.createElement('div');
        card.classList.add('product-card');
        card.innerHTML = `
          <img src="${product.image}" alt="${product.title}">
          <div class="content">
            <h3>${product.title}</h3>
            <p>${product.description}</p>
            <div class="price">${product.price}</div>
            <button onclick="showAd('${product.affiliateLink}')">Shop Now</button>
          </div>
        `;
        productGrid.appendChild(card);
      });
    }

    renderProducts(products);

    // ======== SEARCH FILTER ========
    function filterProducts() {
      const query = document.getElementById('searchInput').value.toLowerCase();
      const filtered = products.filter(p => p.title.toLowerCase().includes(query) || p.category.toLowerCase().includes(query));
      renderProducts(filtered);
    }

    // ======== AD & REDIRECT LOGIC ========
    const adPopup = document.getElementById('adPopup');
    const adIframe = document.getElementById('adIframe');

    function showAd(affiliateLink) {
      adIframe.src = adLink;
      adPopup.classList.add('active');

      // Auto redirect after delay
      setTimeout(() => {
        window.location.href = affiliateLink;
      }, adDelay);

      // Close button logic
      window.closeAd = () => {
        adPopup.classList.remove('active');
        window.location.href = affiliateLink;
      }
    }
  </script>

</body>
</html>
