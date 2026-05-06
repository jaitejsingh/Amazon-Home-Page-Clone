# Amazon-Home-Page-Clone
A clone of home page of amazon website without functionality using only html and css. 


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Amazon Clone</title>
  <link href="https://fonts.googleapis.com/css2?family=Ember:wght@400;700&family=Source+Sans+3:wght@300;400;600;700&display=swap" rel="stylesheet"/>
  <style>
    
    :root {
      --amazon-dark:    #131921;
      --amazon-mid:     #232f3e;
      --amazon-orange:  #febd69;
      --amazon-orange2: #f90;
      --amazon-blue:    #37475a;
      --amazon-light:   #eaeded;
      --amazon-white:   #ffffff;
      --amazon-red:     #cc0c39;
      --text-main:      #0f1111;
      --text-muted:     #565959;
      --border:         #d5d9d9;
      --card-shadow:    0 2px 8px rgba(0,0,0,0.12);
      --radius:         4px;
      --font-main:      'Source Sans 3', 'Arial', sans-serif;
    }

    
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: var(--font-main);
      font-size: 14px;
      color: var(--text-main);
      background: var(--amazon-light);
      min-width: 320px;
    }
    a { text-decoration: none; color: inherit; }
    ul { list-style: none; }
    img { display: block; max-width: 100%; }

    
    .navbar {
      background: var(--amazon-dark);
      color: var(--amazon-white);
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 6px 12px;
      position: sticky;
      top: 0;
      z-index: 1000;
      min-height: 60px;
    }

   
    .nav-logo {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 6px 8px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      transition: border-color .15s;
    }
    .nav-logo:hover { border-color: var(--amazon-white); }
    .nav-logo .logo-img {
      font-size: 22px;
      font-weight: 900;
      letter-spacing: -1px;
      color: var(--amazon-white);
      line-height: 1;
    }
    .nav-logo .logo-img span { color: var(--amazon-orange2); }
    .nav-logo .logo-country {
      font-size: 10px;
      color: var(--amazon-white);
      letter-spacing: .5px;
      margin-top: 1px;
    }

    
    .nav-deliver {
      display: flex;
      flex-direction: column;
      padding: 4px 8px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      white-space: nowrap;
      transition: border-color .15s;
    }
    .nav-deliver:hover { border-color: var(--amazon-white); }
    .nav-deliver .deliver-top { font-size: 11px; color: #ccc; }
    .nav-deliver .deliver-bot { font-size: 13px; font-weight: 700; }
    .nav-deliver .pin-icon { display: inline-block; margin-right: 3px; }

    
    .nav-search {
      flex: 1;
      display: flex;
      height: 40px;
      min-width: 180px;
    }
    .search-category {
      background: #f3f3f3;
      border: none;
      border-radius: var(--radius) 0 0 var(--radius);
      padding: 0 8px;
      font-size: 12px;
      color: var(--text-main);
      cursor: pointer;
      border-right: 1px solid var(--border);
      white-space: nowrap;
    }
    .search-input {
      flex: 1;
      border: none;
      padding: 0 12px;
      font-size: 15px;
      outline: none;
      color: var(--text-main);
    }
    .search-btn {
      background: var(--amazon-orange);
      border: none;
      border-radius: 0 var(--radius) var(--radius) 0;
      padding: 0 14px;
      cursor: pointer;
      font-size: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background .15s;
    }
    .search-btn:hover { background: var(--amazon-orange2); }

   
    .nav-right { display: flex; align-items: center; gap: 4px; margin-left: auto; }
    .nav-item {
      display: flex;
      flex-direction: column;
      padding: 4px 8px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      white-space: nowrap;
      transition: border-color .15s;
    }
    .nav-item:hover { border-color: var(--amazon-white); }
    .nav-item .item-top { font-size: 11px; color: #ccc; }
    .nav-item .item-bot { font-size: 13px; font-weight: 700; }

    .nav-cart {
      display: flex;
      align-items: center;
      gap: 3px;
      padding: 4px 8px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      transition: border-color .15s;
      position: relative;
    }
    .nav-cart:hover { border-color: var(--amazon-white); }
    .cart-icon { font-size: 30px; line-height: 1; position: relative; }
    .cart-count {
      position: absolute;
      top: -2px;
      right: 22px;
      background: var(--amazon-orange2);
      color: var(--amazon-dark);
      border-radius: 50%;
      font-size: 12px;
      font-weight: 800;
      width: 18px;
      height: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .cart-label { font-size: 13px; font-weight: 700; }

    
    .subnav {
      background: var(--amazon-blue);
      color: var(--amazon-white);
      display: flex;
      align-items: center;
      padding: 0 10px;
      height: 38px;
      gap: 2px;
      overflow-x: auto;
      scrollbar-width: none;
    }
    .subnav::-webkit-scrollbar { display: none; }
    .subnav-all {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 6px 10px;
      font-weight: 700;
      font-size: 13px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      white-space: nowrap;
      transition: border-color .15s;
    }
    .subnav-all:hover { border-color: var(--amazon-white); }
    .subnav-link {
      padding: 6px 10px;
      font-size: 13px;
      border: 1.5px solid transparent;
      border-radius: var(--radius);
      cursor: pointer;
      white-space: nowrap;
      transition: border-color .15s;
    }
    .subnav-link:hover { border-color: var(--amazon-white); }

    
    .promo-bar {
      background: #232f3e;
      color: var(--amazon-white);
      text-align: center;
      padding: 8px 16px;
      font-size: 13px;
      letter-spacing: .3px;
    }
    .promo-bar a { color: var(--amazon-orange); font-weight: 600; margin-left: 8px; }
    .promo-bar a:hover { text-decoration: underline; }

    
    .hero {
      position: relative;
      width: 100%;
      overflow: hidden;
      background: linear-gradient(135deg, #c8e6c9 0%, #b3d9e8 50%, #d4c5e2 100%);
      min-height: 340px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .hero-inner {
      max-width: 1500px;
      margin: 0 auto;
      width: 100%;
      position: relative;
    }
    .hero-slide {
      width: 100%;
      height: 340px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(120deg, #1a3a4a 0%, #0d5a70 40%, #16a085 100%);
      position: relative;
      overflow: hidden;
    }
    .hero-content {
      z-index: 2;
      color: white;
      text-align: center;
      padding: 24px;
    }
    .hero-content .badge {
      background: var(--amazon-orange2);
      color: var(--amazon-dark);
      font-size: 11px;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      padding: 4px 12px;
      border-radius: 2px;
      display: inline-block;
      margin-bottom: 14px;
    }
    .hero-content h1 {
      font-size: clamp(28px, 5vw, 52px);
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 10px;
      text-shadow: 0 2px 10px rgba(0,0,0,.25);
    }
    .hero-content p {
      font-size: 16px;
      opacity: .9;
      margin-bottom: 22px;
    }
    .hero-btn {
      background: var(--amazon-orange2);
      color: var(--amazon-dark);
      padding: 12px 32px;
      border-radius: 2px;
      font-size: 15px;
      font-weight: 700;
      display: inline-block;
      cursor: pointer;
      transition: background .15s, transform .1s;
      border: none;
    }
    .hero-btn:hover { background: var(--amazon-orange); transform: translateY(-1px); }

    
    .hero-blob {
      position: absolute;
      border-radius: 50%;
      opacity: .15;
    }
    .blob1 { width: 300px; height: 300px; background: #fff; top: -80px; right: 100px; }
    .blob2 { width: 200px; height: 200px; background: var(--amazon-orange); bottom: -60px; left: 60px; }

    /* Hero arrows */
    .hero-arrow {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(255,255,255,.6);
      border: none;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      font-size: 20px;
      cursor: pointer;
      z-index: 10;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background .15s;
    }
    .hero-arrow:hover { background: rgba(255,255,255,.9); }
    .hero-arrow.left { left: 10px; }
    .hero-arrow.right { right: 10px; }

    /* ─── MAIN CONTENT WRAPPER ──────────────────────── */
    .main-content {
      max-width: 1500px;
      margin: 0 auto;
      padding: 16px 12px;
    }

    /* ─── PRODUCT CARD GRID ─────────────────────────── */
    .section-title {
      font-size: 21px;
      font-weight: 700;
      color: var(--text-main);
      margin-bottom: 14px;
      padding-left: 2px;
    }

    .cards-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
      margin-bottom: 24px;
    }

    .product-card {
      background: var(--amazon-white);
      border-radius: var(--radius);
      box-shadow: var(--card-shadow);
      padding: 16px;
      cursor: pointer;
      transition: box-shadow .2s, transform .15s;
      overflow: hidden;
    }
    .product-card:hover {
      box-shadow: 0 6px 20px rgba(0,0,0,.18);
      transform: translateY(-2px);
    }
    .product-card .card-title {
      font-size: 15px;
      font-weight: 700;
      margin-bottom: 12px;
      color: var(--text-main);
    }
    .card-img-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
      margin-bottom: 12px;
    }
    .card-img-grid .img-box {
      background: var(--amazon-light);
      border-radius: 2px;
      aspect-ratio: 1;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 38px;
    }
    .card-img-grid .img-box.large {
      grid-column: 1 / -1;
      aspect-ratio: 2/1;
      font-size: 60px;
    }
    .card-img-single .img-box {
      background: var(--amazon-light);
      border-radius: 2px;
      width: 100%;
      aspect-ratio: 4/3;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 70px;
      margin-bottom: 12px;
    }
    .card-cta {
      font-size: 13px;
      color: #007185;
      font-weight: 500;
    }
    .card-cta:hover { color: #c7511f; text-decoration: underline; }

    /* ─── DEALS ROW ─────────────────────────────────── */
    .deals-row {
      background: var(--amazon-white);
      border-radius: var(--radius);
      box-shadow: var(--card-shadow);
      padding: 18px 18px 8px;
      margin-bottom: 24px;
    }
    .deals-header {
      display: flex;
      align-items: baseline;
      gap: 14px;
      margin-bottom: 16px;
    }
    .deals-header .section-title { margin-bottom: 0; }
    .deals-see-all { font-size: 13px; color: #007185; cursor: pointer; }
    .deals-see-all:hover { color: #c7511f; text-decoration: underline; }

    .deals-scroll {
      display: flex;
      gap: 14px;
      overflow-x: auto;
      padding-bottom: 12px;
      scrollbar-width: thin;
      scrollbar-color: #ccc transparent;
    }
    .deal-item {
      min-width: 170px;
      flex-shrink: 0;
      cursor: pointer;
    }
    .deal-img {
      background: var(--amazon-light);
      border-radius: var(--radius);
      aspect-ratio: 1;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 52px;
      margin-bottom: 8px;
      transition: opacity .15s;
    }
    .deal-item:hover .deal-img { opacity: .85; }
    .deal-badge {
      background: var(--amazon-red);
      color: white;
      font-size: 10px;
      font-weight: 700;
      padding: 2px 6px;
      border-radius: 2px;
      display: inline-block;
      margin-bottom: 5px;
    }
    .deal-name { font-size: 13px; color: var(--text-main); margin-bottom: 3px; }
    .deal-price { font-size: 14px; font-weight: 700; color: var(--amazon-red); }
    .deal-old-price { font-size: 12px; color: var(--text-muted); text-decoration: line-through; }

    /* ─── WIDE PROMO BANNER ─────────────────────────── */
    .wide-promo {
      background: linear-gradient(90deg, #1a252f 0%, #2c3e50 50%, #1a252f 100%);
      border-radius: var(--radius);
      padding: 28px 36px;
      color: white;
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 24px;
      gap: 20px;
      box-shadow: var(--card-shadow);
      overflow: hidden;
      position: relative;
    }
    .wide-promo::before {
      content: '';
      position: absolute;
      right: -40px;
      top: -40px;
      width: 220px;
      height: 220px;
      background: var(--amazon-orange2);
      border-radius: 50%;
      opacity: .08;
    }
    .wide-promo-text h2 { font-size: 24px; font-weight: 800; margin-bottom: 6px; }
    .wide-promo-text p { font-size: 14px; opacity: .8; }
    .wide-promo-right { text-align: right; flex-shrink: 0; }
    .wide-promo-price { font-size: 13px; opacity: .7; }
    .wide-promo-amount { font-size: 32px; font-weight: 900; color: var(--amazon-orange2); line-height: 1; }
    .wide-promo-btn {
      background: var(--amazon-orange2);
      color: var(--amazon-dark);
      padding: 10px 24px;
      border-radius: 2px;
      font-size: 14px;
      font-weight: 700;
      display: inline-block;
      margin-top: 10px;
      cursor: pointer;
      transition: background .15s;
    }
    .wide-promo-btn:hover { background: var(--amazon-orange); }

    /* ─── BOTTOM GRID ───────────────────────────────── */
    .bottom-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 14px;
      margin-bottom: 32px;
    }
    .mini-card {
      background: var(--amazon-white);
      border-radius: var(--radius);
      box-shadow: var(--card-shadow);
      padding: 16px;
      cursor: pointer;
      transition: box-shadow .2s, transform .15s;
      overflow: hidden;
    }
    .mini-card:hover { box-shadow: 0 6px 20px rgba(0,0,0,.18); transform: translateY(-2px); }
    .mini-card .card-title { font-size: 15px; font-weight: 700; margin-bottom: 10px; }
    .mini-img {
      width: 100%;
      aspect-ratio: 4/3;
      background: var(--amazon-light);
      border-radius: 2px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 60px;
      margin-bottom: 10px;
    }
    .mini-card .card-cta { font-size: 12px; color: #007185; }

    /* ─── FOOTER ────────────────────────────────────── */
    .back-to-top {
      background: var(--amazon-blue);
      color: var(--amazon-white);
      text-align: center;
      padding: 14px;
      font-size: 13px;
      cursor: pointer;
      transition: background .15s;
    }
    .back-to-top:hover { background: #485769; }

    footer {
      background: var(--amazon-mid);
      color: var(--amazon-white);
      padding: 40px 20px 20px;
    }
    .footer-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 24px;
      max-width: 1200px;
      margin: 0 auto 30px;
    }
    .footer-col h3 {
      font-size: 15px;
      font-weight: 700;
      margin-bottom: 12px;
      color: var(--amazon-white);
    }
    .footer-col ul { display: flex; flex-direction: column; gap: 6px; }
    .footer-col ul li {
      font-size: 13px;
      color: #ccc;
      cursor: pointer;
      transition: color .15s;
    }
    .footer-col ul li:hover { color: var(--amazon-white); }

    .footer-divider {
      border: none;
      border-top: 1px solid #3d4f5c;
      max-width: 1200px;
      margin: 0 auto 24px;
    }

    .footer-bottom {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      max-width: 1200px;
      margin: 0 auto;
    }
    .footer-logo {
      font-size: 28px;
      font-weight: 900;
      letter-spacing: -1px;
      color: var(--amazon-white);
    }
    .footer-logo span { color: var(--amazon-orange2); }
    .footer-badges {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .badge-item {
      border: 1px solid #888;
      border-radius: var(--radius);
      padding: 5px 12px;
      font-size: 12px;
      color: #ccc;
      cursor: pointer;
      transition: border-color .15s, color .15s;
    }
    .badge-item:hover { border-color: var(--amazon-white); color: var(--amazon-white); }
    .footer-copy {
      font-size: 11px;
      color: #999;
      text-align: center;
    }
    .footer-links {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .footer-links a { font-size: 11px; color: #ccc; transition: color .15s; }
    .footer-links a:hover { color: var(--amazon-white); }

    /* ─── HOVER ANIMATIONS ──────────────────────────── */
    .product-card,
    .mini-card {
      animation: fadeInUp .35s ease both;
    }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ─── RESPONSIVE ────────────────────────────────── */
    @media (max-width: 1100px) {
      .cards-grid, .bottom-grid { grid-template-columns: repeat(3, 1fr); }
    }
    @media (max-width: 840px) {
      .cards-grid, .bottom-grid { grid-template-columns: repeat(2, 1fr); }
      .footer-grid { grid-template-columns: repeat(2, 1fr); }
      .nav-deliver, .nav-item:not(.nav-account) { display: none; }
      .wide-promo { flex-direction: column; text-align: center; }
      .wide-promo-right { text-align: center; }
    }
    @media (max-width: 560px) {
      .cards-grid, .bottom-grid { grid-template-columns: 1fr 1fr; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .hero-slide { height: 240px; }
      .hero-content h1 { font-size: 22px; }
      .navbar { padding: 6px 8px; }
    }
    @media (max-width: 400px) {
      .cards-grid, .bottom-grid { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr; }
    }

    /* ─── MISC UTILITIES ─────────────────────────────── */
    .sr-only {
      position: absolute; width: 1px; height: 1px;
      padding: 0; margin: -1px; overflow: hidden;
      clip: rect(0,0,0,0); white-space: nowrap; border: 0;
    }
  </style>
</head>
<body>

<!-- ══════════════════════════════════════════════════ -->
<!--  TOP NAVIGATION BAR                               -->
<!-- ══════════════════════════════════════════════════ -->
<header class="navbar">

  <!-- Logo -->
  <div class="nav-logo">
    <div class="logo-img">amazon<span>.</span>in</div>
  </div>

  <!-- Deliver to -->
  <div class="nav-deliver">
    <span class="deliver-top">Deliver to</span>
    <span class="deliver-bot"><span class="pin-icon">📍</span>Mumbai 400001</span>
  </div>

  <!-- Search bar -->
  <div class="nav-search">
    <select class="search-category" aria-label="Search category">
      <option>All</option>
      <option>Electronics</option>
      <option>Books</option>
      <option>Clothing</option>
      <option>Home</option>
      <option>Sports</option>
      <option>Toys</option>
      <option>Grocery</option>
    </select>
    <input class="search-input" type="text" placeholder="Search Amazon.in" aria-label="Search"/>
    <button class="search-btn" aria-label="Search">🔍</button>
  </div>

  <!-- Right items -->
  <div class="nav-right">
    <div class="nav-item">
      <span class="item-top">Hello, Sign in</span>
      <span class="item-bot">Account &amp; Lists ▾</span>
    </div>
    <div class="nav-item">
      <span class="item-top">Returns</span>
      <span class="item-bot">&amp; Orders</span>
    </div>
    <div class="nav-item">
      <span class="item-top">Today's</span>
      <span class="item-bot">Deals</span>
    </div>
    <div class="nav-cart">
      <span class="cart-icon">🛒</span>
      <span class="cart-count">3</span>
      <span class="cart-label">Cart</span>
    </div>
  </div>

</header>

<!-- ══════════════════════════════════════════════════ -->
<!--  SECONDARY NAVIGATION BAR                         -->
<!-- ══════════════════════════════════════════════════ -->
<nav class="subnav" aria-label="Category navigation">
  <div class="subnav-all">☰ All</div>
  <a class="subnav-link" href="#">Today's Deals</a>
  <a class="subnav-link" href="#">Customer Service</a>
  <a class="subnav-link" href="#">Registry</a>
  <a class="subnav-link" href="#">Gift Cards</a>
  <a class="subnav-link" href="#">Sell</a>
  <a class="subnav-link" href="#">Electronics</a>
  <a class="subnav-link" href="#">Fashion</a>
  <a class="subnav-link" href="#">Amazon Pay</a>
  <a class="subnav-link" href="#">Prime</a>
  <a class="subnav-link" href="#">Mobiles</a>
  <a class="subnav-link" href="#">Grocery</a>
  <a class="subnav-link" href="#">New Launches</a>
  <a class="subnav-link" href="#">Best Sellers</a>
</nav>

<!-- Promo bar -->
<div class="promo-bar">
  🚀 Great Indian Festival — Deals up to 80% off!
  <a href="#">Shop now →</a>
</div>

<!-- ══════════════════════════════════════════════════ -->
<!--  HERO BANNER                                      -->
<!-- ══════════════════════════════════════════════════ -->
<section class="hero" aria-label="Featured promotion">
  <div class="hero-inner">
    <div class="hero-slide">
      <div class="hero-blob blob1"></div>
      <div class="hero-blob blob2"></div>
      <button class="hero-arrow left" aria-label="Previous">‹</button>
      <div class="hero-content">
        <div class="badge">Limited Time Offer</div>
        <h1>Great Indian Festival</h1>
        <p>Up to 80% off on Electronics, Fashion, Grocery &amp; more</p>
        <button class="hero-btn">Shop Now</button>
      </div>
      <button class="hero-arrow right" aria-label="Next">›</button>
    </div>
  </div>
</section>

<!-- ══════════════════════════════════════════════════ -->
<!--  MAIN CONTENT                                     -->
<!-- ══════════════════════════════════════════════════ -->
<main class="main-content">

  <!-- ── Category / Product Cards Grid ── -->
  <h2 class="section-title">Shop by Category</h2>
  <div class="cards-grid">

    <!-- Electronics -->
    <div class="product-card">
      <div class="card-title">Electronics</div>
      <div class="card-img-grid">
        <div class="img-box">📱</div>
        <div class="img-box">💻</div>
        <div class="img-box">🎧</div>
        <div class="img-box">📷</div>
      </div>
      <a class="card-cta" href="#">See all offers →</a>
    </div>

    <!-- Fashion -->
    <div class="product-card">
      <div class="card-title">Fashion for Everyone</div>
      <div class="card-img-grid">
        <div class="img-box">👗</div>
        <div class="img-box">👟</div>
        <div class="img-box">👜</div>
        <div class="img-box">🧢</div>
      </div>
      <a class="card-cta" href="#">Shop fashion →</a>
    </div>

    <!-- Home & Kitchen -->
    <div class="product-card">
      <div class="card-title">Home &amp; Kitchen</div>
      <div class="card-img-grid">
        <div class="img-box">🛋️</div>
        <div class="img-box">🍳</div>
        <div class="img-box">🪴</div>
        <div class="img-box">🕯️</div>
      </div>
      <a class="card-cta" href="#">Shop home →</a>
    </div>

    <!-- Books -->
    <div class="product-card">
      <div class="card-title">Books &amp; Media</div>
      <div class="card-img-grid">
        <div class="img-box">📚</div>
        <div class="img-box">🎬</div>
        <div class="img-box">🎵</div>
        <div class="img-box">🎮</div>
      </div>
      <a class="card-cta" href="#">Browse books →</a>
    </div>

  </div>

  <!-- ── Today's Deals Horizontal Scroll ── -->
  <div class="deals-row">
    <div class="deals-header">
      <h2 class="section-title">Today's Deals</h2>
      <a class="deals-see-all" href="#">See all deals</a>
    </div>
    <div class="deals-scroll">

      <div class="deal-item">
        <div class="deal-img">📱</div>
        <span class="deal-badge">55% OFF</span>
        <div class="deal-name">Smartphone Pro Max</div>
        <div class="deal-price">₹18,999 <span class="deal-old-price">₹41,999</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">🎧</div>
        <span class="deal-badge">40% OFF</span>
        <div class="deal-name">Noise-Cancelling Buds</div>
        <div class="deal-price">₹2,199 <span class="deal-old-price">₹3,699</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">💻</div>
        <span class="deal-badge">30% OFF</span>
        <div class="deal-name">Laptop 15" FHD</div>
        <div class="deal-price">₹44,990 <span class="deal-old-price">₹64,990</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">⌚</div>
        <span class="deal-badge">60% OFF</span>
        <div class="deal-name">Smart Watch Series 5</div>
        <div class="deal-price">₹3,499 <span class="deal-old-price">₹8,999</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">📷</div>
        <span class="deal-badge">35% OFF</span>
        <div class="deal-name">DSLR Camera Kit</div>
        <div class="deal-price">₹28,499 <span class="deal-old-price">₹43,999</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">🖨️</div>
        <span class="deal-badge">25% OFF</span>
        <div class="deal-name">Inkjet Colour Printer</div>
        <div class="deal-price">₹5,999 <span class="deal-old-price">₹7,999</span></div>
      </div>

      <div class="deal-item">
        <div class="deal-img">🎮</div>
        <span class="deal-badge">20% OFF</span>
        <div class="deal-name">Gaming Controller</div>
        <div class="deal-price">₹2,399 <span class="deal-old-price">₹2,999</span></div>
      </div>

    </div>
  </div>

  <!-- ── Wide Promo Banner ── -->
  <div class="wide-promo">
    <div class="wide-promo-text">
      <h2>Prime Membership</h2>
      <p>Unlimited free delivery · Exclusive deals · Prime Video &amp; Music</p>
    </div>
    <div class="wide-promo-right">
      <div class="wide-promo-price">Starting at</div>
      <div class="wide-promo-amount">₹299<small style="font-size:16px;opacity:.7">/mo</small></div>
      <a class="wide-promo-btn" href="#">Try Prime Free</a>
    </div>
  </div>

  <!-- ── More Category Cards ── -->
  <h2 class="section-title">More to Explore</h2>
  <div class="bottom-grid">

    <div class="mini-card">
      <div class="card-title">Sports &amp; Outdoors</div>
      <div class="mini-img">⚽</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Toys &amp; Games</div>
      <div class="mini-img">🧸</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Grocery &amp; Gourmet</div>
      <div class="mini-img">🛒</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Health &amp; Beauty</div>
      <div class="mini-img">💄</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Automotive</div>
      <div class="mini-img">🚗</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Pet Supplies</div>
      <div class="mini-img">🐾</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Office Products</div>
      <div class="mini-img">🖊️</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

    <div class="mini-card">
      <div class="card-title">Baby Products</div>
      <div class="mini-img">🍼</div>
      <a class="card-cta" href="#">Shop now →</a>
    </div>

  </div>

</main>

<!-- ══════════════════════════════════════════════════ -->
<!--  FOOTER                                           -->
<!-- ══════════════════════════════════════════════════ -->
<div class="back-to-top" onclick="window.scrollTo({top:0,behavior:'smooth'})">
  ▲ Back to top
</div>

<footer>
  <div class="footer-grid">
    <div class="footer-col">
      <h3>Get to Know Us</h3>
      <ul>
        <li>About Amazon</li>
        <li>Careers</li>
        <li>Press Releases</li>
        <li>Amazon Science</li>
        <li>Amazon Cares</li>
      </ul>
    </div>
    <div class="footer-col">
      <h3>Make Money with Us</h3>
      <ul>
        <li>Sell on Amazon</li>
        <li>Sell under Amazon Accelerator</li>
        <li>Amazon Associates</li>
        <li>Fulfillment by Amazon</li>
        <li>Advertise Your Products</li>
      </ul>
    </div>
    <div class="footer-col">
      <h3>Amazon Payment Products</h3>
      <ul>
        <li>Amazon Pay</li>
        <li>Amazon Pay ICICI Credit Card</li>
        <li>Reload Your Balance</li>
        <li>Amazon Currency Converter</li>
        <li>Gift Cards</li>
      </ul>
    </div>
    <div class="footer-col">
      <h3>Let Us Help You</h3>
      <ul>
        <li>COVID-19 and Amazon</li>
        <li>Your Account</li>
        <li>Returns Centre</li>
        <li>100% Purchase Protection</li>
        <li>Amazon App Download</li>
        <li>Help</li>
      </ul>
    </div>
  </div>

  <hr class="footer-divider"/>

  <div class="footer-bottom">
    <div class="footer-logo">amazon<span>.</span>in</div>
    <div class="footer-badges">
      <div class="badge-item">🌐 English</div>
      <div class="badge-item">₹ INR — Indian Rupee</div>
      <div class="badge-item">🇮🇳 India</div>
    </div>
    <div class="footer-links">
      <a href="#">Conditions of Use &amp; Sale</a>
      <a href="#">Privacy Notice</a>
      <a href="#">Interest-Based Ads Notice</a>
    </div>
    <p class="footer-copy">© 1996–2026, Amazon.com, Inc. or its affiliates</p>
  </div>
</footer>

</body>
</html>
