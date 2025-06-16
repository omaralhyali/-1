<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="متجر إلكتروني متكامل لبيع الأجهزة الإلكترونية والكهربائية">
  <title>متجري الإلكتروني</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary-color: #0a3d62;
      --secondary-color: #3c6382;
      --accent-color: #27ae60;
      --light-color: #f5f7fa;
      --dark-color: #333;
      --danger-color: #e74c3c;
      --warning-color: #f39c12;
    }
    
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    
    html {
      scroll-behavior: smooth;
    }
    
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: var(--light-color);
      color: var(--dark-color);
      line-height: 1.6;
    }
    
    /* Header Styles */
    header {
      background-color: var(--primary-color);
      color: white;
      padding: 15px 20px;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .logo {
      font-size: 24px;
      font-weight: bold;
      display: flex;
      align-items: center;
    }
    
    .logo i {
      margin-left: 10px;
    }
    
    .auth-section {
      display: flex;
      align-items: center;
      gap: 15px;
    }
    
    .auth-buttons {
      display: flex;
      gap: 10px;
    }
    
    .auth-buttons button {
      padding: 8px 15px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      font-size: 14px;
      color: white;
      display: flex;
      align-items: center;
      gap: 5px;
    }
    
    .auth-google {
      background-color: #db4437;
    }
    
    .auth-facebook {
      background-color: #3b5998;
    }
    
    .auth-logout {
      background-color: var(--secondary-color);
    }
    
    #user-info {
      color: white;
      font-weight: bold;
      font-size: 14px;
      display: flex;
      align-items: center;
      gap: 10px;
    }
    
    .user-avatar {
      width: 35px;
      height: 35px;
      border-radius: 50%;
      object-fit: cover;
    }
    
    /* Navigation */
    nav {
      background-color: var(--secondary-color);
      padding: 10px 0;
    }
    
    .nav-links {
      display: flex;
      justify-content: center;
      list-style: none;
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
      flex-wrap: wrap;
    }
    
    .nav-links li {
      margin: 0 10px;
    }
    
    .nav-links a {
      color: white;
      text-decoration: none;
      padding: 5px 10px;
      border-radius: 5px;
      transition: background-color 0.3s;
      display: flex;
      align-items: center;
      gap: 5px;
    }
    
    .nav-links a:hover {
      background-color: rgba(255,255,255,0.1);
    }
    
    .nav-links i {
      font-size: 16px;
    }
    
    /* Main Content */
    .container {
      max-width: 1200px;
      margin: 20px auto;
      padding: 0 20px;
    }
    
    .section-title {
      text-align: center;
      color: var(--primary-color);
      margin-bottom: 30px;
      font-size: 28px;
      position: relative;
      padding-bottom: 10px;
    }
    
    .section-title::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 3px;
      background-color: var(--accent-color);
    }
    
    /* Dashboard Grid */
    .dashboard-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-bottom: 40px;
    }
    
    .dashboard-card {
      background-color: white;
      border-radius: 10px;
      padding: 25px 20px;
      text-align: center;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
      transition: all 0.3s ease;
      cursor: pointer;
    }
    
    .dashboard-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 5px 15px rgba(0,0,0,0.15);
    }
    
    .dashboard-card i {
      font-size: 40px;
      color: var(--primary-color);
      margin-bottom: 15px;
    }
    
    .dashboard-card h3 {
      margin: 10px 0;
      font-size: 20px;
      color: var(--primary-color);
    }
    
    .dashboard-card p {
      font-size: 15px;
      color: #555;
    }
    
    /* Products Section */
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 25px;
      margin-top: 30px;
    }
    
    .product-card {
      background: white;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
      transition: all 0.3s ease;
      position: relative;
    }
    
    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 5px 15px rgba(0,0,0,0.15);
    }
    
    .product-image {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
    
    .product-badge {
      position: absolute;
      top: 10px;
      left: 10px;
      background-color: var(--accent-color);
      color: white;
      padding: 3px 8px;
      border-radius: 3px;
      font-size: 12px;
      font-weight: bold;
    }
    
    .product-info {
      padding: 15px;
    }
    
    .product-title {
      font-size: 18px;
      margin-bottom: 10px;
      color: var(--primary-color);
    }
    
    .product-description {
      color: #666;
      font-size: 14px;
      margin-bottom: 15px;
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }
    
    .product-price {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 15px;
    }
    
    .price {
      font-weight: bold;
      color: var(--primary-color);
      font-size: 18px;
    }
    
    .old-price {
      text-decoration: line-through;
      color: #999;
      font-size: 14px;
      margin-left: 5px;
    }
    
    .add-to-cart {
      background-color: var(--accent-color);
      color: white;
      border: none;
      padding: 8px 15px;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 5px;
      transition: background-color 0.3s;
    }
    
    .add-to-cart:hover {
      background-color: #219653;
    }
    
    /* Cart Section */
    #cart {
      background-color: white;
      border-radius: 10px;
      padding: 25px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
      margin: 40px 0;
    }
    
    .cart-items {
      margin-bottom: 20px;
    }
    
    .cart-item {
      display: flex;
      border-bottom: 1px solid #eee;
      padding: 15px 0;
      align-items: center;
    }
    
    .cart-item-image {
      width: 80px;
      height: 80px;
      object-fit: cover;
      border-radius: 5px;
      margin-left: 15px;
    }
    
    .cart-item-details {
      flex: 1;
    }
    
    .cart-item-title {
      font-weight: bold;
      margin-bottom: 5px;
    }
    
    .cart-item-price {
      color: var(--primary-color);
      font-weight: bold;
    }
    
    .cart-item-quantity {
      display: flex;
      align-items: center;
      margin: 10px 0;
    }
    
    .quantity-btn {
      background-color: #eee;
      border: none;
      width: 30px;
      height: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      font-size: 16px;
    }
    
    .quantity-input {
      width: 50px;
      text-align: center;
      margin: 0 5px;
      border: 1px solid #ddd;
      border-radius: 3px;
      padding: 5px;
    }
    
    .remove-item {
      color: var(--danger-color);
      cursor: pointer;
      margin-right: 15px;
    }
    
    .cart-summary {
      border-top: 1px solid #eee;
      padding-top: 20px;
      text-align: left;
    }
    
    .summary-row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    
    .total {
      font-weight: bold;
      font-size: 18px;
      color: var(--primary-color);
    }
    
    .checkout-btn {
      background-color: var(--accent-color);
      color: white;
      border: none;
      padding: 12px 25px;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      font-size: 16px;
      margin-top: 20px;
      width: 100%;
      transition: background-color 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
    }
    
    .checkout-btn:hover {
      background-color: #219653;
    }
    
    /* Payment Section */
    .payment-methods {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      margin: 30px 0;
      justify-content: center;
    }
    
    .payment-method {
      border: 1px solid #ddd;
      border-radius: 8px;
      padding: 15px;
      width: 120px;
      text-align: center;
      cursor: pointer;
      transition: all 0.3s;
    }
    
    .payment-method:hover {
      border-color: var(--accent-color);
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    }
    
    .payment-method img {
      width: 60px;
      height: 40px;
      object-fit: contain;
      margin-bottom: 10px;
    }
    
    .payment-method.active {
      border-color: var(--accent-color);
      background-color: rgba(39, 174, 96, 0.1);
    }
    
    /* Orders Section */
    .orders-list {
      margin-top: 30px;
    }
    
    .order-card {
      background: white;
      border-radius: 10px;
      padding: 20px;
      margin-bottom: 20px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    }
    
    .order-header {
      display: flex;
      justify-content: space-between;
      border-bottom: 1px solid #eee;
      padding-bottom: 10px;
      margin-bottom: 15px;
    }
    
    .order-id {
      font-weight: bold;
      color: var(--primary-color);
    }
    
    .order-date {
      color: #666;
    }
    
    .order-status {
      padding: 3px 10px;
      border-radius: 3px;
      font-size: 12px;
      font-weight: bold;
    }
    
    .status-pending {
      background-color: #fff4e5;
      color: var(--warning-color);
    }
    
    .status-completed {
      background-color: #e6f7ee;
      color: var(--accent-color);
    }
    
    .status-cancelled {
      background-color: #fdecea;
      color: var(--danger-color);
    }
    
    .order-products {
      margin: 15px 0;
    }
    
    .order-product {
      display: flex;
      margin-bottom: 10px;
      padding-bottom: 10px;
      border-bottom: 1px dashed #eee;
    }
    
    .order-product:last-child {
      border-bottom: none;
    }
    
    .order-product-image {
      width: 60px;
      height: 60px;
      object-fit: cover;
      border-radius: 5px;
      margin-left: 15px;
    }
    
    .order-product-title {
      font-weight: bold;
      margin-bottom: 5px;
    }
    
    .order-summary {
      display: flex;
      justify-content: space-between;
      margin-top: 15px;
      padding-top: 15px;
      border-top: 1px solid #eee;
      font-weight: bold;
    }
    
    /* Footer */
    footer {
      background-color: var(--primary-color);
      color: white;
      text-align: center;
      padding: 30px 20px;
      margin-top: 50px;
    }
    
    .footer-content {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 30px;
      text-align: right;
    }
    
    .footer-column h3 {
      margin-bottom: 15px;
      font-size: 18px;
      position: relative;
      padding-bottom: 10px;
    }
    
    .footer-column h3::after {
      content: '';
      position: absolute;
      bottom: 0;
      right: 0;
      width: 40px;
      height: 2px;
      background-color: var(--accent-color);
    }
    
    .footer-links {
      list-style: none;
    }
    
    .footer-links li {
      margin-bottom: 10px;
    }
    
    .footer-links a {
      color: #ddd;
      text-decoration: none;
      transition: color 0.3s;
    }
    
    .footer-links a:hover {
      color: white;
    }
    
    .social-links {
      display: flex;
      gap: 15px;
      margin-top: 15px;
    }
    
    .social-links a {
      color: white;
      background-color: rgba(255,255,255,0.1);
      width: 40px;
      height: 40px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background-color 0.3s;
    }
    
    .social-links a:hover {
      background-color: var(--accent-color);
    }
    
    .copyright {
      margin-top: 30px;
      padding-top: 20px;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 14px;
    }
    
    /* Responsive Styles */
    @media (max-width: 768px) {
      header {
        flex-direction: column;
        gap: 15px;
      }
      
      .auth-section {
        width: 100%;
        justify-content: space-between;
      }
      
      .nav-links {
        justify-content: flex-start;
        overflow-x: auto;
        padding-bottom: 10px;
      }
      
      .nav-links::-webkit-scrollbar {
        height: 5px;
      }
      
      .nav-links::-webkit-scrollbar-thumb {
        background-color: rgba(255,255,255,0.3);
        border-radius: 5px;
      }
      
      .cart-item {
        flex-direction: column;
        align-items: flex-start;
      }
      
      .cart-item-image {
        margin-left: 0;
        margin-bottom: 10px;
      }
    }
    
    @media (max-width: 480px) {
      .auth-buttons {
        flex-direction: column;
        width: 100%;
      }
      
      .auth-buttons button {
        width: 100%;
        justify-content: center;
      }
      
      .dashboard-grid {
        grid-template-columns: 1fr;
      }
      
      .products-grid {
        grid-template-columns: 1fr;
      }
    }
    
    /* Utility Classes */
    .hidden {
      display: none !important;
    }
    
    .text-center {
      text-align: center;
    }
    
    .mt-20 {
      margin-top: 20px;
    }
    
    .mb-20 {
      margin-bottom: 20px;
    }
  </style>
</head>
<body>

<header>
  <div class="logo">
    <span>متجري الإلكتروني</span>
    <i class="fas fa-shopping-bag"></i>
  </div>
  
  <div class="auth-section">
    <div id="user-info" class="hidden">
      <img id="user-avatar" class="user-avatar" src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" alt="صورة المستخدم">
      <span id="user-name"></span>
      <button class="auth-logout" id="logout-btn">تسجيل خروج <i class="fas fa-sign-out-alt"></i></button>
    </div>
    
    <div class="auth-buttons" id="auth-buttons">
      <button class="auth-google" id="login-google">
        <i class="fab fa-google"></i> جيميل
      </button>
      <button class="auth-facebook" id="login-facebook">
        <i class="fab fa-facebook-f"></i> فيسبوك
      </button>
    </div>
  </div>
</header>

<nav>
  <ul class="nav-links">
    <li><a href="#home"><i class="fas fa-home"></i> الرئيسية</a></li>
    <li><a href="#products"><i class="fas fa-box-open"></i> المنتجات</a></li>
    <li><a href="#categories"><i class="fas fa-list"></i> الأقسام</a></li>
    <li><a href="#cart"><i class="fas fa-shopping-cart"></i> السلة</a></li>
    <li><a href="#orders"><i class="fas fa-clipboard-list"></i> الطلبات</a></li>
    <li><a href="#contact"><i class="fas fa-envelope"></i> اتصل بنا</a></li>
  </ul>
</nav>

<main class="container">
  <!-- الرئيسية -->
  <section id="home">
    <h2 class="section-title">مرحبًا بكم في متجرنا الإلكتروني</h2>
    
    <div class="dashboard-grid">
      <a href="#products" class="dashboard-card">
        <i class="fas fa-boxes"></i>
        <h3>تصفح المنتجات</h3>
        <p>اكتشف أحدث المنتجات لدينا بأسعار تنافسية</p>
      </a>
      
      <a href="#cart" class="dashboard-card">
        <i class="fas fa-shopping-cart"></i>
        <h3>سلة التسوق</h3>
        <p>إدارة مشترياتك وتتبع طلباتك</p>
      </a>
      
      <a href="#offers" class="dashboard-card">
        <i class="fas fa-tag"></i>
        <h3>العروض الخاصة</h3>
        <p>تصفح أحدث العروض والتخفيضات</p>
      </a>
      
      <a href="https://wa.me/9647701773303"target="_blank" class="dashboard-card">
        <i class="fab fa-whatsapp"></i>
        <h3>الدعم الفني</h3>
        <p>تواصل معنا عبر واتساب للاستفسارات</p>
      </a>
    </div>
  </section>
  
  <!-- المنتجات -->
  <section id="products" class="mt-20">
    <h2 class="section-title">منتجاتنا</h2>
    
    <div class="products-grid">
      <!-- Product 1 -->
      <div class="product-card">
        <span class="product-badge">جديد</span>
        <img src="https://images.unsplash.com/photo-1556656793-08538906a9f8?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="هاتف ذكي" class="product-image">
        <div class="product-info">
          <h3 class="product-title">هاتف ذكي - موديل 2023</h3>
          <p class="product-description">هاتف ذكي بمواصفات عالية مع شاشة 6.5 بوصة وكاميرا رباعية</p>
          <div class="product-price">
            <div>
              <span class="price">2,499 د.ع</span>
              <span class="old-price">2,999 ر.س</span>
            </div>
            <button class="add-to-cart">
              <i class="fas fa-cart-plus"></i> إضافة
            </button>
          </div>
        </div>
      </div>
      
      <!-- Product 2 -->
      <div class="product-card">
        <span class="product-badge">خصم 20%</span>
        <img src="https://images.unsplash.com/photo-1593642632823-8f785ba67e45?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="لابتوب" class="product-image">
        <div class="product-info">
          <h3 class="product-title">لابتوب - Core i7</h3>
          <p class="product-description">لابتوب بمعالج قوي وذاكرة 16 جيجا بايت مع قرص SSD سعة 512 جيجا</p>
          <div class="product-price">
            <div>
              <span class="price">4,299 ر.س</span>
              <span class="old-price">5,399 ر.س</span>
            </div>
            <button class="add-to-cart">
              <i class="fas fa-cart-plus"></i> إضافة
            </button>
          </div>
        </div>
      </div>
      
      <!-- Product 3 -->
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="سماعات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">سماعات لاسلكية</h3>
          <p class="product-description">سماعات بلوتوث مع تقنية إلغاء الضوضاء وعمر بطارية 30 ساعة</p>
          <div class="product-price">
            <div>
              <span class="price">599 ر.س</span>
            </div>
            <button class="add-to-cart">
              <i class="fas fa-cart-plus"></i> إضافة
            </button>
          </div>
        </div>
      </div>
      
      <!-- Product 4 -->
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="كاميرا" class="product-image">
        <div class="product-info">
          <h3 class="product-title">كاميرا رقمية</h3>
          <p class="product-description">كاميرا احترافية بدقة 24 ميجابكسل مع عدسات متعددة</p>
          <div class="product-price">
            <div>
              <span class="price">3,199 ر.س</span>
            </div>
            <button class="add-to-cart">
              <i class="fas fa-cart-plus"></i> إضافة
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- الأقسام -->
  <section id="categories" class="mt-20">
    <h2 class="section-title">أقسام المتجر</h2>
    
    <div class="products-grid">
      <!-- Category 1 -->
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="الهواتف" class="product-image">
        <div class="product-info">
          <h3 class="product-title">الهاتف وملحقاته</h3>
          <p class="product-description">أحدث الموديلات من الهواتف الذكية بجميع الماركات العالمية</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
      
      <!-- Category 2 -->
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1496181133206-80ce9b88a853?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="اللابتوبات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">لابتوبات</h3>
          <p class="product-description">أجهزة كمبيوتر محمولة بمواصفات متنوعة لجميع الاستخدامات</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
      
      <!-- Category 3 -->
      <div class="product-card">
        <img src="https://www.seder.ps/uc_files/image/resize/1200/600/app_files/custom-fields/image/613ij7gejal_ac_sl1500_jpg_170117212297171440985868.jpg?vsig=2a19c7ab34debcc1d1d818faf1cfd71d" alt="الأجهزة المنزلية" class="product-image">
        <div class="product-info">
          <h3 class="product-title">اجهزة متنوعة</h3>
          <p class="product-description">أجهزة كهربائية منزلية بجودة عالية وضمان ممتد</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
      
      <!-- Category 4 -->
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1550009158-9ebf69173e03?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="الاكسسوارات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">الاكسسوارات</h3>
          <p class="product-description">جميع اكسسوارات الأجهزة الإلكترونية بأسعار مناسبة</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
    
  
  
       <!-- category 5-->
      <div class="product-card">
        <img src="https://maharat-news.com/media/3810/solarpanels-cover-ar08092020.jpg" alt="الاكسسوارات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">خلايا الطاقة الشمسية</h3>
          <p class="product-description">مصادر الطاقة النظيفة هي خيارك الانسب مع متجري</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
	  
      <!-- Category 6-->
      <div class="product-card">
        <img src="https://www.ultra-vision.net/wp-content/uploads/2022/07/%D8%B4%D8%A7%D8%B4%D8%A9-led-660x330-1.webp" alt="الاكسسوارات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">شاشات تلفيزون</h3>
          <p class="product-description">شاشات متجري دقة عالية بمختلف الاحجام وانسب الاسعار</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
    
      <!-- Category 7-->
      <div class="product-card">
        <img src="https://img.pikbest.com/wp/202408/problem-solving-a-luminous-lightbulb-illuminating-dark-space-with-room-for-innovative-thinking-and-through-3d-rendering_9829941.jpg!w700wp" alt="الاكسسوارات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">كهربائيات انارة</h3>
          <p class="product-description">انارة بموديلات حديثة توافق الذوق وحداثة البناء</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
    
      <!-- Category 8-->
      <div class="product-card">
        <img src="https://cdn-eshop.jo.zain.com/images/thumbs/0054670_tp-link-ax1500-gigabit-wi-fi-6-router_600.webp" alt="الاكسسوارات" class="product-image">
        <div class="product-info">
          <h3 class="product-title">اجهزة اتصالات</h3>
          <p class="product-description">احدث واقوى اجهزة الاتصالات من المناشى العالمية</p>
          <div class="product-price">
            <button class="add-to-cart" style="width: 100%;">
              <i class="fas fa-eye"></i> تصفح القسم
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- سلة التسوق -->
  <section id="cart" class="mt-20">
    <h2 class="section-title">سلة التسوق</h2>
    
    <div id="cart-content">
      <div class="cart-empty text-center">
        <i class="fas fa-shopping-cart" style="font-size: 50px; color: #ccc; margin-bottom: 20px;"></i>
        <h3>سلة التسوق فارغة</h3>
        <p>لم تقم بإضافة أي منتجات إلى سلة التسوق بعد</p>
        <a href="#products" class="add-to-cart mt-20" style="display: inline-flex;">
          <i class="fas fa-arrow-left"></i> تصفح المنتجات
        </a>
      </div>
      
      <div class="cart-with-items hidden">
        <div class="cart-items">
          <!-- سيتم إضافة العناصر هنا عبر JavaScript -->
        </div>
        
        <div class="cart-summary">
          <div class="summary-row">
            <span>المجموع الفرعي:</span>
            <span id="subtotal">0 ر.س</span>
          </div>
          <div class="summary-row">
            <span>التوصيل:</span>
            <span id="shipping">25 ر.س</span>
          </div>
          <div class="summary-row total">
            <span>المجموع الكلي:</span>
            <span id="total">25 ر.س</span>
          </div>
          
          <button class="checkout-btn">
            <i class="fas fa-credit-card"></i> اتمام الشراء
          </button>
        </div>
      </div>
    </div>
  </section>
  
  <!-- طرق الدفع -->
  <section id="payment" class="mt-20 hidden">
    <h2 class="section-title">اختر طريقة الدفع</h2>
    
    <div class="payment-methods">
      <div class="payment-method active">
        <img src="C:\Users\عمر نبراس\Desktop\photo_٢٠٢٥-٠٦-١٦_٠٣-٣٧-٥٠" alt="زين كاش">
        <div>زين كاش</div>
      </div>
      
      <button type="submit" class="checkout-btn">
        <i class="fas fa-lock"></i> تأكيد الدفع
      </button>
    </form>
  </section>
  
  <!-- الطلبات -->
  <section id="orders" class="mt-20 hidden">
    <h2 class="section-title">طلباتي</h2>
    
    <div class="orders-list">
      <div class="order-card">
        <div class="order-header">
          <div>
            <!-- داخل قسم الطلبات -->
<section id="orders" class="mt-20">
  <h2 class="section-title">طلباتي</h2>
  
  <div class="orders-list">
    <!-- سيتم عرض الطلبات هنا ديناميكياً -->
  </div>
</section>
  </section>
  
  <!-- اتصل بنا -->
  <section id="contact" class="mt-20 hidden">
    <h2 class="section-title">اتصل بنا</h2>
    
    <div style="background: white; padding: 30px; border-radius: 10px; max-width: 800px; margin: 0 auto; box-shadow: 0 3px 10px rgba(0,0,0,0.1);">
      <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px;">
        <div>
          <h3 style="margin-bottom: 15px; color: var(--primary-color);">معلومات التواصل</h3>
          <div style="margin-bottom: 15px;">
            <div style="font-weight: bold; margin-bottom: 5px;"><i class="fas fa-phone" style="margin-left: 10px;"></i> الهاتف</div>
            <div>+9647701773303</div>
          </div>
          
          <div style="margin-bottom: 15px;">
            <div style="font-weight: bold; margin-bottom: 5px;"><i class="fas fa-envelope" style="margin-left: 10px;"></i> البريد الإلكتروني</div>
            <div>omarnebras1999@gmail.com</div>
          </div>
          
          <div style="margin-bottom: 15px;">
            <div style="font-weight: bold; margin-bottom: 5px;"><i class="fas fa-map-marker-alt" style="margin-left: 10px;"></i> العنوان</div>
            <div>جمهورية العراق /الموصل/حي الزهور</div>
          </div>
          
          <div style="margin-top: 20px;">
            <div style="font-weight: bold; margin-bottom: 10px;">وسائل التواصل الاجتماعي</div>
            <div style="display: flex; gap: 10px;">
              <a href="#" style="color: var(--primary-color); font-size: 20px;"><i class="fab fa-twitter"></i></a>
              <a href="#" style="color: var(--primary-color); font-size: 20px;"><i class="fab fa-instagram"></i></a>
              <a href="#" style="color: var(--primary-color); font-size: 20px;"><i class="fab fa-snapchat"></i></a>
              <a href="#" style="color: var(--primary-color); font-size: 20px;"><i class="fab fa-whatsapp"></i></a>
            </div>
          </div>
        </div>
        
        <div>
          <h3 style="margin-bottom: 15px; color: var(--primary-color);">أرسل رسالة</h3>
          <form>
            <div style="margin-bottom: 15px;">
              <input type="text" placeholder="الاسم الكامل" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px;">
            </div>
            
            <div style="margin-bottom: 15px;">
              <input type="email" placeholder="البريد الإلكتروني" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px;">
            </div>
            
            <div style="margin-bottom: 15px;">
              <input type="text" placeholder="الموضوع" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px;">
            </div>
            
            <div style="margin-bottom: 15px;">
              <textarea placeholder="الرسالة" rows="5" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px;"></textarea>
            </div>
            
            <button type="submit" class="add-to-cart" style="width: 100%;">
              <i class="fas fa-paper-plane"></i> إرسال الرسالة
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</main>

<footer>
  <div class="footer-content">
    <div class="footer-column">
      <h3>عن المتجر</h3>
      <p>متجرنا الإلكتروني يوفر أحدث المنتجات التقنية بأسعار تنافسية وخدمة توصيل سريعة لكافة أنحاء المملكة.</p>
    </div>
    
    <div class="footer-column">
      <h3>روابط سريعة</h3>
      <ul class="footer-links">
        <li><a href="#home">الرئيسية</a></li>
        <li><a href="#products">المنتجات</a></li>
        <li><a href="#categories">الأقسام</a></li>
        <li><a href="#cart">سلة التسوق</a></li>
        <li><a href="#contact">اتصل بنا</a></li>
      </ul>
    </div>
    
    <div class="footer-column">
      <h3>خدمة العملاء</h3>
      <ul class="footer-links">
        <li><a href="#">سياسة الإرجاع</a></li>
        <li><a href="#">أسئلة شائعة</a></li>
        <li><a href="#">شروط وأحكام</a></li>
        <li><a href="#">سياسة الخصوصية</a></li>
      </ul>
    </div>
    
    <div class="footer-column">
      <h3>اشترك في النشرة البريدية</h3>
      <p>اشترك لتصلك أحدث العروض والتخفيضات أولاً بأول</p>
      <form style="margin-top: 15px;">
        <input type="email" placeholder="بريدك الإلكتروني" style="width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px; margin-bottom: 10px;">
        <button type="submit" class="add-to-cart" style="width: 100%;">
          <i class="fas fa-envelope"></i> اشتراك
        </button>
      </form>
      
      <div class="social-links">
        <a href="#"><i class="fab fa-facebook-f"></i></a>
        <a href="#"><i class="fab fa-twitter"></i></a>
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-youtube"></i></a>
      </div>
    </div>
  </div>
  
  <div class="copyright">
    &copy; 2023 متجري الإلكتروني - جميع الحقوق محفوظة
  </div>
</footer>

<!-- Firebase SDK -->
<script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.22.1/firebase-auth-compat.js"></script>

<script>
  // إعداد Firebase (يجب استبدالها ببياناتك الخاصة)
  // Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyCZG2cUEowP8lYoAIp3F-nDe2efypCg4EE",
  authDomain: "project-3507391035839391122.firebaseapp.com",
  databaseURL: "https://project-3507391035839391122-default-rtdb.firebaseio.com",
  projectId: "project-3507391035839391122",
  storageBucket: "project-3507391035839391122.firebasestorage.app",
  messagingSenderId: "374189775027",
  appId: "1:374189775027:web:8a41e1bcf84f9a5c70f8c6",
  measurementId: "G-X2G7WSXN0C"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);

  // تهيئة Firebase
  firebase.initializeApp(firebaseConfig);
  const auth = firebase.auth();

  // مراجع لعناصر الواجهة
  const loginGoogleBtn = document.getElementById('login-google');
  const loginFacebookBtn = document.getElementById('login-facebook');
  const logoutBtn = document.getElementById('logout-btn');
  const authButtons = document.getElementById('auth-buttons');
  const userInfo = document.getElementById('user-info');
  const userNameSpan = document.getElementById('user-name');
  const userAvatar = document.getElementById('user-avatar');
  
  // متغيرات للتطبيق
  let cart = [];
  let currentSection = 'home';
  
  // تسجيل دخول جيميل
  loginGoogleBtn.addEventListener('click', () => {
    const provider = new firebase.auth.GoogleAuthProvider();
    auth.signInWithPopup(provider)
      .then((result) => {
        // تسجيل الدخول ناجح
        showUserInfo(result.user);
      })
      .catch((error) => {
        alert("حدث خطأ أثناء تسجيل الدخول بجيميل: " + error.message);
      });
  });

  // تسجيل دخول فيسبوك
  loginFacebookBtn.addEventListener('click', () => {
    const provider = new firebase.auth.FacebookAuthProvider();
    auth.signInWithPopup(provider)
      .then((result) => {
        // تسجيل الدخول ناجح
        showUserInfo(result.user);
      })
      .catch((error) => {
        alert("حدث خطأ أثناء تسجيل الدخول بفيسبوك: " + error.message);
      });
  });

  // تسجيل خروج
  logoutBtn.addEventListener('click', () => {
    auth.signOut()
      .then(() => {
        // تسجيل الخروج ناجح
        userInfo.classList.add('hidden');
        authButtons.classList.remove('hidden');
      })
      .catch((error) => {
        alert("حدث خطأ أثناء تسجيل الخروج: " + error.message);
      });
  });

  // عرض معلومات المستخدم
  function showUserInfo(user) {
    userInfo.classList.remove('hidden');
    authButtons.classList.add('hidden');
    
    userNameSpan.textContent = user.displayName || user.email || "المستخدم";
    
    if (user.photoURL) {
      userAvatar.src = user.photoURL;
    }
  }

  // مراقبة حالة تسجيل الدخول
  auth.onAuthStateChanged((user) => {
    if (user) {
      // مستخدم مسجل دخول
      showUserInfo(user);
      
      // جلب بيانات المستخدم من قاعدة البيانات إذا لزم الأمر
    } else {
      // لا يوجد مستخدم مسجل دخول
      userInfo.classList.add('hidden');
      authButtons.classList.remove('hidden');
    }
  });
  
  // إدارة أقسام الصفحة
  function showSection(sectionId) {
    // إخفاء جميع الأقسام
    document.querySelectorAll('main > section').forEach(section => {
      section.classList.add('hidden');
    });
    
    // إظهار القسم المطلوب
    document.getElementById(sectionId).classList.remove('hidden');
    currentSection = sectionId;
    
    // تحديث الروابط النشطة في القائمة
    updateActiveNavLink();
  }
  
  // تحديث الروابط النشطة في القائمة
  function updateActiveNavLink() {
    document.querySelectorAll('.nav-links a').forEach(link => {
      if (link.getAttribute('href') === `#${currentSection}`) {
        link.style.backgroundColor = 'rgba(255,255,255,0.2)';
      } else {
        link.style.backgroundColor = 'transparent';
      }
    });
  }
  
  // إضافة عناصر إلى السلة
  function addToCart(product) {
    // هنا يمكنك إضافة منطق إضافة المنتج إلى السلة
    console.log('تمت إضافة المنتج إلى السلة:', product);
    
    // عرض تنبيه
    alert('تمت إضافة المنتج إلى سلة التسوق');
    
    // تحديث عرض السلة
    updateCartDisplay();
  }
  
  // تحديث عرض السلة
  function updateCartDisplay() {
    // هنا يمكنك إضافة منطق تحديث عرض السلة
  }
  
  // التنقل بين الأقسام
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', (e) => {
      e.preventDefault();
      const sectionId = link.getAttribute('href').substring(1);
      showSection(sectionId);
      
      // Scroll to top
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });
  });
  
  // معالجة النقر على أزرار إضافة إلى السلة
  document.querySelectorAll('.add-to-cart').forEach(button => {
    if (!button.getAttribute('href')) {
      button.addEventListener('click', (e) => {
        e.preventDefault();
        
        // الحصول على معلومات المنتج
        const productCard = button.closest('.product-card');
        const productTitle = productCard.querySelector('.product-title').textContent;
        const productPrice = productCard.querySelector('.price').textContent;
        
        // إضافة المنتج إلى السلة
        addToCart({
          title: productTitle,
          price: productPrice,
          quantity: 1
        });
      });
    }
  });
  
  // معالجة النقر على زر اتمام الشراء
  document.querySelector('.checkout-btn')?.addEventListener('click', (e) => {
    e.preventDefault();
    showSection('payment');
  });
  
  // عند تحميل الصفحة، إظهار القسم الحالي
  window.addEventListener('load', () => {
    showSection(currentSection);
  });
</script>

</body>
</html>
