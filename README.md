<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Riwaj Wear - Tradition with Elegance</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    .floating-cart-btn {
    position: fixed;
    bottom: 30px;
    right: 30px;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, #e75480 0%, #f8c8dc 100%);
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 24px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
    cursor: pointer;
    z-index: 99;
    transition: all 0.3s ease;
    opacity: 0;
    transform: translateY(20px);
    visibility: hidden;
  }
  
  .floating-cart-btn.visible {
    opacity: 1;
    transform: translateY(0);
    visibility: visible;
  }
  
  .floating-cart-btn:hover {
    transform: scale(1.1);
    box-shadow: 0 6px 20px rgba(0,0,0,0.25);
  }
  
  .floating-cart-btn span {
    position: absolute;
    top: -5px;
    right: -5px;
    background: #90ee90;
    color: white;
    font-size: 12px;
    padding: 3px 8px;
    border-radius: 50%;
    font-weight: bold;
  }
  
  @media (max-width: 768px) {
    .floating-cart-btn {
      bottom: 20px;
      right: 20px;
      width: 50px;
      height: 50px;
      font-size: 20px;
    }
  }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background-color: #fffaf0;
      color: #333;
      line-height: 1.6;
    }
    
    header {
      position: sticky;
      top: 0;
      background: #f8c8dc;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 15px 30px;
      box-shadow: 0 2px 15px rgba(0,0,0,0.1);
      z-index: 100;
    }
    
    .logo {
      font-size: 28px;
      font-weight: bold;
      color: #e75480;
    }
    
    header nav a {
      margin: 0 15px;
      text-decoration: none;
      color: #333;
      font-weight: bold;
      transition: all 0.3s;
      padding: 8px 15px;
      border-radius: 20px;
    }
    
    header nav a:hover {
      background: #90ee90;
      color: #fff;
    }
    
    .cart {
      position: relative;
      cursor: pointer;
      font-size: 24px;
    }
    
    .cart span {
      position: absolute;
      top: -8px;
      right: -15px;
      background: #90ee90;
      color: white;
      font-size: 14px;
      padding: 3px 8px;
      border-radius: 50%;
    }
    
    .hero {
      background: linear-gradient(135deg, #f8c8dc 0%, #d6ffd6 100%);
      padding: 80px 20px;
      text-align: center;
    }
    
    .hero h1 {
      font-size: 3.2rem;
      margin-bottom: 15px;
      color: #e75480;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.1);
    }
    
    .hero p {
      font-size: 1.2rem;
      max-width: 700px;
      margin: 0 auto;
      color: #5a5a5a;
    }
    
    .shop-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
      padding: 40px;
      max-width: 1400px;
      margin: 0 auto;
    }
    
    .product-card {
      background: #fff;
      border-radius: 15px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.08);
      overflow: hidden;
      text-align: center;
      transition: transform 0.3s, box-shadow 0.3s;
      cursor: pointer;
    }
    
    .product-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 25px rgba(0,0,0,0.15);
    }
    
    .product-card img {
      width: 100%;
      height: 300px;
      object-fit: cover;
      display: block;
      transition: transform 0.5s;
    }
    
    .product-card:hover img {
      transform: scale(1.05);
    }
    
    .product-card h3 {
      margin: 15px 0 8px;
      font-size: 1.3rem;
      color: #e75480;
    }
    
    .product-card p {
      padding: 0 15px;
      color: #666;
      font-size: 0.95rem;
    }
    
    .product-card .price {
      color: #e75480;
      font-weight: bold;
      font-size: 1.2rem;
      margin: 10px 0;
    }
    
    .product-card button {
      margin: 15px 0 20px;
      padding: 10px 25px;
      border: none;
      border-radius: 25px;
      background: #90ee90;
      color: #fff;
      font-weight: bold;
      cursor: pointer;
      transition: background 0.3s, transform 0.2s;
    }
    
    .product-card button:hover {
      background: #f8c8dc;
      color: #333;
      transform: scale(1.05);
    }
    
    .product-detail {
      display: none;
      max-width: 1200px;
      margin: 40px auto;
      padding: 20px;
    }
    
    .product-detail.active {
      display: block;
    }
    
    .detail-container {
      display: flex;
      flex-wrap: wrap;
      gap: 40px;
      background: white;
      border-radius: 15px;
      padding: 30px;
      box-shadow: 0 5px 25px rgba(0,0,0,0.1);
    }
    
    .detail-image {
      flex: 1;
      min-width: 300px;
      position: relative;
    }
    
    .detail-image img {
      width: 100%;
      border-radius: 10px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }
    
    .image-slider {
      position: relative;
    }
    
    .slider-nav {
      position: absolute;
      top: 50%;
      width: 100%;
      display: flex;
      justify-content: space-between;
      transform: translateY(-50%);
      padding: 0 15px;
    }
    
    .slider-btn {
      background: rgba(255, 255, 255, 0.7);
      border: none;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      font-size: 18px;
      cursor: pointer;
      transition: all 0.3s;
    }
    
    .slider-btn:hover {
      background: rgba(248, 200, 220, 0.9);
    }
    
    .image-dots {
      display: flex;
      justify-content: center;
      margin-top: 15px;
      gap: 8px;
    }
    
    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: #ddd;
      cursor: pointer;
    }
    
    .dot.active {
      background: #e75480;
    }
    
    .detail-info {
      flex: 1;
      min-width: 300px;
    }
    
    .detail-info h2 {
      font-size: 2.2rem;
      color: #e75480;
      margin-bottom: 15px;
    }
    
    .detail-info .price {
      font-size: 1.5rem;
      color: #e75480;
      font-weight: bold;
      margin: 15px 0;
    }
    
    .detail-info .description {
      margin: 20px 0;
      line-height: 1.8;
      color: #555;
    }
    
    .size-chart {
      margin: 25px 0;
    }
    
    .size-chart h3 {
      margin-bottom: 15px;
      color: #e75480;
    }
    
    .size-options {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
    }
    
    .size-option {
      padding: 10px 15px;
      border: 2px solid #f8c8dc;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.2s;
    }
    
    .size-option:hover, .size-option.selected {
      background: #f8c8dc;
      color: #333;
    }
    
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 15px;
    }
    
    th, td {
      border: 1px solid #f8c8dc;
      padding: 10px;
      text-align: center;
    }
    
    th {
      background-color: #f8c8dc;
    }
    
    .add-to-cart-lg {
      padding: 15px 30px;
      border: none;
      border-radius: 30px;
      background: #90ee90;
      color: #fff;
      font-weight: bold;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background 0.3s;
      margin-top: 20px;
      width: 100%;
    }
    
    .add-to-cart-lg:hover {
      background: #f8c8dc;
      color: #333;
    }
    
    .back-button {
      background: #f8c8dc;
      color: #333;
      border: none;
      padding: 10px 20px;
      border-radius: 20px;
      cursor: pointer;
      margin-bottom: 20px;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .back-button:hover {
      background: #90ee90;
      color: #fff;
    }
    
    /* Cart Modal */
    .cart-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 1000;
      justify-content: center;
      align-items: center;
    }
    
    .cart-modal.active {
      display: flex;
    }
    
    .cart-content {
      background: white;
      border-radius: 15px;
      padding: 30px;
      width: 90%;
      max-width: 800px;
      max-height: 80vh;
      overflow-y: auto;
      box-shadow: 0 5px 30px rgba(0, 0, 0, 0.2);
    }
    
    .cart-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
      padding-bottom: 15px;
      border-bottom: 2px solid #f8c8dc;
    }
    
    .cart-header h2 {
      color: #e75480;
    }
    
    .close-cart {
      background: none;
      border: none;
      font-size: 24px;
      cursor: pointer;
      color: #999;
    }
    
    .close-cart:hover {
      color: #e75480;
    }
    
    .cart-items {
      margin-bottom: 20px;
    }
    
    .cart-item {
      display: flex;
      align-items: center;
      padding: 15px 0;
      border-bottom: 1px solid #f0f0f0;
    }
    
    .cart-item img {
      width: 80px;
      height: 80px;
      object-fit: cover;
      border-radius: 8px;
      margin-right: 15px;
    }
    
    .cart-item-details {
      flex: 1;
    }
    
    .cart-item-details h4 {
      margin-bottom: 5px;
      color: #333;
    }
    
    .cart-item-details p {
      color: #e75480;
      font-weight: bold;
      margin-bottom: 5px;
    }
    
    .cart-item-details .size {
      color: #777;
      font-size: 0.9rem;
    }
    
    .remove-item {
      background: none;
      border: none;
      color: #ff6b6b;
      cursor: pointer;
      font-size: 1.2rem;
    }
    
    .cart-summary {
      margin-top: 10px;
      padding-top: 10px;
      border-top: 2px solid #f8c8dc;
    }
    
    .cart-summary-row {
      display: flex;
      justify-content: space-between;
      padding: 8px 0;
      font-weight: 600;
    }
    
    .delivery-status {
      font-weight: bold;
    }
    
    /* Free-delivery hint box */
    .free-delivery-hint {
      margin: 12px 0 0;
      padding: 12px 16px;
      border-radius: 10px;
      background: linear-gradient(90deg, #fff0f6, #f8fff0);
      color: #333;
      font-weight: 600;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .checkout-btn {
      padding: 15px;
      border: none;
      border-radius: 30px;
      background: #90ee90;
      color: #fff;
      font-weight: bold;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background 0.3s;
      width: 100%;
      margin-top: 15px;
    }
    
    .checkout-btn:hover {
      background: #f8c8dc;
      color: #333;
    }
    
    /* Checkout Modal */
    .checkout-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 1001;
      justify-content: center;
      align-items: center;
    }
    
    .checkout-modal.active {
      display: flex;
    }
    
    .checkout-content {
      background: white;
      border-radius: 15px;
      padding: 30px;
      width: 90%;
      max-width: 600px;
      max-height: 90vh;
      overflow-y: auto;
      box-shadow: 0 5px 30px rgba(0, 0, 0, 0.2);
    }
    
    .checkout-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
      padding-bottom: 15px;
      border-bottom: 2px solid #f8c8dc;
    }
    
    .checkout-header h2 {
      color: #e75480;
    }
    
    .close-checkout {
      background: none;
      border: none;
      font-size: 24px;
      cursor: pointer;
      color: #999;
    }
    
    .close-checkout:hover {
      color: #e75480;
    }
    
    .checkout-form {
      display: flex;
      flex-direction: column;
    }
    
    .form-group {
      margin-bottom: 20px;
    }
    
    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: bold;
      color: #555;
    }
    
    .form-group input {
      width: 100%;
      padding: 12px 15px;
      border: 2px solid #f8c8dc;
      border-radius: 8px;
      font-size: 1rem;
    }
    
    .submit-order {
      padding: 15px;
      border: none;
      border-radius: 30px;
      background: #90ee90;
      color: #fff;
      font-weight: bold;
      font-size: 1.1rem;
      cursor: pointer;
      transition: background 0.3s;
      margin-top: 15px;
    }
    
    .submit-order:hover {
      background: #f8c8dc;
      color: #333;
    }
    
    #contact {
      padding: 60px 40px;
      text-align: center;
      background: linear-gradient(135deg, #f8c8dc 0%, #d6ffd6 100%);
    }
    
    .contact-container {
      max-width: 1000px;
      margin: 0 auto;
      display: flex;
      flex-wrap: wrap;
      gap: 40px;
      justify-content: center;
      text-align: left;
    }
    
    .contact-info {
      flex: 1;
      min-width: 300px;
    }
    
    .contact-info h2 {
      color: #e75480;
      margin-bottom: 25px;
      font-size: 2.2rem;
    }
    
    .contact-detail {
      display: flex;
      align-items: center;
      margin: 20px 0;
      gap: 15px;
    }
    
    .contact-detail i {
      font-size: 24px;
      width: 50px;
      height: 50px;
      background: #90ee90;
      color: white;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .contact-form {
      flex: 1;
      min-width: 300px;
    }
    
    .contact-form h3 {
      color: #e75480;
      margin-bottom: 20px;
      font-size: 1.8rem;
    }
    
    .contact-form form {
      display: flex;
      flex-direction: column;
    }
    
    .contact-form input, 
    .contact-form textarea {
      margin: 8px 0;
      padding: 12px 15px;
      border: 2px solid #f8c8dc;
      border-radius: 8px;
      font-size: 1rem;
    }
    
    .contact-form button {
      padding: 12px 25px;
      border: none;
      border-radius: 25px;
      background: #90ee90;
      color: #fff;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
      transition: background 0.3s;
    }
    
    .contact-form button:hover {
      background: #f8c8dc;
      color: #333;
    }
    
    footer {
      background: #f8c8dc;
      text-align: center;
      padding: 30px;
      margin-top: 40px;
    }
    
    footer p {
      margin: 10px 0;
      color: #333;
    }
    
    .social-icons {
      margin-top: 15px;
      display: flex;
      justify-content: center;
      gap: 15px;
    }
    
    .social-icons a {
      text-decoration: none;
      color: #e75480;
      font-size: 24px;
      transition: transform 0.3s;
    }
    
    .social-icons a:hover {
      transform: scale(1.2);
    }
    
    /* Pagination controls */
    .pagination-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 10px;
      max-width: 1400px;
      margin: 10px auto 50px;
      padding: 0 40px;
    }
    
    .pagination-controls .arrow-btn {
      padding: 10px 18px;
      border-radius: 20px;
      border: none;
      background: #f8c8dc;
      font-weight: bold;
      cursor: pointer;
    }
    
    .pagination-controls .page-indicator {
      text-align: center;
      font-weight: 700;
      color: #e75480;
    }
    
    /* Back to top h3 button */
    .back-to-top-h3 {
      text-align: center;
      margin: 30px 0;
      cursor: pointer;
    }
    
    .back-to-top-h3 h3 {
      display: inline-block;
      padding: 10px 20px;
      background: #f8c8dc;
      color: #e75480;
      border-radius: 12px;
    }
    
    @media (max-width: 768px) {
      header {
        flex-direction: column;
        padding: 15px;
      }
      
      header nav {
        margin: 15px 0;
      }
      
      .hero h1 {
        font-size: 2.5rem;
      }
      
      .detail-container {
        flex-direction: column;
      }
      
      .cart-content, .checkout-content {
        width: 95%;
        padding: 20px;
      }
      
      .pagination-controls {
        padding: 0 15px;
      }
    }
  </style>
</head>
<body>

<header>
  <div class="logo">Riwaj Wear</div>
  <nav>
    <a href="#home">Home</a>
    <a href="#shop">Shop</a>
    <a href="#about">About Us</a>
    <a href="#contact">Contact Us</a>
  </nav>
  <div class="cart" onclick="openCart()">🛒<span id="cart-count">0</span></div>
  <div class="floating-cart-btn" id="floating-cart-btn" onclick="openCart()">
  🛒
  <span id="floating-cart-count">0</span>
</div>
</header>

<section id="home" class="hero">
  <h1>Welcome to Riwaj Wear</h1>
  <p>Tradition with Elegance. Discover our unique collection of traditional and modern clothing.</p>
</section>

<section id="shop">
  <h2 style="text-align:center; padding:40px 20px 20px; font-size:2.5rem; color:#e75480;">Shop Our Collection</h2>
  <div id="shop-container" class="shop-grid">
    <!-- Products will be loaded here -->
  </div>

  <!-- Pagination controls -->
  <div class="pagination-controls" id="pagination-controls">
    <button class="arrow-btn" id="prev-page" onclick="goPrevPage()">← Back</button>
    <div class="page-indicator" id="page-indicator">Page 1 of 4</div>
    <button class="arrow-btn" id="next-page" onclick="goNextPage()">Next →</button>
  </div>

  <!-- Back to top H3 button centered per page -->
  <div class="back-to-top-h3">
    <h3 onclick="scrollToTop()">Back to top</h3>
  </div>
</section>

<!-- Product Detail Section -->
<section id="product-detail" class="product-detail">
  <button class="back-button" onclick="hideProductDetail()">← Back to Products</button>
  <div class="detail-container">
    <div class="detail-image">
      <div class="image-slider">
        <img id="detail-img" src="" alt="" onerror="this.src='https://via.placeholder.com/600x400?text=Image+Not+Found'">
        <div class="slider-nav">
          <button class="slider-btn" onclick="prevImage()">❮</button>
          <button class="slider-btn" onclick="nextImage()">❯</button>
        </div>
      </div>
      <div class="image-dots" id="image-dots">
        <!-- Dots will be added here -->
      </div>
    </div>
    <div class="detail-info">
      <h2 id="detail-title"></h2>
      <p class="price" id="detail-price"></p>
      <p class="description" id="detail-description"></p>
      
      <div class="size-chart">
        <h3>Select Size</h3>
        <div class="size-options" id="size-options">
          <!-- Size options will be added here -->
        </div>
        
        <div id="size-guide">
          <!-- Size guide will be added here -->
        </div>
      </div>
      
      <button class="add-to-cart-lg" onclick="addToCartFromDetail()">Add to Cart</button>
    </div>
  </div>
</section>

<!-- Cart Modal -->
<div class="cart-modal" id="cart-modal">
  <div class="cart-content">
    <div class="cart-header">
      <h2>Your Shopping Cart</h2>
      <button class="close-cart" onclick="closeCart()">×</button>
    </div>
    
    <div class="cart-items" id="cart-items">
      <!-- Cart items will be added here -->
    </div>

    <div class="cart-summary" id="cart-summary">
      <!-- Subtotal, delivery and total will be shown here -->
      <div class="cart-summary-row"><span>Delivery:</span><span id="delivery-text">Rs. 0.00</span></div>
      <div class="cart-summary-row"><span>Total Bill:</span><span id="total-bill-text">Rs. 0.00</span></div>

      <!-- Free delivery hint box (only visible when subtotal < 3000) -->
      <div id="free-delivery-hint" class="free-delivery-hint" style="display:none;">
        <div id="free-delivery-msg">Add Rs. 0.00 more for Free Delivery</div>
        <div id="free-delivery-meter"></div>
      </div>
    </div>
    
    <button class="checkout-btn" onclick="openCheckout()">Proceed to Checkout</button>
  </div>
</div>

<!-- Checkout Modal -->
<div class="checkout-modal" id="checkout-modal">
  <div class="checkout-content">
    <div class="checkout-header">
      <h2>Checkout</h2>
      <button class="close-checkout" onclick="closeCheckout()">×</button>
    </div>

    <div style="margin-bottom:12px;">
      <div style="display:flex; justify-content:space-between; font-weight:700; padding:8px 0;"><span>Delivery:</span><span id="checkout-delivery-text">Rs. 0.00</span></div>
      <div style="display:flex; justify-content:space-between; font-weight:700; padding:8px 0;"><span>Total Bill:</span><span id="checkout-total-text">Rs. 0.00</span></div>
    </div>
    
    <form class="checkout-form" id="checkout-form">
      <div class="form-group">
        <label for="fullname">Full Name</label>
        <input type="text" id="fullname" required>
      </div>
      
      <div class="form-group">
        <label for="email">Email Address</label>
        <input type="email" id="email" required>
      </div>
      
      <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" required>
      </div>
      
      <div class="form-group">
        <label for="address">Shipping Address</label>
        <input type="text" id="address" required>
      </div>
      
      <button type="submit" class="submit-order">Place Order</button>
    </form>
  </div>
</div>

<section id="about" style="padding:60px 40px; text-align:center; background:#fffaf0;">
  <h2 style="font-size:2.5rem; color:#e75480; margin-bottom:30px;">About Us</h2>
  <p style="max-width:800px; margin:0 auto; font-size:1.1rem; line-height:1.8;">
    Riwaj Wear – Tradition with Elegance<br><br>
    Founded in 2024, Riwaj Wear is a women's clothing brand inspired by the beauty of tradition and the charm of modern fashion. Our collections are crafted with premium fabrics, intricate embroidery, and timeless designs that reflect sophistication and cultural grace. At Riwaj Wear, we believe every woman deserves elegance in her everyday wear and confidence in her festive attire. From casuals to luxury suits, each piece is created with care, comfort, and style. Our mission is to blend heritage with contemporary trends, making fashion not just wearable but unforgettable. Riwaj Wear – where tradition meets elegance.
  </p>
</section>

<section id="contact">
  <div class="contact-container">
    <div class="contact-info">
      <h2>Contact Us</h2>
      <div class="contact-detail">
        <i>✉</i>
        <div>
          <h3>Email</h3>
          <p>Riwajwear123@gmail.com</p>
        </div>
      </div>
      <div class="contact-detail">
        <i>📍</i>
        <div>
          <h3>Address</h3>
          <p>Lahore, Pakistan</p>
        </div>
      </div>
      <div class="contact-detail">
        <i>📱</i>
        <div>
          <h3>Phone</h3>
          <p>03704787871</p>
        </div>
      </div>
      <div class="contact-detail">
        <i>🕒</i>
        <div>
          <h3>Opening Hours</h3>
          <p>Mon to Saturday: 9am to 9pm</p>
        </div>
      </div>
    </div>
    
    <div class="contact-form">
      <h3>Send us a Message</h3>
      <form id="contact-form">
        <input type="text" id="contact-name" placeholder="Your Name" required>
        <input type="email" id="contact-email" placeholder="Your Email" required>
        <textarea id="contact-message" placeholder="Your Message" rows="5" required></textarea>
        <button type="submit">Send Message</button>
      </form>
    </div>
  </div>
</section>

<footer>
  <p>© 2025 Riwaj Wear. All rights reserved.</p>
  <div class="social-icons">
    <a href="https://www.instagram.com/riwajthebrand?igsh=bmo2anM0MWgyN3Bh" target="_blank">
      <span>🌸</span>
    </a>
    <a href="https://www.facebook.com/share/1MoPNfaGX2/" target="_blank">
      <span>🌿</span>
    </a>
  </div>
</footer>

<script>
  /***************
   * CONFIG & STATE
   ***************/
  const FREE_DELIVERY_THRESHOLD = 3000;
  const DELIVERY_FEE = 250;
  
  // Webhook URLs
  const CHECKOUT_WEBHOOK_URL = "http://localhost:5678/webhook/checkout-order";
  const CONTACT_WEBHOOK_URL = "http://localhost:5678/webhook/contact-message";

  let cartItems = [];
  let selectedProduct = null;
  let selectedSize = null;
  let currentImageIndex = 0;
  let selectedProductImages = [];

  // Pagination state
  const PER_PAGE = 25;
  let currentPage = 1;
  let products = [];

  /***********************
   * INITIAL RENDERING
   ***********************/
  document.addEventListener('DOMContentLoaded', function() {
    // Sample products data
    products = [
      {
        "id": 1,
        "name": "Amber Embroidery 2Pc",
        "price": 2799,
        "short": "Premium Linen with beautiful embroidery",
        "description": "Premium Linen 2-piece set with intricate embroidery. Features a stylish shirt and comfortable plazzo.",
        "images": [
          "https://i.postimg.cc/vmLMfY35/1-1.jpg",
          "https://i.postimg.cc/W3NV7BHC/1.jpg",
          "https://i.postimg.cc/0NqPzMd8/1-2.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 2,
        "name": "Juna Embroidery 3PC",
        "price": 3699,
        "short": "Premium Collection - Pure Cotton Lawn",
        "description": "Premium 3-piece set with embroidery on shirt, trousers, and dupatta. Made from pure cotton lawn brand fabric.",
        "images": [
          "https://i.postimg.cc/brdj7Q8R/2.jpg",
          "https://i.postimg.cc/LXxpQydX/2-1.jpg",
          "https://i.postimg.cc/SR5pkJxb/2-3.jpg" 
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 3,
        "name": "Warda Emb Long Length",
        "price": 2599,
        "short": "Premium Collection - Summer Linen",
        "description": "Long length embroidery shirt with embroidery plazo. Made from summer linen brand fabric.",
        "images": [
          "https://i.postimg.cc/15kZdndp/3.jpg",
          "https://i.postimg.cc/BQL0NcmS/3-1.jpg",
          "https://i.postimg.cc/8knGhnBX/3-2.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 4,
        "name": "Horiyaa Lawn 3Pc",
        "price": 3700,
        "short": "Luxury Premium Lawn Cotton",
        "description": "Beautiful 3-piece set with embroidery shirt, plain trouser, and shafoon digital dupatta.",
        "images": [
          "https://i.postimg.cc/507hS6vQ/4.jpg",
          "https://i.postimg.cc/d0vcsMw3/4-1.jpg",
          "https://i.postimg.cc/QdcrZNLv/4-2.jpg",
          "https://i.postimg.cc/vmzFDPZz/4-3.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 5,
        "name": "Bluepret 2Pc",
        "price": 2600,
        "short": "Premium Arabic Lawn with Embroidery",
        "description": "Elegant 2-piece set with embroidery shirt and plain trouser. Made from premium Arabic lawn.",
        "images": [
          "https://i.postimg.cc/Sss5Rk5S/5.jpg",
          "https://i.postimg.cc/k4grSxVd/5-1.jpg",
          "https://i.postimg.cc/sxMt6s96/5-2.jpg",
          "https://i.postimg.cc/kGLLLzTn/5-3.jpg",
          "https://i.postimg.cc/TPTB8rJW/5-4.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 6,
        "name": "Jhangir Pocket Emb Long Length",
        "price": 2599,
        "short": "Double Pocket Design - Premium Linen",
        "description": "Long length shirt with double pocket embroidery and embroidery trousers. Made from premium summer linen.",
        "images": [
          "https://i.postimg.cc/xjW0w4JJ/6.jpg",
          "https://i.postimg.cc/zfp6qVx2/6-1.jpg",
          "https://i.postimg.cc/3xXzbLmT/6-2.jpg",
          "https://i.postimg.cc/gr9BgR0j/6-3.jpg",
          "https://i.postimg.cc/rFx8MNxh/6-4.jpg",
          "https://i.postimg.cc/P5HdxvMd/6-5.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 7,
        "name": "White Violet Emb 2Pc",
        "price": 3199,
        "short": "Summer Collection - Pure Lawn",
        "description": "Beautiful white violet embroidery long length shirt with embroidery plazo. Made from pure lawn brand fabric.",
        "images": [
          "https://i.postimg.cc/1RNSrrC9/7.jpg",
          "https://i.postimg.cc/KYvF7XVV/7-1.jpg",
          "https://i.postimg.cc/vmqy3qwm/7-2.jpg",
          "https://i.postimg.cc/63FXN83J/7-3.jpg",
          "https://i.postimg.cc/sxSRf3QB/7-4.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 8,
        "name": "Nazneen Embroidery 3Pc",
        "price": 3899,
        "short": "Summer Collection - Pure Lawn",
        "description": "Elegant 3-piece set with embroidery long length shirt, plain trousers, and chiffon embroidered dupatta.",
        "images": [
          "https://i.postimg.cc/bwMrvwdg/8.jpg", 
          "https://i.postimg.cc/0Ky038Kk/8-1.jpg",
          "https://i.postimg.cc/FsT12Z42/8-2.jpg",
          "https://i.postimg.cc/bwdd8tYd/8-3.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 9,
        "name": "Lina Embroidery 2Pc",
        "price": 2700,
        "short": "Luxury Premium Pure Lawn Cotton",
        "description": "Beautiful embroidery shirt with plain farshi shalwar. Made from luxury premium pure lawn cotton.",
        "images": [
          "https://i.postimg.cc/85dzwd4X/9.jpg",
          "https://i.postimg.cc/TPDw5vD6/9-1.jpg",
          "https://i.postimg.cc/MTJGy37j/9-2.jpg",
          "https://i.postimg.cc/HnpsNJPY/9-3.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 10,
        "name": "Horiyaa 2Pc",
        "price": 3099,
        "short": "Luxury Premium Lawn Cotton",
        "description": "Elegant embroidery shirt with plain trouser. Made from luxury premium lawn cotton.",
        "images": [
          "https://i.postimg.cc/8PXPyzdG/10.jpg",
          "https://i.postimg.cc/4yBNRJrz/10-1.jpg",
          "https://i.postimg.cc/zDjfgjVV/10-2.jpg",
          "https://i.postimg.cc/YqCCfWW8/10-3.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 11,
        "name": "Zafa 2Pc Co-Ord Set",
        "price": 2700,
        "short": "Luxury Premium Lawn Cotton",
        "description": "Beautiful co-ord set with embroidery shirt and embroidery trousers. Made from luxury premium lawn cotton.",
        "images": [
          "https://i.postimg.cc/PxHtLpHW/11.jpg",
          "https://i.postimg.cc/fR3W1Q59/11-1.jpg",
          "https://i.postimg.cc/SxwQh1tt/11-2.jpg",
          "https://i.postimg.cc/TPgdYjz2/11-3.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 12,
        "name": "Sitara 3Pc",
        "price": 3050,
        "short": "Luxury Premium Lawn Cotton",
        "description": "Elegant 3-piece set with embroidery shirt, plain trouser, and shaffon dupatta. Made from luxury premium lawn cotton.",
        "images": [
          "https://i.postimg.cc/5y71ksCg/12.jpg",
          "https://i.postimg.cc/JnQRjr79/12-1.jpg",
          "https://i.postimg.cc/L562Tcnh/12-2.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 13,
        "name": "Grace 2Pc",
        "price": 2599,
        "short": "Stone Linen with Embroidery",
        "description": "Beautiful embroidery shirt with plain trouser. Made from high-quality stone linen fabric.",
        "images": [
          "https://i.postimg.cc/wjsH0cT5/13.jpg",
          "https://i.postimg.cc/gkjG6bCT/13-1.jpg",
          "https://i.postimg.cc/7YRw3QDY/13-2.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 14,
        "name": "Farshi White Shalwar 3Pc",
        "price": 2400,
        "short": "Chamki Silk with Arganza Dupatta",
        "description": "Elegant 3-piece set with chamki silk shirt, farshi shalwar, and soft arganza dupatta.",
        "images": [
          "https://i.postimg.cc/TwT6dzjQ/14.jpg",
          "https://i.postimg.cc/nLbx5jCy/14-1.jpg",
          "https://i.postimg.cc/mrY4GL9t/14-2.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 15,
        "name": "Minsha 2Pc",
        "price": 2899,
        "short": "Luxury Premium Lawn Cotton",
        "description": "Beautiful embroidery shirt with sequence bazo work and farshi shalwar. Made from luxury premium lawn cotton.",
        "images": [
          "https://i.postimg.cc/WpWvVfd6/15.jpg",
          "https://i.postimg.cc/63zNyMYK/15-1.jpg",
          "https://i.postimg.cc/Wz3cr0Hk/15-2.jpg",
          "https://i.postimg.cc/qq5VGgPZ/15-3.jpg"
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 16,
        "name": "Kalamkar Green 2Pc",
        "price": 2599,
        "short": "Premium Dhank Fabric",
        "description": "Elegant embroidery shirt with plain trouser. Made from premium dhank fabric.",
        "images": [
          "https://i.postimg.cc/JzJVbrPP/16.jpg",
          "https://i.postimg.cc/X7r0YcFM/16-1.jpg",
          "https://i.postimg.cc/65Fx22L8/16-2.jpg",
          "https://i.postimg.cc/8CS842YD/16-3.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 17,
        "name": "Malvin 2Pc Co-Ord Set",
        "price": 2499,
        "short": "Premium Linen with Elegant Embroidery",
        "description": "Elegant co-ord set with embroidery shirt and straight fit trousers. Made from premium linen fabric.",
        "images": [
          "https://i.postimg.cc/260PzVS8/17.jpg",
          "https://i.postimg.cc/W46BH9RZ/17-1.jpg",
          "https://i.postimg.cc/yd1M4FBb/17-2.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 18,
        "name": "Daina 2Pc Co-Ord Set",
        "price": 2700,
        "short": "Luxury Premium Pure Lawn Cotton",
        "description": "Beautiful co-ord set with embroidery shirt and plain farshi shalwar. Made from luxury premium pure lawn cotton.",
        "images": [
          "https://i.postimg.cc/rFB7F6MW/18.jpg",
          "https://i.postimg.cc/SR53M39B/18-1.jpg",
          "https://i.postimg.cc/Y2yJZGPd/18-2.jpg",
          "https://i.postimg.cc/WbFQvpLT/18-3.jpg"  
        ],
        "hasDetailedSizeChart": false
      },
      {
        "id": 19,
        "name": "Western Black Embroidery 2Pc",
        "price": 2600,
        "short": "Cotton Fabric with Western Design",
        "description": "Western style black embroidery shirt with plain trouser. Made from high-quality cotton fabric.",
        "images": [
          "https://i.postimg.cc/FRCnM8TY/19.jpg",
          "https://i.postimg.cc/8zL97yzY/19-1.jpg",
          "https://i.postimg.cc/s2y87pBg/19-2.jpg",
          "https://i.postimg.cc/d0BfBLdm/19-3.jpg",
          "https://i.postimg.cc/cHLb50Bq/19-4.jpg"
        ],
        "hasDetailedSizeChart": true
      },
      {
        "id": 20,
        "name": "Mehar 3PC Digital Co-Ord Set",
        "price": 3299,
        "short": "Luxury Premium Poly Lawn",
        "description": "Beautiful 3-piece digital co-ord set with digital shirt, digital shalwar, and monar dupatta. Made from luxury premium poly lawn.",
        "images": [
          "https://i.postimg.cc/qM3ZFmy7/20.jpg",
          "https://i.postimg.cc/fy3gDCPB/20-1.jpg",
          "https://i.postimg.cc/brKVJbc8/20-2.jpg",
          "https://i.postimg.cc/h4w5pFJw/20-3.jpg" 
        ],
        "hasDetailedSizeChart": false
      },
      {
    "id": 21,
    "name": "BLACK GULAB EMBROIDERY 2Pc",
    "price": 2600,
    "short": "Emb Shirt + Plain Trouser - Cotton",
    "description": "Emb Shirt + Plain Trouser. Sizes: S | M | L. Fabric: Cotton.",
    "images": [
       "https://i.postimg.cc/HnfNkLVq/21.jpg",
        "https://i.postimg.cc/9QHS3r3T/21-1.jpg",
        "https://i.postimg.cc/dQXpB545/21-2.jpg",
        "https://i.postimg.cc/X7ChD9P4/21-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 22,
    "name": "NOVINA LAWN CO-ORD SET 2Pc",
    "price": 2700,
    "short": "Digital Shirt + Trouser - Premium Poly Lawn",
    "description": "2Pc Digital Co-Ord Set. Sizes: S | M | L | XL. Fabric: Luxury Premium Poly Lawn.",
    "images": [
        "https://i.postimg.cc/wvM45NJK/22.jpg",
        "https://i.postimg.cc/FK9BR8HH/22-1.jpg",
       "https://i.postimg.cc/Vk9hzm1h/22-2.jpg",
       "https://i.postimg.cc/fbBg0CVj/22-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 23,
    "name": "ALYANA EMB 2Pc",
    "price": 2599,
    "short": "Emb Shirt + Emb Plazo - Premium Arabic Lawn",
    "description": "Premium Arabic Lawn with Embroidery Work. Sizes: S | M | L.",
    "images": [
      "https://i.postimg.cc/nMbdtwWZ/23.jpg",
    "https://i.postimg.cc/85YKZCB7/23-1.jpg",
    "https://i.postimg.cc/tRZppZcm/23-2.jpg",
    "https://i.postimg.cc/prn04tqq/23-3.jpg" 
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 24,
    "name": "WHITE/BLUE LAWN 3Pc",
    "price": 3700,
    "short": "Emb Shirt + Plain Trouser + Dupatta - Pure Lawn Cotton",
    "description": "3Pc Lawn Set with Shafoon Dupatta and Lace Work. Sizes: S | M | L | XL.",
    "images": [
     "https://i.postimg.cc/xd1V7cH5/24.jpg",
    "https://i.postimg.cc/HWqHxWDW/24-1.jpg",
    "https://i.postimg.cc/Z5ZS8f51/24-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 25,
    "name": "AROOJ LAWN 3Pc",
    "price": 3299,
    "short": "Emb Shirt + Emb Plazo + Digital Dupatta - Summer Linen Embroidery",
    "description": "3Pc with digital dupatta. Sizes: M | L.",
    "images": [
      "https://i.postimg.cc/sXBdjqTZ/25.jpg",
    "https://i.postimg.cc/0yfqcp6r/25-1.jpg",
    "https://i.postimg.cc/Bv7fG4B0/25-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 26,
    "name": "ARFA EMBROIDERY LAWN 3Pc",
    "price": 3799,
    "short": "Emb Shirt + Emb Trouser - Pure Lawn",
    "description": "Premium 3Pc Pure Lawn (Brand Fabric). Sizes: S | M | L | XL.",
    "images": [
      "https://i.postimg.cc/Jn9wGxFY/26-1.jpg",
    "https://i.postimg.cc/qqnPnnVJ/26-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 27,
    "name": "AZMIN LAWN 2Pc",
    "price": 2700,
    "short": "Emb Shirt + Plain Trouser - Poly Lawn",
    "description": "Summer Collection. Sizes: S | M | L | XL.",
    "images": [
        "https://i.postimg.cc/h4dWHFJk/27.jpg",
    "https://i.postimg.cc/wT5KjhQF/27-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 28,
    "name": "PINK FLORAL DIGITAL PRINTED 2Pc",
    "price": 2599,
    "short": "Digital Printed Shirt + Plazo - Silky Lawn",
    "description": "Summer Collection. Sizes: S | M | L | XL.",
    "images": [
       "https://i.postimg.cc/cJb2bTd1/28.jpg",
    "https://i.postimg.cc/021RvtDb/28-1.jpg",
    "https://i.postimg.cc/cLdpgrDW/28-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 29,
    "name": "HIRA DIGITAL PRINT 2Pc",
    "price": 2599,
    "short": "Digital Printed Shirt + Printed Trouser - Poly Lawn",
    "description": "Digital Print, Trendy & Eye-Catching. Sizes: M | L.",
    "images": [
        "https://i.postimg.cc/QN5wfpws/29.jpg",
    "https://i.postimg.cc/DZ4Hkszr/29-1.jpg",
    "https://i.postimg.cc/cJHPhPy5/29-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 30,
    "name": "PHULKARI 2Pc",
    "price": 2600,
    "short": "Emb Shirt + Plain Trouser - Premium Linen",
    "description": "Summer Premium Linen set. Sizes: S | M | L.",
    "images": [
          "https://i.postimg.cc/dtYXphcC/30.jpg",
    "https://i.postimg.cc/0jp4rsDr/30-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
   {
    "id": 31,
    "name": "DAZZEL EMB LONG LENGTH 2Pc",
    "price": 2599,
    "short": "Full Embroidered Shirt + Plain Trouser - Summer Linen",
    "description": "Long length 2Pc. Sizes: M | L.",
    "images": [
        "https://i.postimg.cc/9frNZTZ6/31.jpg",
    "https://i.postimg.cc/VLWT8zzV/31-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
    {
    "id": 32,
    "name": "JENIFER EMB CO-ORD SET",
    "price": 2599,
    "short": " Premium Summer Linen Embroidery",
    "description": "Beautiful 2-piece linen set with intricate embroidery. Perfect for summer occasions.Embroidered Shirt with Embroidered Trouser",
    "images": [
           "https://i.postimg.cc/9QXkXsMF/32-black.jpg",
    "https://i.postimg.cc/sgnNMKQP/32-grey.jpg",
    "https://i.postimg.cc/nLgSkz1C/32-red.jpg",
    "https://i.postimg.cc/RFtsbBPG/32-white.jpg" 
    ],
    "hasDetailedSizeChart": true,
    "sizeChart": {
      "title": "Size Measurements",
      "headers": ["Size", "Chest", "Length", "Armhole"],
      "rows": [
        ["S", "19", "45", "10"],
        ["M", "21", "45", "10"],
        ["L", "23", "45", "11"],
        ["XL", "24", "45", "12"]
      ]
    }
  },
  {
    "id": 33,
    "name": "MATKA DIGITAL MIRROR 2PC",
    "price": 2599,
    "short": "Brand Stitch Mirror Work - Grip Silk",
    "description": "Plazzo Trouser. Sizes: M | L.",
    "images": [
         "https://i.postimg.cc/W149crWd/33.jpg",
    "https://i.postimg.cc/RhQP4TxH/33-1.jpg",
    "https://i.postimg.cc/pVDcfP5L/33-2.jpg",
    "https://i.postimg.cc/rFMng75C/33-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 34,
    "name": "NORAA 3PC",
    "price": 2800,
    "short": "Plain White Shirt with Black Fabric Work - China Lawn",
    "description": "3Pc with Shaffon Dupatta. Sizes: S | M | L | XL.",
    "images": [
        "https://i.postimg.cc/q7hjzrd0/34.jpg",
    "https://i.postimg.cc/52ks40Tn/34-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 35,
    "name": "SILVIRA 2PC",
    "price": 3900,
    "short": "Luxury Premium Pure Lawn Cotton",
    "description": "Premium 2Pc. Sizes: S | M | L | XL.",
    "images": [
        "https://i.postimg.cc/L5TVr6jk/35.jpg",
    "https://i.postimg.cc/nLyTmWHm/35-0.jpg",
    "https://i.postimg.cc/7hDVsTJY/35-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 36,
    "name": "ZIMAL BLUE LAWN 2PC",
    "price": 3100,
    "short": "Luxury Premium Pure Lawn Cotton",
    "description": "2Pc. Sizes: S | M | L | XL.",
    "images": [
        "https://i.postimg.cc/3x6ZMq0q/36.jpg",
    "https://i.postimg.cc/qBXQtQWt/36-1.jpg",
    "https://i.postimg.cc/HsYzbXC6/36-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 37,
    "name": "SOFIA EMBROIDERY WORK 2PC",
    "price": 2300,
    "short": "Long Neck Embroidered Shirt with Embroidered Plazo - Premium Linen",
    "description": "Sizes: M | L.",
    "images": [
        "https://i.postimg.cc/9f7YcBGQ/37.jpg",
    "https://i.postimg.cc/9FLpb0mC/37-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 38,
    "name": "BLUE TOPZ 2PC",
    "price": 2599,
    "short": "Emb Shirt + Plazzo - Premium Linen",
    "description": "Sizes: S | M | L | XL.",
    "images": [
          "https://i.postimg.cc/hjnTcRD2/38.jpg",
    "https://i.postimg.cc/XYXgzWqF/38-1.jpg",
    "https://i.postimg.cc/DZQQXypV/38-2.jpg",
    "https://i.postimg.cc/4yL96Kz0/38-3.jpg",
    "https://i.postimg.cc/Qtq5MYVh/38-4.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 39,
    "name": "RUBY PINK 2PC (Farshi Shalwar)",
    "price": 3100,
    "short": "Emb Shirt + Emb Plazo - Pure Lawn Cotton",
    "description": "Farshi Shalwar set. Sizes: S | M | L | XL.",
    "images": [
         "https://i.postimg.cc/6Qr4Hbrn/39.jpg",
    "https://i.postimg.cc/sDxSVczC/39-1.jpg",
    "https://i.postimg.cc/W4LJwcks/39-2.jpg",
    "https://i.postimg.cc/024Srw5M/39-3.jpg",
    "https://i.postimg.cc/Bn1KFnth/39-4.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 40,
    "name": "FIZA LAWN 2PC",
    "price": 3100,
    "short": "Embroidered Shirt + Embroidered Plazo - Pure Lawn",
    "description": "Sizes: S | M | L | XL.",
    "images": [
          "https://i.postimg.cc/FFWdnLLW/40.jpg",
    "https://i.postimg.cc/JnKD8ydh/40-1.jpg",
    "https://i.postimg.cc/Y094CpJz/40-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
    {
    "id": 41,
    "name": "MONOCHROME DIGITAL 2PC",
    "price": 2700,
    "short": "Digital Shirt with Digital Plazo - Poly Lawn",
    "description": "Free size. Chest 22/23. Shirt length 38/39.",
    "images": [
         "https://i.postimg.cc/FHcYRCn8/41.jpg",
    "https://i.postimg.cc/vTN41JyF/41-1.jpg",
    "https://i.postimg.cc/DySJVwQ2/41-2.jpg",
    "https://i.postimg.cc/9Fs4cH1y/41-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 42,
    "name": "HORIYA LAWN 3PC",
    "price": 3700,
    "short": "Emb Shirt + Plain Trouser + Dupatta - Luxury Premium Lawn Cotton",
    "description": "3Pc set. Sizes: S | M | L | XL.",
    "images": [
         "https://i.postimg.cc/k4j4Z0B6/42.jpg",
    "https://i.postimg.cc/bvhs207J/42-1.jpg",
    "https://i.postimg.cc/zBDvxzXY/42-2.jpg",
    "https://i.postimg.cc/d0jDRkF9/42-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 43,
    "name": "IRIS EMBROIDERY 2PC",
    "price": 2600,
    "short": "Embroidered Shirt + Plazzo - Premium Linen",
    "description": "Sizes: S | M | L.",
    "images": [
         "https://i.postimg.cc/Gm0pZJhQ/43.jpg",
    "https://i.postimg.cc/3NdRHtvL/43-1.jpg",
    "https://i.postimg.cc/tRMJzGK8/43-2.jpg",
    "https://i.postimg.cc/yY3dQrBx/43-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 44,
    "name": "GULISTAN EMBOSSED 2PC",
    "price": 2000,
    "short": "Embossed Shirt + Trouser - Premium Linen",
    "description": "Sizes: S | M | L.",
    "images": [
       "https://i.postimg.cc/zBfDnx0J/44.jpg",
    "https://i.postimg.cc/RZc096Wz/44-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 45,
    "name": "WAVY ORGANZA 3PC",
    "price": 2499,
    "short": "Shirt + Plazzo + Dupatta - Organza",
    "description": "3Pc Organza set. Sizes: S | M | L.",
    "images": [
       "https://i.postimg.cc/bNnyHDH2/45.jpg",
    "https://i.postimg.cc/d1SsnGxG/45-1.jpg",
    "https://i.postimg.cc/prh2Syw4/45-2.jpg",
    "https://i.postimg.cc/05F5wdms/45-3.jpg"
    ],
    "hasDetailedSizeChart": false
  },
  {
    "id": 46,
    "name": "INZIA GOWN 3PC",
    "price": 2899,
    "short": "Inner + Gown + Plazzo - Silky Lawn",
    "description": "3Pc gown set. Sizes: S | M | L.",
    "images": [
         "https://i.postimg.cc/MpbzNCL6/46.jpg",
    "https://i.postimg.cc/13Z9WmJ7/46-1.jpg"
    ],
    "hasDetailedSizeChart": false
  },
       {
    "id": 47,
    "name": " EMILY LONG KURTI (Foam Print)",
    "price": 1500,
    "short": "Premium  Lenin Long Kurti ",
    "description":"Luxury Premium 👗 ✨.Perfect for summer occasions.",
    "images": [
         "https://i.postimg.cc/W4Nsv9RM/47-black.jpg",
    "https://i.postimg.cc/Bvm4QxsR/47-maroon.jpg",
    "https://i.postimg.cc/263mqVSy/47-mehendi.jpg",
    "https://i.postimg.cc/QtPDchFb/47-yellow.jpg"
    ],
    "hasDetailedSizeChart": true,
    "sizeChart": {
      "title": "Size Measurements",
      "headers": ["Size", "Chest", "Shirt Length", "Trouser Length"],
      "rows": [
        ["S", "19", "37", "37"],
        ["M", "21", "37", "38"],
        ["L", "23", "37", "38"],
        ["XL", "24", "37", "38"]
      ]
    }
  },
  {
    "id": 48,
    "name": "Avril 2PC",
    "price": 2600,
    "short": "Silky Lawn 2Pc",
    "description": "Silky Lawn 2Pc. Sizes: S | M | L.",
    "images": [
       "https://i.postimg.cc/ZndSc23h/48.jpg",
    "https://i.postimg.cc/141ZYBcV/48-1.jpg",
    "https://i.postimg.cc/ZYBB2qxJ/48-2.jpg"
    ],
    "hasDetailedSizeChart": false
  },
    {
    "id": 49,
    "name": "Amel 2PC",
    "price": 2200,
    "short": "Premium Lenin 👗 ✨",
    "description": "Premium Lenin 👗 ✨.Perfect for summer occasions.",
    "images": [
         "https://i.postimg.cc/kg922v35/49-black.jpg",
    "https://i.postimg.cc/mgwtC1By/49-dark-maroon.jpg",
    "https://i.postimg.cc/Pq5N4fqs/49-light-skin.jpg"
    ],
    "hasDetailedSizeChart": true,
    "sizeChart": {
      "title": "Size Measurements",
      "headers": ["Size", "Chest", "Shirt Length", "Plazo Length"],
      "rows": [
        ["S", "19", "45", "38"],
        ["M", "21", "45", "38"],
        ["L", "23", "46", "39"],
        ["XL", "24", "46", "39"]
      ]
    }
  },
  {
    "id": 50,
    "name": "Calico Embroidery 3PC",
    "price": 3150,
    "short": "3Pc - Premium Lenin with Dupatta",
    "description": "3Pc set with dupatta. Sizes: S | M | L.",
    "images": [
       "https://i.postimg.cc/CMq5JQw1/50.jpg",
    "https://i.postimg.cc/SsXsBZ8g/50-1.jpg",
    "https://i.postimg.cc/pdcr1N99/50-2.jpg",
    "https://i.postimg.cc/sXtXsp4s/50-3.jpg",
    "https://i.postimg.cc/NFm0M5dT/50-4.jpg"
    ],
    "hasDetailedSizeChart": false
  }
    ];

    // Render the initial page
    renderProducts(currentPage);

    // Load cart from localStorage if available
    const savedCart = localStorage.getItem('riwajCart');
    if (savedCart) {
      cartItems = JSON.parse(savedCart);
    }
    updateCartCount();
    
    // Add event listener to contact form
    document.getElementById('contact-form').addEventListener('submit', handleContactSubmit);
  });

  /***********************
   * PAGINATION FUNCTIONS
   ***********************/
  function totalPages() {
    return Math.ceil(products.length / PER_PAGE);
  }

  function getThumbnail(p) {
    if (p.images && p.images.length) return p.images[0];
    return 'https://via.placeholder.com/400x300?text=Image+Not+Found';
  }

  function renderProducts(page = 1) {
    currentPage = page;
    const shopContainer = document.getElementById("shop-container");
    shopContainer.innerHTML = '';

    const start = (page - 1) * PER_PAGE;
    const end = start + PER_PAGE;
    const pageProducts = products.slice(start, end);

    pageProducts.forEach(p => {
      const card = document.createElement("div");
      card.className = "product-card";
      const thumb = getThumbnail(p);
      card.innerHTML = `
        <img src="${thumb}" alt="${escapeHtml(p.name)}" onerror="this.src='https://via.placeholder.com/400x300?text=Image+Not+Found'">
        <h3>${escapeHtml(p.name)}</h3>
        <p>${escapeHtml(p.short || '')}</p>
        <p class="price">Rs. ${Number(p.price).toFixed(2)}</p>
        <button class="add-to-cart" data-id="${p.id}">Add to Cart</button>
      `;

      // Show detail on card click (but prevent when clicking Add to Cart)
      card.addEventListener('click', function(e) {
        if (!e.target.classList.contains('add-to-cart')) {
          showProductDetailById(p.id);
        }
      });

      // Add to cart button
      const addToCartBtn = card.querySelector('.add-to-cart');
      addToCartBtn.addEventListener('click', function(e) {
        e.stopPropagation();
        addToCart(p, 'M'); // default size M for quick add
      });

      shopContainer.appendChild(card);
    });

    // Update pagination UI
    document.getElementById('page-indicator').textContent = `Page ${currentPage} of ${totalPages()}`;
    document.getElementById('prev-page').style.visibility = currentPage <= 1 ? 'hidden' : 'visible';
    document.getElementById('next-page').style.visibility = currentPage >= totalPages() ? 'hidden' : 'visible';
    // Scroll to top of shop when changing page
    document.getElementById('shop').scrollIntoView({behavior:'smooth'});
  }

  function goNextPage() { if (currentPage < totalPages()) renderProducts(currentPage + 1); }
  function goPrevPage() { if (currentPage > 1) renderProducts(currentPage - 1); }

  function scrollToTop() { window.scrollTo({top: 0, behavior: 'smooth'}); }

  /***********************
   * PRODUCT DETAIL
   ***********************/
  function showProductDetailById(id) {
    const p = products.find(x => x.id === id);
    if (p) showProductDetail(p);
  }

  function showProductDetail(product) {
    selectedProduct = product;
    currentImageIndex = 0;

    // Determine images to show in slider
    selectedProductImages = (product.images && product.images.length) ? product.images.slice() : ['https://via.placeholder.com/600x400?text=Image+Not+Found'];

    // Set detail image
    document.getElementById("detail-img").src = selectedProductImages[0];

    // Build dots
    const dotsContainer = document.getElementById("image-dots");
    dotsContainer.innerHTML = '';
    selectedProductImages.forEach((img, index) => {
      const dot = document.createElement("div");
      dot.className = `dot ${index === 0 ? 'active' : ''}`;
      dot.addEventListener('click', () => showImage(index));
      dotsContainer.appendChild(dot);
    });

    document.getElementById("detail-title").textContent = product.name;
    document.getElementById("detail-price").textContent = `Rs. ${Number(product.price).toFixed(2)}`;
    document.getElementById("detail-description").textContent = product.description || '';

    // Sizes
    const sizeOptionsContainer = document.getElementById("size-options");
    sizeOptionsContainer.innerHTML = '';
    const sizes = ['S','M','L','XL'];
    sizes.forEach(size => {
      const sizeOption = document.createElement("div");
      sizeOption.className = "size-option";
      sizeOption.textContent = size;
      sizeOption.addEventListener('click', function(){ selectSize(this); });
      sizeOptionsContainer.appendChild(sizeOption);
    });

    // Size guide area
    const sizeGuideContainer = document.getElementById("size-guide");
    sizeGuideContainer.innerHTML = '';
    if (product.hasDetailedSizeChart) {
      const title = document.createElement('h3'); 
      title.textContent = "Size Chart: S M L XL";
      sizeGuideContainer.appendChild(title);
      const p = document.createElement('p');
      p.textContent = "Please refer to our standard size chart for measurements.";
      sizeGuideContainer.appendChild(p);
    } else {
      const t = document.createElement('h3'); 
      t.textContent = "Size Chart: S M L XL";
      sizeGuideContainer.appendChild(t);
    }

    document.getElementById("shop").style.display = "none";
    document.getElementById("product-detail").classList.add("active");
    selectedSize = null;
    document.querySelectorAll('.size-option').forEach(o => o.classList.remove('selected'));
    window.scrollTo(0,0);
  }

  function hideProductDetail() {
    document.getElementById("product-detail").classList.remove("active");
    document.getElementById("shop").style.display = "block";
  }

  function showImage(index) {
    if (!selectedProductImages || !selectedProductImages.length) return;
    currentImageIndex = index;
    document.getElementById("detail-img").src = selectedProductImages[index];
    document.querySelectorAll('.dot').forEach((d,i)=> d.classList.toggle('active', i===index));
  }
  function nextImage(){ if (!selectedProductImages || !selectedProductImages.length) return; let n = currentImageIndex+1; if (n >= selectedProductImages.length) n = 0; showImage(n); }
  function prevImage(){ if (!selectedProductImages || !selectedProductImages.length) return; let p = currentImageIndex-1; if (p < 0) p = selectedProductImages.length-1; showImage(p); }

  function selectSize(element) {
    document.querySelectorAll('.size-option').forEach(o=>o.classList.remove('selected'));
    element.classList.add('selected');
    selectedSize = element.textContent;
  }

  function addToCartFromDetail() {
    if (!selectedSize) {
      alert("Please select a size first!");
      return;
    }
    addToCart(selectedProduct, selectedSize);
    alert(`Added ${selectedProduct.name} (Size: ${selectedSize}) to cart!`);
  }

  /***********************
   * CART LOGIC
   ***********************/
  function addToCart(product, size) {
    const existingIndex = cartItems.findIndex(i => i.id === product.id && i.size === size);
    const imgForCart = (product.images && product.images[0]) || 'https://via.placeholder.com/80';
    if (existingIndex >= 0) {
      cartItems[existingIndex].quantity += 1;
    } else {
      cartItems.push({
        id: product.id,
        name: product.name,
        price: product.price,
        img: imgForCart,
        size: size || 'M',
        quantity: 1
      });
    }
    saveCart();
    updateCartCount();
    updateCartDisplay();
  }

  function saveCart() {
    localStorage.setItem('riwajCart', JSON.stringify(cartItems));
  }

  function updateCartCount() {
    const cartCount = cartItems.reduce((s,i) => s + i.quantity, 0);
    document.getElementById('cart-count').textContent = cartCount;
  }

  function updateCartDisplay() {
    const cartItemsContainer = document.getElementById("cart-items");
    cartItemsContainer.innerHTML = '';
    let subtotal = 0;
    cartItems.forEach((item, index) => {
      subtotal += item.price * item.quantity;
      const el = document.createElement('div');
      el.className = 'cart-item';
      el.innerHTML = `
        <img src="${item.img}" alt="${escapeHtml(item.name)}" onerror="this.src='https://via.placeholder.com/80x80?text=Image+Not+Found'">
        <div class="cart-item-details">
          <h4>${escapeHtml(item.name)}</h4>
          <p>Rs. ${Number(item.price).toFixed(2)} × ${item.quantity}</p>
          <p class="size">Size: ${escapeHtml(item.size)}</p>
        </div>
        <div style="display:flex;flex-direction:column;gap:6px;">
          <button style="padding:6px 10px;border-radius:8px;border:none;background:#f8c8dc;cursor:pointer;" onclick="increaseQty(${index})">+</button>
          <button style="padding:6px 10px;border-radius:8px;border:none;background:#f8c8dc;cursor:pointer;" onclick="decreaseQty(${index})">-</button>
        </div>
        <button class="remove-item" onclick="removeFromCart(${index})">×</button>
      `;
      cartItemsContainer.appendChild(el);
    });

    // Determine delivery
    const deliveryFee = subtotal < FREE_DELIVERY_THRESHOLD && subtotal > 0 ? DELIVERY_FEE : 0;
    const deliveryTextEl = document.getElementById('delivery-text');
    deliveryTextEl.textContent = deliveryFee > 0 ? `Rs. ${deliveryFee.toFixed(2)}` : 'Free';

    // Total bill (user sees only "Total Bill: Rs. XXXX" which includes delivery)
    const totalBill = subtotal + deliveryFee;
    document.getElementById('total-bill-text').textContent = `Rs. ${totalBill.toFixed(2)}`;

    // Free delivery hint box
    const freeHint = document.getElementById('free-delivery-hint');
    const freeMsg = document.getElementById('free-delivery-msg');
    if (subtotal > 0 && subtotal < FREE_DELIVERY_THRESHOLD) {
      const moreNeeded = FREE_DELIVERY_THRESHOLD - subtotal;
      freeMsg.textContent = `Add Rs. ${moreNeeded.toFixed(2)} more for Free Delivery`;
      freeHint.style.display = 'flex';
    } else {
      freeHint.style.display = 'none';
    }

    // Update checkout modal info (so when user opens checkout they see the same)
    document.getElementById('checkout-delivery-text').textContent = deliveryFee > 0 ? `Rs. ${deliveryFee.toFixed(2)}` : 'Free';
    document.getElementById('checkout-total-text').textContent = `Rs. ${totalBill.toFixed(2)}`;

    saveCart();
  }

  function increaseQty(index) {
    cartItems[index].quantity += 1;
    updateCartCount();
    updateCartDisplay();
  }
  function decreaseQty(index) {
    if (cartItems[index].quantity > 1) {
      cartItems[index].quantity -= 1;
    } else {
      cartItems.splice(index,1);
    }
    updateCartCount();
    updateCartDisplay();
  }

  function removeFromCart(index) {
    cartItems.splice(index, 1);
    updateCartCount();
    updateCartDisplay();
  }

  function openCart() {
    updateCartDisplay();
    document.getElementById('cart-modal').classList.add('active');
  }
  function closeCart() {
    document.getElementById('cart-modal').classList.remove('active');
  }

  /***********************
   * CHECKOUT FLOW - MODIFIED FOR WEBHOOK
   ***********************/
  function openCheckout() {
    if (cartItems.length === 0) {
      alert("Your cart is empty!");
      return;
    }
    document.getElementById('checkout-modal').classList.add('active');
    closeCart();
  }

  function closeCheckout() {
    document.getElementById('checkout-modal').classList.remove('active');
  }

  document.getElementById('checkout-form').addEventListener('submit', async function(e) {
    e.preventDefault();
    
    // Get form values
    const name = document.getElementById('fullname').value;
    const email = document.getElementById('email').value;
    const phone = document.getElementById('phone').value;
    const address = document.getElementById('address').value;
    
    // Calculate order total
    const subtotal = cartItems.reduce((sum, item) => sum + (item.price * item.quantity), 0);
    const deliveryFee = subtotal < FREE_DELIVERY_THRESHOLD ? DELIVERY_FEE : 0;
    const total = subtotal + deliveryFee;
    
    // Prepare order data for webhook
    const orderData = {
      customer: {
        name,
        email,
        phone,
        address
      },
      order: {
        items: cartItems,
        subtotal,
        deliveryFee,
        total
      }
    };
    
    try {
      // Show loading state
      const submitBtn = document.querySelector('.submit-order');
      const originalText = submitBtn.textContent;
      submitBtn.textContent = 'Placing Order...';
      submitBtn.disabled = true;
      
      // Send order data to webhook
      const response = await fetch(CHECKOUT_WEBHOOK_URL, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(orderData)
      });
      
      const result = await response.json();
      
      if (response.ok) {
        // Show success message from webhook response
        alert(result.message || `✅ Order received successfully!\n\nHey ${name}, thanks for shopping with us 💓. We will contact you soon at ${email} or on phone ${phone}`);
        
        // Clear cart and close modals
        cartItems = [];
        saveCart();
        updateCartCount();
        closeCheckout();
        
        // Reset form
        document.getElementById('checkout-form').reset();
      } else {
        throw new Error(result.message || 'Failed to place order');
      }
    } catch (error) {
      console.error('Error placing order:', error);
      alert(`Error placing order: ${error.message}. Please try again or contact us directly.`);
    } finally {
      // Restore button state
      const submitBtn = document.querySelector('.submit-order');
      submitBtn.textContent = 'Place Order';
      submitBtn.disabled = false;
    }
  });

  /***********************
   * CONTACT FORM HANDLING - MODIFIED FOR WEBHOOK
   ***********************/
  async function handleContactSubmit(e) {
    e.preventDefault();
    
    const name = document.getElementById('contact-name').value;
    const email = document.getElementById('contact-email').value;
    const message = document.getElementById('contact-message').value;
    
    const contactData = {
      name,
      email,
      message
    };
    
    try {
      // Show loading state
      const submitBtn = e.target.querySelector('button[type="submit"]');
      const originalText = submitBtn.textContent;
      submitBtn.textContent = 'Sending...';
      submitBtn.disabled = true;
      
      // Send contact data to webhook
      const response = await fetch(CONTACT_WEBHOOK_URL, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(contactData)
      });
      
      const result = await response.json();
      
      if (response.ok) {
        // Show success message from webhook response
        alert(result.message || `Thank you ${name}, we got your message and will reply on email soon!`);
        e.target.reset();
      } else {
        throw new Error(result.message || 'Failed to send message');
      }
    } catch (error) {
      console.error('Error sending message:', error);
      alert(`Error sending message: ${error.message}. Please try again or contact us directly.`);
    } finally {
      // Restore button state
      const submitBtn = e.target.querySelector('button[type="submit"]');
      submitBtn.textContent = 'Send Message';
      submitBtn.disabled = false;
    }
  }

  /***********************
   * UTILITY FUNCTIONS
   ***********************/
  function escapeHtml(text) {
    const map = {
      '&': '&amp;',
      '<': '&lt;',
      '>': '&gt;',
      '"': '&quot;',
      "'": '&#039;'
    };
    return text.replace(/[&<>"']/g, function(m) { return map[m]; });
  }
</script>
<script>
  // Floating cart button functionality
  const floatingCartBtn = document.getElementById('floating-cart-btn');
  const floatingCartCount = document.getElementById('floating-cart-count');
  
  // Show/hide floating cart button on scroll
  window.addEventListener('scroll', function() {
    if (window.scrollY > 300) {
      floatingCartBtn.classList.add('visible');
    } else {
      floatingCartBtn.classList.remove('visible');
    }
  });
  
  // Update floating cart count
  function updateCartCount() {
    const cartCount = cartItems.reduce((s,i) => s + i.quantity, 0);
    document.getElementById('cart-count').textContent = cartCount;
    floatingCartCount.textContent = cartCount;
  }
</script>
</body>
</html>
