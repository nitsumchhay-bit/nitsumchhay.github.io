# nitsumchhay.github.io
<!DOCTYPE html>

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>LOOM — Minimal Clothing</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>

  <!-- Google Analytics — replace G-XXXXXXXXXX with your tracking ID -->

  <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>

  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
  </script>

  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #f7f5f2;
      --charcoal: #1a1a18;
      --warm-gray: #8a8580;
      --accent: #c9a96e;
      --light-line: #e8e4de;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--charcoal);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.4rem 3rem;
      background: rgba(247,245,242,0.92);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--light-line);
    }

    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.6rem;
      font-weight: 300;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--charcoal);
      text-decoration: none;
    }

    .nav-links {
      display: flex; gap: 2.5rem; list-style: none;
    }

    .nav-links a {
      font-size: 0.78rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--warm-gray);
      text-decoration: none;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--charcoal); }

    .nav-right {
      display: flex; align-items: center; gap: 1.4rem;
    }

    .cart-btn {
      font-size: 0.78rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--charcoal);
      text-decoration: none;
      padding: 0.5rem 1.2rem;
      border: 1px solid var(--charcoal);
      transition: all 0.25s;
    }

    .cart-btn:hover {
      background: var(--charcoal);
      color: var(--cream);
    }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 80px;
    }

    .hero-text {
      display: flex; flex-direction: column; justify-content: center;
      padding: 6rem 4rem 6rem 3rem;
      animation: fadeUp 1s ease both;
    }

    .hero-eyebrow {
      font-size: 0.72rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1.5rem;
    }

    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 5vw, 5.5rem);
      font-weight: 300;
      line-height: 1.05;
      margin-bottom: 1.8rem;
    }

    .hero-title em {
      font-style: italic;
      color: var(--warm-gray);
    }

    .hero-sub {
      font-size: 0.9rem;
      line-height: 1.8;
      color: var(--warm-gray);
      max-width: 340px;
      margin-bottom: 2.8rem;
    }

    .btn-primary {
      display: inline-block;
      padding: 0.9rem 2.5rem;
      background: var(--charcoal);
      color: var(--cream);
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      text-decoration: none;
      transition: background 0.25s, transform 0.2s;
      width: fit-content;
    }

    .btn-primary:hover {
      background: #333;
      transform: translateY(-1px);
    }

    .hero-image {
      position: relative;
      overflow: hidden;
      background: #e8e3db;
      animation: fadeIn 1.2s ease both 0.3s;
    }

    .hero-image img {
      width: 100%; height: 100%; object-fit: cover;
    }

    .hero-image-placeholder {
      width: 100%; height: 100%;
      display: flex; align-items: center; justify-content: center;
      flex-direction: column;
      gap: 1rem;
      color: var(--warm-gray);
    }

    .hero-image-placeholder svg {
      opacity: 0.3;
    }

    /* ── MARQUEE ── */
    .marquee-bar {
      border-top: 1px solid var(--light-line);
      border-bottom: 1px solid var(--light-line);
      overflow: hidden;
      padding: 0.85rem 0;
      background: var(--charcoal);
    }

    .marquee-track {
      display: flex; gap: 3rem;
      animation: marquee 20s linear infinite;
      white-space: nowrap;
    }

    .marquee-item {
      font-size: 0.72rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--cream);
      opacity: 0.7;
    }

    .marquee-dot {
      color: var(--accent);
      opacity: 1 !important;
    }

    /* ── SECTION HEADER ── */
    .section-header {
      text-align: center;
      padding: 5rem 2rem 3rem;
    }

    .section-eyebrow {
      font-size: 0.72rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1rem;
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 3.5vw, 3rem);
      font-weight: 300;
    }

    /* ── PRODUCTS GRID ── */
    .products {
      padding: 0 3rem 6rem;
      max-width: 1400px;
      margin: 0 auto;
    }

    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 2.5rem;
    }

    .product-card {
      cursor: pointer;
      animation: fadeUp 0.7s ease both;
    }

    .product-card:nth-child(2) { animation-delay: 0.1s; }
    .product-card:nth-child(3) { animation-delay: 0.2s; }
    .product-card:nth-child(4) { animation-delay: 0.3s; }
    .product-card:nth-child(5) { animation-delay: 0.4s; }
    .product-card:nth-child(6) { animation-delay: 0.5s; }

    .product-image {
      position: relative;
      overflow: hidden;
      aspect-ratio: 3/4;
      background: #ede9e2;
      margin-bottom: 1.2rem;
    }

    .product-image img {
      width: 100%; height: 100%; object-fit: cover;
      transition: transform 0.6s ease;
    }

    .product-card:hover .product-image img {
      transform: scale(1.04);
    }

    .product-image-placeholder {
      width: 100%; height: 100%;
      display: flex; align-items: center; justify-content: center;
      color: var(--warm-gray);
      opacity: 0.4;
      transition: transform 0.6s ease;
    }

    .product-card:hover .product-image-placeholder {
      transform: scale(1.04);
    }

    .product-tag {
      position: absolute; top: 1rem; left: 1rem;
      font-size: 0.65rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 0.3rem 0.7rem;
      background: var(--charcoal);
      color: var(--cream);
    }

    .product-tag.sale {
      background: var(--accent);
      color: var(--charcoal);
    }

    .product-add {
      position: absolute; bottom: 0; left: 0; right: 0;
      padding: 0.8rem;
      background: var(--charcoal);
      color: var(--cream);
      font-size: 0.72rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      text-align: center;
      transform: translateY(100%);
      transition: transform 0.3s ease;
      border: none; cursor: pointer; width: 100%;
    }

    .product-card:hover .product-add {
      transform: translateY(0);
    }

    .product-name {
      font-size: 0.9rem;
      font-weight: 400;
      margin-bottom: 0.4rem;
    }

    .product-category {
      font-size: 0.75rem;
      color: var(--warm-gray);
      letter-spacing: 0.08em;
      margin-bottom: 0.6rem;
    }

    .product-price {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.15rem;
      font-weight: 300;
    }

    .product-price .original {
      text-decoration: line-through;
      color: var(--warm-gray);
      margin-right: 0.5rem;
      font-size: 0.95rem;
    }

    /* ── BANNER ── */
    .banner {
      margin: 2rem 3rem 6rem;
      background: var(--charcoal);
      color: var(--cream);
      display: grid;
      grid-template-columns: 1fr 1fr;
      min-height: 360px;
    }

    .banner-text {
      display: flex; flex-direction: column; justify-content: center;
      padding: 4rem;
    }

    .banner-eyebrow {
      font-size: 0.72rem;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1.2rem;
    }

    .banner-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 3vw, 3rem);
      font-weight: 300;
      line-height: 1.1;
      margin-bottom: 1.5rem;
    }

    .btn-outline {
      display: inline-block;
      padding: 0.8rem 2rem;
      border: 1px solid var(--cream);
      color: var(--cream);
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      text-decoration: none;
      width: fit-content;
      transition: all 0.25s;
    }

    .btn-outline:hover {
      background: var(--cream);
      color: var(--charcoal);
    }

    .banner-image {
      background: #2a2a28;
      display: flex; align-items: center; justify-content: center;
      color: #444; font-size: 0.8rem; letter-spacing: 0.1em;
    }

    /* ── FOOTER ── */
    footer {
      border-top: 1px solid var(--light-line);
      padding: 4rem 3rem 2rem;
    }

    .footer-top {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 3rem;
      margin-bottom: 3rem;
    }

    .footer-brand .nav-logo {
      display: block; margin-bottom: 1rem;
    }

    .footer-brand p {
      font-size: 0.82rem;
      line-height: 1.8;
      color: var(--warm-gray);
      max-width: 260px;
    }

    .footer-col h4 {
      font-size: 0.72rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 1.2rem;
    }

    .footer-col ul {
      list-style: none;
      display: flex; flex-direction: column; gap: 0.7rem;
    }

    .footer-col a {
      font-size: 0.82rem;
      color: var(--warm-gray);
      text-decoration: none;
      transition: color 0.2s;
    }

    .footer-col a:hover { color: var(--charcoal); }

    .footer-bottom {
      display: flex; align-items: center; justify-content: space-between;
      padding-top: 2rem;
      border-top: 1px solid var(--light-line);
      font-size: 0.75rem;
      color: var(--warm-gray);
    }

    /* ── TOAST ── */
    .toast {
      position: fixed; bottom: 2rem; right: 2rem;
      background: var(--charcoal);
      color: var(--cream);
      padding: 0.9rem 1.8rem;
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      transform: translateY(120%);
      transition: transform 0.35s ease;
      z-index: 200;
    }

    .toast.show { transform: translateY(0); }

    /* ── CART DRAWER ── */
    .cart-overlay {
      position: fixed; inset: 0;
      background: rgba(26,26,24,0.5);
      opacity: 0; pointer-events: none;
      transition: opacity 0.3s;
      z-index: 150;
    }

    .cart-overlay.open { opacity: 1; pointer-events: all; }

    .cart-drawer {
      position: fixed; top: 0; right: 0; bottom: 0;
      width: 380px;
      background: var(--cream);
      transform: translateX(100%);
      transition: transform 0.4s ease;
      z-index: 151;
      display: flex; flex-direction: column;
      padding: 2rem;
    }

    .cart-drawer.open { transform: translateX(0); }

    .cart-header {
      display: flex; align-items: center; justify-content: space-between;
      margin-bottom: 2rem;
      padding-bottom: 1rem;
      border-bottom: 1px solid var(--light-line);
    }

    .cart-header h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem; font-weight: 300;
    }

    .cart-close {
      background: none; border: none; cursor: pointer;
      font-size: 1.4rem; color: var(--warm-gray);
    }

    .cart-items { flex: 1; overflow-y: auto; }

    .cart-empty {
      text-align: center; padding: 4rem 2rem;
      color: var(--warm-gray); font-size: 0.85rem;
    }

    .cart-item {
      display: flex; gap: 1rem; margin-bottom: 1.5rem;
      padding-bottom: 1.5rem;
      border-bottom: 1px solid var(--light-line);
    }

    .cart-item-img {
      width: 70px; height: 90px;
      background: #ede9e2;
      flex-shrink: 0;
      display: flex; align-items: center; justify-content: center;
      color: var(--warm-gray); font-size: 0.65rem;
    }

    .cart-item-info { flex: 1; }
    .cart-item-name { font-size: 0.85rem; margin-bottom: 0.3rem; }
    .cart-item-price { font-size: 0.8rem; color: var(--warm-gray); }

    .cart-item-remove {
      background: none; border: none; cursor: pointer;
      color: var(--warm-gray); font-size: 1rem;
      align-self: flex-start;
    }

    .cart-footer {
      padding-top: 1.5rem;
      border-top: 1px solid var(--light-line);
    }

    .cart-total {
      display: flex; justify-content: space-between;
      margin-bottom: 1.5rem;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
    }

    .btn-checkout {
      width: 100%;
      padding: 1rem;
      background: var(--charcoal);
      color: var(--cream);
      border: none; cursor: pointer;
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      transition: background 0.25s;
    }

    .btn-checkout:hover { background: #333; }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }

    @keyframes marquee {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }

    /* ── MOBILE ── */
    @media (max-width: 768px) {
      nav { padding: 1.2rem 1.5rem; }
      .nav-links { display: none; }

      .hero { grid-template-columns: 1fr; min-height: auto; }
      .hero-text { padding: 4rem 1.5rem 2rem; }
      .hero-image { min-height: 55vw; }

      .products { padding: 0 1.5rem 4rem; }
      .products-grid { grid-template-columns: repeat(2, 1fr); gap: 1.2rem; }

      .banner { grid-template-columns: 1fr; margin: 2rem 1.5rem; }
      .banner-image { display: none; }
      .banner-text { padding: 3rem 2rem; }

      .footer-top { grid-template-columns: 1fr 1fr; gap: 2rem; }
      footer { padding: 3rem 1.5rem 2rem; }

      .cart-drawer { width: 100%; }
    }
  </style>

</head>
<body>

<!-- NAV -->

<nav>
  <a class="nav-logo" href="#">Loom</a>
  <ul class="nav-links">
    <li><a href="#products">Shop</a></li>
    <li><a href="#">Collections</a></li>
    <li><a href="#">About</a></li>
  </ul>
  <div class="nav-right">
    <a class="cart-btn" href="#" onclick="openCart(); return false;">Bag (<span id="cart-count">0</span>)</a>
  </div>
</nav>

<!-- HERO -->

<section class="hero">
  <div class="hero-text">
    <p class="hero-eyebrow">New Collection · Spring 2025</p>
    <h1 class="hero-title">Wear Less,<br><em>Mean More.</em></h1>
    <p class="hero-sub">Timeless pieces designed for the unhurried. Every garment woven with intention, made to last beyond the season.</p>
    <a class="btn-primary" href="#products">Shop the Collection</a>
  </div>
  <div class="hero-image">
    <img src="https://images.unsplash.com/photo-1469334031218-e382a71b716b?w=1200&q=80&fit=crop" alt="Minimal clothing hero" loading="eager"/>
  </div>
</section>

<!-- MARQUEE -->

<div class="marquee-bar">
  <div class="marquee-track" id="marquee-track"></div>
</div>

<!-- PRODUCTS -->

<section id="products">
  <div class="section-header">
    <p class="section-eyebrow">Curated Essentials</p>
    <h2 class="section-title">The Collection</h2>
  </div>

  <div class="products" id="products-grid"></div>
</section>

<!-- BANNER -->

<div class="banner">
  <div class="banner-text">
    <p class="banner-eyebrow">Limited Edition</p>
    <h2 class="banner-title">The Linen<br>Summer Edit</h2>
    <a class="btn-outline" href="#">Explore Now</a>
  </div>
  <div class="banner-image" style="overflow:hidden;">
    <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?w=900&q=80&fit=crop" alt="Summer linen collection" style="width:100%;height:100%;object-fit:cover;opacity:0.6;"/>
  </div>
</div>

<!-- FOOTER -->

<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <a class="nav-logo" href="#">Loom</a>
      <p>Minimal clothing for considered living. Crafted from natural fibres, designed to endure.</p>
    </div>
    <div class="footer-col">
      <h4>Shop</h4>
      <ul>
        <li><a href="#">New In</a></li>
        <li><a href="#">Tops</a></li>
        <li><a href="#">Bottoms</a></li>
        <li><a href="#">Outerwear</a></li>
        <li><a href="#">Accessories</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Help</h4>
      <ul>
        <li><a href="#">Sizing Guide</a></li>
        <li><a href="#">Shipping</a></li>
        <li><a href="#">Returns</a></li>
        <li><a href="#">FAQ</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a href="#">About</a></li>
        <li><a href="#">Sustainability</a></li>
        <li><a href="#">Contact</a></li>
        <li><a href="#">Instagram</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 Loom. All rights reserved.</span>
    <span>School Project — Not a real store</span>
  </div>
</footer>

<!-- TOAST -->

<div class="toast" id="toast"></div>

<!-- CART OVERLAY + DRAWER -->

<div class="cart-overlay" id="cart-overlay" onclick="closeCart()"></div>
<div class="cart-drawer" id="cart-drawer">
  <div class="cart-header">
    <h3>Your Bag</h3>
    <button class="cart-close" onclick="closeCart()">×</button>
  </div>
  <div class="cart-items" id="cart-items">
    <div class="cart-empty">Your bag is empty.</div>
  </div>
  <div class="cart-footer">
    <div class="cart-total">
      <span>Total</span>
      <span id="cart-total">$0.00</span>
    </div>
    <button class="cart-checkout" class="btn-checkout" style="width:100%;padding:1rem;background:var(--charcoal);color:var(--cream);border:none;cursor:pointer;font-size:0.78rem;letter-spacing:0.18em;text-transform:uppercase;" onclick="showToast('Checkout coming soon!')">Checkout</button>
  </div>
</div>

<script>
  // ── DATA ──
  const products = [
    { id:1, name:'Oversized Linen Shirt', category:'Tops', price:89, tag:'New',
      img:'https://images.unsplash.com/photo-1596755094514-f87e34085b2c?w=600&q=80&fit=crop' },
    { id:2, name:'Wide-Leg Trousers', category:'Bottoms', price:115, originalPrice:145, tag:'Sale',
      img:'https://images.unsplash.com/photo-1509551388413-e18d0ac5d495?w=600&q=80&fit=crop' },
    { id:3, name:'Ribbed Cotton Tee', category:'Tops', price:45,
      img:'https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?w=600&q=80&fit=crop' },
    { id:4, name:'Structured Blazer', category:'Outerwear', price:210, tag:'New',
      img:'https://images.unsplash.com/photo-1591085686350-798c0f9faa7f?w=600&q=80&fit=crop' },
    { id:5, name:'Linen Midi Skirt', category:'Bottoms', price:95,
      img:'https://images.unsplash.com/photo-1583496661160-fb5886a0aaaa?w=600&q=80&fit=crop' },
    { id:6, name:'Washed Denim Jacket', category:'Outerwear', price:175, originalPrice:220,
      img:'https://images.unsplash.com/photo-1544441893-675973e31985?w=600&q=80&fit=crop' },
  ];

  // ── MARQUEE ──
  const marqueeItems = ['Free shipping over $150','New linen collection','Sustainable fabrics','30-day returns','Responsibly made'];
  const track = document.getElementById('marquee-track');
  [...marqueeItems, ...marqueeItems].forEach((item, i) => {
    const span = document.createElement('span');
    span.className = 'marquee-item';
    span.textContent = item;
    track.appendChild(span);
    if (i < marqueeItems.length * 2 - 1) {
      const dot = document.createElement('span');
      dot.className = 'marquee-item marquee-dot';
      dot.textContent = '·';
      track.appendChild(dot);
    }
  });

  // ── RENDER PRODUCTS ──
  const grid = document.getElementById('products-grid');
  const inner = document.createElement('div');
  inner.className = 'products-grid';

  products.forEach(p => {
    const card = document.createElement('div');
    card.className = 'product-card';
    card.innerHTML = `
      <div class="product-image">
        <img src="${p.img}" alt="${p.name}" loading="lazy"/>
        ${p.tag ? `<span class="product-tag ${p.tag === 'Sale' ? 'sale' : ''}">${p.tag}</span>` : ''}
        <button class="product-add" onclick="addToCart(${p.id})">Add to Bag</button>
      </div>
      <p class="product-name">${p.name}</p>
      <p class="product-category">${p.category}</p>
      <p class="product-price">
        ${p.originalPrice ? `<span class="original">$${p.originalPrice}</span>` : ''}
        $${p.price}
      </p>
    `;
    inner.appendChild(card);
  });

  grid.appendChild(inner);

  // ── CART ──
  let cart = [];

  function addToCart(id) {
    const product = products.find(p => p.id === id);
    cart.push(product);
    updateCart();
    showToast(`${product.name} added to bag`);
  }

  function removeFromCart(index) {
    cart.splice(index, 1);
    updateCart();
  }

  function updateCart() {
    const count = cart.length;
    document.getElementById('cart-count').textContent = count;

    const total = cart.reduce((sum, p) => sum + p.price, 0);
    document.getElementById('cart-total').textContent = `$${total.toFixed(2)}`;

    const itemsEl = document.getElementById('cart-items');
    if (cart.length === 0) {
      itemsEl.innerHTML = '<div class="cart-empty">Your bag is empty.</div>';
      return;
    }

    itemsEl.innerHTML = cart.map((p, i) => `
      <div class="cart-item">
        <div class="cart-item-img"><img src="${p.img}" alt="${p.name}" style="width:100%;height:100%;object-fit:cover;"/></div>
        <div class="cart-item-info">
          <p class="cart-item-name">${p.name}</p>
          <p class="cart-item-price">$${p.price}</p>
        </div>
        <button class="cart-item-remove" onclick="removeFromCart(${i})">×</button>
      </div>
    `).join('');
  }

  function openCart() {
    document.getElementById('cart-overlay').classList.add('open');
    document.getElementById('cart-drawer').classList.add('open');
  }

  function closeCart() {
    document.getElementById('cart-overlay').classList.remove('open');
    document.getElementById('cart-drawer').classList.remove('open');
  }

  // ── TOAST ──
  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 2500);
  }

  // ── GA: track add to cart ──
  function trackAddToCart(productName, price) {
    if (typeof gtag !== 'undefined') {
      gtag('event', 'add_to_cart', {
        currency: 'USD',
        value: price,
        items: [{ item_name: productName, price: price }]
      });
    }
  }
</script>

</body>
</html>
