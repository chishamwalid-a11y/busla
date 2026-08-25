[index.html](https://github.com/user-attachments/files/31422192/index.html)
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>متجرنا B — تسوق أونلاين</title>
  <meta name="description" content="متجر إلكتروني احترافي لبيع المنتجات مع توصيل سريع ودفع آمن">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap" rel="stylesheet">
  <style>
/* ============================================
   متجرنا — ملف التنسيقات
   عدّل الألوان من المتغيرات في :root
============================================ */
:root {
  --primary: #1e3a8a;
  --primary-dark: #172f6e;
  --accent: #f97316;
  --accent-dark: #ea580c;
  --bg: #f8fafc;
  --card: #ffffff;
  --text: #0f172a;
  --muted: #64748b;
  --border: #e2e8f0;
  --success: #16a34a;
  --danger: #dc2626;
  --radius: 14px;
  --shadow: 0 4px 18px rgba(15, 23, 42, .08);
  --shadow-lg: 0 14px 44px rgba(15, 23, 42, .18);
  --font: 'Cairo', Tahoma, sans-serif;
}

* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; scroll-padding-top: 120px; }
body { font-family: var(--font); background: var(--bg); color: var(--text); line-height: 1.6; }
img { max-width: 100%; display: block; }
a { text-decoration: none; color: inherit; }
button { font-family: inherit; cursor: pointer; border: none; background: none; }
input, select, textarea { font-family: inherit; font-size: 15px; }
body.lock { overflow: hidden; }
.container { max-width: 1200px; margin: 0 auto; padding: 0 16px; }
.hidden { display: none !important; }

/* ===== أزرار ===== */
.btn {
  display: inline-flex; align-items: center; justify-content: center; gap: 8px;
  padding: 11px 24px; border-radius: 12px; font-weight: 700; font-size: 15px;
  border: 2px solid transparent; transition: .25s; white-space: nowrap;
}
.btn-accent {
  background: linear-gradient(135deg, var(--accent), var(--accent-dark));
  color: #fff; box-shadow: 0 6px 16px rgba(249, 115, 22, .35);
}
.btn-accent:hover { transform: translateY(-2px); box-shadow: 0 10px 24px rgba(249, 115, 22, .45); }
.btn-outline { border-color: var(--primary); color: var(--primary); background: #fff; }
.btn-outline:hover { background: var(--primary); color: #fff; }
.btn-block { width: 100%; }

/* ===== الهيدر ===== */
.site-header {
  position: sticky; top: 0; z-index: 100; background: #fff;
  box-shadow: 0 2px 12px rgba(15, 23, 42, .06);
}
.topbar { background: var(--primary); color: #fff; font-size: 13px; font-weight: 600; }
.topbar-inner { display: flex; justify-content: space-between; padding-block: 6px; }
.header-main { display: flex; align-items: center; gap: 16px; padding-block: 12px; flex-wrap: wrap; }
.logo { font-size: 26px; font-weight: 800; color: var(--primary); }
.logo span { color: var(--accent); }
.menu-toggle { display: none; font-size: 24px; color: var(--text); }

.main-nav { display: flex; gap: 4px; align-items: center; }
.main-nav a { padding: 8px 12px; border-radius: 10px; font-weight: 600; font-size: 15px; color: var(--text); transition: .2s; }
.main-nav a:hover { background: #eef2ff; color: var(--primary); }

.header-actions { display: flex; align-items: center; gap: 10px; margin-inline-start: auto; }
.search-box { display: flex; align-items: center; background: var(--bg); border: 2px solid var(--border); border-radius: 12px; padding: 4px 6px 4px 12px; transition: .2s; }
.search-box:focus-within { border-color: var(--primary); background: #fff; }
.search-box input { border: none; outline: none; background: transparent; width: 200px; padding: 6px 4px; }
.search-box button { font-size: 16px; padding: 4px 8px; }

.cart-btn {
  position: relative; display: inline-flex; align-items: center; gap: 6px;
  background: var(--primary); color: #fff; padding: 9px 16px; border-radius: 12px; font-weight: 700; font-size: 15px;
  transition: .2s;
}
.cart-btn:hover { background: var(--primary-dark); transform: translateY(-1px); }
.cart-badge {
  position: absolute; top: -7px; inset-inline-start: -7px; background: var(--accent); color: #fff;
  min-width: 22px; height: 22px; border-radius: 999px; font-size: 12px; font-weight: 800;
  display: flex; align-items: center; justify-content: center; padding: 0 5px; border: 2px solid #fff;
}
.cart-badge.pulse { animation: pulse .35s ease; }
@keyframes pulse { 50% { transform: scale(1.35); } }

/* ===== الهيرو ===== */
.hero {
  background: linear-gradient(135deg, #1e3a8a 0%, #312e81 55%, #4c1d95 100%);
  color: #fff; position: relative; overflow: hidden;
}
.hero::before, .hero::after {
  content: ''; position: absolute; border-radius: 50%; background: rgba(255, 255, 255, .06);
}
.hero::before { width: 340px; height: 340px; top: -140px; inset-inline-start: -100px; }
.hero::after { width: 260px; height: 260px; bottom: -120px; inset-inline-end: 8%; }
.hero-inner { display: flex; align-items: center; justify-content: space-between; gap: 24px; padding-block: 64px; position: relative; z-index: 1; }
.hero-badge {
  display: inline-block; background: rgba(249, 115, 22, .2); border: 1px solid var(--accent);
  color: #fdba74; padding: 5px 14px; border-radius: 999px; font-size: 14px; font-weight: 700; margin-bottom: 16px;
}
.hero h1 { font-size: clamp(1.9rem, 4.5vw, 3rem); line-height: 1.35; margin-bottom: 14px; }
.hero p { color: #c7d2fe; max-width: 480px; margin-bottom: 26px; font-size: 16.5px; }
.hero-art {
  font-size: 120px; background: rgba(255, 255, 255, .1); border: 1px solid rgba(255, 255, 255, .2);
  width: 230px; height: 230px; border-radius: 50%; display: flex; align-items: center; justify-content: center;
  animation: float 4s ease-in-out infinite; flex-shrink: 0;
}
@keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-14px); } }

/* ===== فلاتر الفئات ===== */
.chips-wrap { margin-top: 28px; }
.cat-chips { display: flex; gap: 10px; flex-wrap: wrap; }
.chip {
  padding: 9px 18px; border-radius: 999px; background: #fff; border: 2px solid var(--border);
  font-weight: 700; font-size: 14.5px; color: var(--muted); transition: .2s;
}
.chip:hover { border-color: var(--primary); color: var(--primary); }
.chip.active { background: var(--primary); border-color: var(--primary); color: #fff; }

/* ===== المنتجات ===== */
.products-section { padding-block: 36px 60px; }
.section-head { display: flex; align-items: center; justify-content: space-between; gap: 12px; margin-bottom: 22px; flex-wrap: wrap; }
.section-head h2 { font-size: 26px; font-weight: 800; position: relative; }
.section-head h2::after {
  content: ''; position: absolute; bottom: -6px; inset-inline-start: 0;
  width: 46px; height: 4px; border-radius: 4px; background: var(--accent);
}
.sort-box { display: flex; align-items: center; gap: 8px; color: var(--muted); font-weight: 600; font-size: 14px; }
.sort-box select {
  padding: 8px 12px; border: 2px solid var(--border); border-radius: 10px; background: #fff;
  font-weight: 600; color: var(--text); outline: none; cursor: pointer;
}

.product-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 22px; }
.product-card {
  background: var(--card); border-radius: var(--radius); overflow: hidden; position: relative;
  box-shadow: var(--shadow); display: flex; flex-direction: column; cursor: pointer;
  transition: transform .25s, box-shadow .25s; animation: cardIn .4s ease backwards;
}
@keyframes cardIn { from { opacity: 0; transform: translateY(14px); } to { opacity: 1; transform: none; } }
.product-card:hover { transform: translateY(-6px); box-shadow: var(--shadow-lg); }
.badge {
  position: absolute; top: 12px; inset-inline-start: 12px; z-index: 2;
  background: var(--accent); color: #fff; font-size: 12.5px; font-weight: 800;
  padding: 4px 12px; border-radius: 999px;
}
.product-img {
  aspect-ratio: 1/1; display: flex; align-items: center; justify-content: center;
  position: relative; transition: transform .3s;
}
.product-card:hover .product-img { transform: scale(1.04); }
.product-img .emoji { font-size: 74px; filter: drop-shadow(0 8px 14px rgba(0, 0, 0, .18)); }
.product-body { padding: 14px 16px 8px; flex: 1; }
.p-cat { font-size: 12.5px; font-weight: 700; color: var(--accent-dark); }
.p-name {
  font-size: 16px; font-weight: 700; margin: 4px 0 6px; min-height: 3em; line-height: 1.5;
  display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden;
}
.p-rating { display: flex; align-items: center; gap: 6px; font-size: 13px; color: var(--muted); }
.stars { color: #f59e0b; letter-spacing: 2px; font-size: 14px; }
.p-price { display: flex; align-items: baseline; gap: 10px; margin-top: 8px; }
.p-price .now { font-size: 19px; font-weight: 800; color: var(--primary); }
.p-price del { color: var(--muted); font-size: 13.5px; }
.add-btn { margin: 0 14px 14px; background: var(--primary); color: #fff; }
.add-btn:hover { background: var(--accent); transform: none; box-shadow: 0 8px 18px rgba(249, 115, 22, .4); }
.empty-msg { text-align: center; color: var(--muted); font-size: 17px; padding: 40px 0; }

/* ===== المميزات ===== */
.features { background: #fff; border-block: 1px solid var(--border); }
.features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 20px; padding-block: 34px; }
.feature { text-align: center; }
.feature span {
  display: inline-flex; align-items: center; justify-content: center; width: 58px; height: 58px;
  background: #eef2ff; border-radius: 16px; font-size: 26px; margin-bottom: 10px;
}
.feature h4 { font-size: 16px; font-weight: 800; }
.feature p { color: var(--muted); font-size: 13.5px; }

/* ===== الفوتر ===== */
.site-footer { background: #0f172a; color: #cbd5e1; margin-top: 60px; }
.footer-grid { display: grid; grid-template-columns: 1.4fr 1fr 1fr 1.4fr; gap: 30px; padding-block: 48px; }
.footer-logo { color: #fff; }
.f-col { display: flex; flex-direction: column; gap: 8px; font-size: 14.5px; }
.f-col h4 { color: #fff; font-size: 17px; margin-bottom: 8px; }
.f-col a { transition: .2s; }
.f-col a:hover { color: var(--accent); }
.f-col p { margin: 0; }
.socials { display: flex; gap: 8px; margin-top: 8px; }
.socials a {
  width: 36px; height: 36px; border-radius: 10px; background: #1e293b; color: #fff;
  display: flex; align-items: center; justify-content: center; font-weight: 800; font-size: 13px;
}
.socials a:hover { background: var(--accent); }
.newsletter { display: flex; gap: 8px; margin-top: 6px; }
.newsletter input {
  flex: 1; padding: 9px 12px; border-radius: 10px; border: 1px solid #334155;
  background: #1e293b; color: #fff; outline: none; min-width: 0;
}
.newsletter input::placeholder { color: #64748b; }
.footer-bottom { border-top: 1px solid #1e293b; }
.fb-inner { display: flex; justify-content: space-between; align-items: center; gap: 10px; padding-block: 16px; font-size: 13.5px; flex-wrap: wrap; }
.payments { font-weight: 700; }

/* ===== درج السلة ===== */
.cart-drawer {
  position: fixed; top: 0; inset-inline-start: -430px; width: min(410px, 94vw); height: 100%;
  background: #fff; z-index: 210; display: flex; flex-direction: column;
  transition: inset-inline-start .35s ease; box-shadow: var(--shadow-lg);
}
.cart-drawer.open { inset-inline-start: 0; }
.cart-head { display: flex; justify-content: space-between; align-items: center; padding: 18px 20px; border-bottom: 1px solid var(--border); }
.cart-head h3 { font-size: 19px; font-weight: 800; }
.modal-close {
  width: 34px; height: 34px; border-radius: 10px; background: var(--bg); color: var(--muted);
  font-size: 15px; font-weight: 700; display: flex; align-items: center; justify-content: center; transition: .2s;
}
.modal-close:hover { background: #fee2e2; color: var(--danger); }
.cart-items { flex: 1; overflow-y: auto; padding: 14px 20px; display: flex; flex-direction: column; gap: 12px; }
.cart-empty { text-align: center; color: var(--muted); margin-top: 40px; }
.cart-empty .ce-icon { font-size: 48px; display: block; margin-bottom: 10px; }
.cart-empty p { margin-bottom: 16px; font-weight: 700; }
.cart-item { display: flex; gap: 12px; align-items: center; background: var(--bg); border-radius: 12px; padding: 10px; }
.ci-img { width: 62px; height: 62px; border-radius: 10px; display: flex; align-items: center; justify-content: center; font-size: 28px; flex-shrink: 0; }
.ci-info { flex: 1; min-width: 0; }
.ci-info h4 { font-size: 14px; font-weight: 700; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.ci-info .ci-price { font-size: 13.5px; color: var(--primary); font-weight: 800; }
.ci-qty { display: flex; align-items: center; gap: 8px; margin-top: 4px; }
.ci-qty button {
  width: 26px; height: 26px; border-radius: 8px; background: #fff; border: 1px solid var(--border);
  font-weight: 800; font-size: 15px; display: flex; align-items: center; justify-content: center; transition: .2s;
}
.ci-qty button:hover { border-color: var(--primary); color: var(--primary); }
.ci-qty span { min-width: 20px; text-align: center; font-weight: 800; font-size: 14px; }
.ci-remove { color: var(--muted); font-size: 15px; transition: .2s; padding: 4px; }
.ci-remove:hover { color: var(--danger); transform: scale(1.15); }

.cart-foot { border-top: 1px solid var(--border); padding: 16px 20px 20px; display: flex; flex-direction: column; gap: 12px; }
.promo { display: flex; gap: 8px; }
.promo input {
  flex: 1; padding: 9px 12px; border: 2px solid var(--border); border-radius: 10px; outline: none; min-width: 0;
}
.promo input:focus { border-color: var(--primary); }
.totals { display: flex; flex-direction: column; gap: 6px; font-size: 14.5px; }
.totals > div { display: flex; justify-content: space-between; color: var(--muted); }
.totals .grand { color: var(--text); font-size: 18px; font-weight: 800; border-top: 1px dashed var(--border); padding-top: 8px; margin-top: 2px; }
.totals .grand span:last-child { color: var(--primary); }

/* ===== الطبقات والنوافذ ===== */
.overlay {
  position: fixed; inset: 0; background: rgba(15, 23, 42, .55); z-index: 200;
  opacity: 0; pointer-events: none; transition: opacity .3s;
}
.overlay.show { opacity: 1; pointer-events: auto; }

.modal { position: fixed; inset: 0; z-index: 250; display: none; align-items: center; justify-content: center; padding: 16px; }
.modal.open { display: flex; }
.modal-box {
  background: #fff; border-radius: 18px; position: relative; width: 100%;
  max-width: 920px; max-height: 90vh; overflow-y: auto; padding: 26px;
  animation: pop .3s ease;
}
@keyframes pop { from { transform: scale(.93); opacity: 0; } to { transform: scale(1); opacity: 1; } }
.modal-box > .modal-close { position: absolute; top: 14px; inset-inline-end: 14px; z-index: 3; }

.product-modal { display: grid; grid-template-columns: 1fr 1fr; gap: 26px; }
.pm-img {
  aspect-ratio: 1/1; border-radius: 14px; display: flex; align-items: center; justify-content: center;
  font-size: 110px;
}
.pm-cat { font-size: 13px; font-weight: 800; color: var(--accent-dark); }
.pm-info h3 { font-size: 23px; font-weight: 800; margin: 6px 0 4px; }
.pm-rating { display: flex; align-items: center; gap: 6px; color: var(--muted); font-size: 14px; }
.pm-price { display: flex; align-items: baseline; gap: 12px; margin: 12px 0; }
.pm-price .now { font-size: 26px; font-weight: 800; color: var(--primary); }
.pm-price del { color: var(--muted); font-size: 16px; }
.pm-info p { color: var(--muted); font-size: 14.5px; margin-bottom: 16px; }
.qty-row { display: flex; align-items: center; gap: 14px; margin-bottom: 18px; font-weight: 700; }
.qty { display: flex; align-items: center; gap: 4px; background: var(--bg); border-radius: 10px; padding: 4px; }
.qty button {
  width: 34px; height: 34px; border-radius: 8px; background: #fff; border: 1px solid var(--border);
  font-size: 18px; font-weight: 800; display: flex; align-items: center; justify-content: center; transition: .2s;
}
.qty button:hover { border-color: var(--primary); color: var(--primary); }
.qty span { min-width: 36px; text-align: center; font-weight: 800; font-size: 16px; }

.checkout-modal { max-width: 500px; }
.co-title { font-size: 21px; font-weight: 800; margin-bottom: 16px; }
#checkoutForm { display: flex; flex-direction: column; gap: 6px; }
#checkoutForm label { font-weight: 700; font-size: 14px; margin-top: 8px; }
#checkoutForm input, #checkoutForm textarea {
  padding: 10px 12px; border: 2px solid var(--border); border-radius: 10px; outline: none; resize: vertical; transition: .2s;
}
#checkoutForm input:focus, #checkoutForm textarea:focus { border-color: var(--primary); }
.pay-methods { display: flex; flex-direction: column; gap: 8px; margin: 4px 0 14px; }
.pay-method {
  display: flex; align-items: center; gap: 10px; border: 2px solid var(--border); border-radius: 10px;
  padding: 10px 12px; cursor: pointer; transition: .2s; font-weight: 700; font-size: 14.5px;
}
.pay-method:has(input:checked) { border-color: var(--primary); background: #eef2ff; }
.pay-method input { accent-color: var(--primary); }
.co-submit { margin-top: 6px; }
.order-success { text-align: center; padding: 20px 0 6px; }
.os-icon { font-size: 56px; margin-bottom: 8px; }
.order-success h3 { font-size: 21px; font-weight: 800; color: var(--success); margin-bottom: 6px; }
.order-success p { color: var(--muted); font-size: 15px; }
.order-success strong { color: var(--primary); font-size: 17px; }
.os-note { margin-bottom: 16px; }

/* ===== الإشعار ===== */
.toast {
  position: fixed; bottom: 24px; inset-inline-start: 50%; transform: translate(-50%, 80px);
  background: #0f172a; color: #fff; padding: 13px 24px; border-radius: 12px; z-index: 300;
  font-weight: 700; font-size: 15px; box-shadow: var(--shadow-lg); opacity: 0; transition: .35s;
  max-width: 90vw; text-align: center;
}
.toast.show { transform: translate(-50%, 0); opacity: 1; }

/* ===== التجاوب ===== */
@media (max-width: 992px) {
  .hero-inner { flex-direction: column; text-align: center; padding-block: 44px; }
  .hero p { margin-inline: auto; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 768px) {
  .menu-toggle { display: block; }
  .main-nav {
    display: none; position: absolute; top: 100%; inset-inline: 0; background: #fff;
    flex-direction: column; align-items: stretch; padding: 10px 16px 16px;
    box-shadow: 0 12px 24px rgba(15, 23, 42, .12); gap: 2px;
  }
  .main-nav.open { display: flex; }
  .main-nav a { padding: 12px; border-bottom: 1px solid var(--border); }
  .main-nav a:last-child { border-bottom: none; }
  .search-box { order: 3; width: 100%; }
  .search-box input { width: 100%; }
  .header-actions { margin-inline-start: 0; }
  .hero-art { width: 170px; height: 170px; font-size: 86px; }
  .product-modal { grid-template-columns: 1fr; gap: 18px; }
}
@media (max-width: 560px) {
  .footer-grid { grid-template-columns: 1fr; }
  .topbar-inner span:last-child { display: none; }
  .fb-inner { justify-content: center; text-align: center; }
}
</style>
</head>
<body>

  <!-- ===== الهيدر ===== -->
  <header class="site-header">
    <div class="topbar">
      <div class="container topbar-inner">
        <span>🚚 شحن مجاني للطلبات فوق 500 ج.م</span>
        <span>📞 0100 000 0000</span>
      </div>
    </div>
    <div class="container header-main">
      <button class="menu-toggle" id="menuToggle" aria-label="القائمة">☰</button>
      <a href="#hero" class="logo">متجرنا<span>B</span></a>
      <nav class="main-nav" id="mainNav">
        <a href="#hero">الرئيسية</a>
        <a href="#products">المنتجات</a>
        <a href="#" data-cat="all">الكل</a>
        <a href="#" data-cat="electronics">إلكترونيات</a>
        <a href="#" data-cat="fashion">أزياء</a>
        <a href="#" data-cat="home">المنزل</a>
        <a href="#" data-cat="accessories">إكسسوارات</a>
      </nav>
      <div class="header-actions">
        <div class="search-box">
          <input type="text" id="searchInput" placeholder="ابحث عن منتج...">
          <button type="button" aria-label="بحث">🔍</button>
        </div>
        <button class="cart-btn" id="cartBtn" aria-label="سلة التسوق">
          🛒 <span id="cartBadge" class="cart-badge">0</span>
        </button>
      </div>
    </div>
  </header>

  <main>
    <!-- ===== الهيرو ===== -->
    <section class="hero" id="hero">
      <div class="container hero-inner">
        <div class="hero-text">
          <span class="hero-badge">🔥 عروض الصيف</span>
          <h1>تسوّق أفضل المنتجات<br>بأفضل الأسعار</h1>
          <p>اكتشف تشكيلة واسعة من المنتجات الأصلية مع توصيل سريع وضمان استرجاع خلال 14 يوم.</p>
          <a href="#products" class="btn btn-accent">تسوّق الآن ←</a>
        </div>
        <div class="hero-art">🛍️</div>
      </div>
    </section>

    <!-- ===== فلاتر الفئات ===== -->
    <section class="container chips-wrap">
      <div class="cat-chips" id="catChips">
        <button class="chip active" data-cat="all">الكل</button>
        <button class="chip" data-cat="electronics">📱 إلكترونيات</button>
        <button class="chip" data-cat="fashion">👕 أزياء</button>
        <button class="chip" data-cat="home">🛋️ المنزل</button>
        <button class="chip" data-cat="accessories">⌚ إكسسوارات</button>
      </div>
    </section>

    <!-- ===== المنتجات ===== -->
    <section class="container products-section" id="products">
      <div class="section-head">
        <h2>المنتجات</h2>
        <div class="sort-box">
          <label for="sortSelect">ترتيب:</label>
          <select id="sortSelect">
            <option value="default">الأحدث</option>
            <option value="price-asc">السعر: من الأقل للأعلى</option>
            <option value="price-desc">السعر: من الأعلى للأقل</option>
            <option value="rating">الأعلى تقييماً</option>
          </select>
        </div>
      </div>
      <div class="product-grid" id="productGrid"></div>
      <p id="emptyMsg" class="empty-msg" hidden>لا توجد منتجات مطابقة 🔍</p>
    </section>

    <!-- ===== المميزات ===== -->
    <section class="features">
      <div class="container features-grid">
        <div class="feature"><span>🚚</span><h4>توصيل سريع</h4><p>خلال 2-5 أيام عمل</p></div>
        <div class="feature"><span>🔄</span><h4>إرجاع مجاني</h4><p>خلال 14 يوم</p></div>
        <div class="feature"><span>💳</span><h4>دفع آمن</h4><p>طرق دفع متعددة</p></div>
        <div class="feature"><span>🛡️</span><h4>منتجات أصلية</h4><p>ضمان الجودة 100%</p></div>
      </div>
    </section>
  </main>

  <!-- ===== الفوتر ===== -->
  <footer class="site-footer">
    <div class="container footer-grid">
      <div class="f-col">
        <a href="#hero" class="logo footer-logo">متجرنا<span>B</span></a>
        <p>وجهتك الأولى للتسوق الإلكتروني. نقدم لك أفضل المنتجات بأسعار منافسة وجودة مضمونة.</p>
        <div class="socials">
          <a href="#" aria-label="فيسبوك">ف</a>
          <a href="#" aria-label="انستجرام">إن</a>
          <a href="#" aria-label="تويتر">ت</a>
          <a href="#" aria-label="واتساب">و</a>
        </div>
      </div>
      <div class="f-col">
        <h4>روابط سريعة</h4>
        <a href="#hero">الرئيسية</a>
        <a href="#products">المنتجات</a>
        <a href="#">من نحن</a>
        <a href="#">سياسة الخصوصية</a>
        <a href="#">الشحن والاسترجاع</a>
      </div>
      <div class="f-col">
        <h4>الفئات</h4>
        <a href="#" data-cat="electronics">إلكترونيات</a>
        <a href="#" data-cat="fashion">أزياء</a>
        <a href="#" data-cat="home">المنزل</a>
        <a href="#" data-cat="accessories">إكسسوارات</a>
      </div>
      <div class="f-col">
        <h4>تواصل معنا</h4>
        <p>📍 القاهرة، مصر</p>
        <p>📞 0100 000 0000</p>
        <p>✉️ info@example.com</p>
        <form id="nlForm" class="newsletter">
          <input type="email" id="nlEmail" placeholder="اشترك في النشرة البريدية" required>
          <button type="submit" class="btn btn-accent">اشترك</button>
        </form>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="container fb-inner">
        <p>© <span id="year"></span> متجرنا B. جميع الحقوق محفوظة.</p>
        <div class="payments">💳 فيزا &nbsp;|&nbsp; ماستركارد &nbsp;|&nbsp; 💵 الدفع عند الاستلام</div>
      </div>
    </div>
  </footer>

  <!-- ===== درج السلة ===== -->
  <aside class="cart-drawer" id="cartDrawer" aria-label="سلة التسوق">
    <div class="cart-head">
      <h3>🛒 سلة التسوق</h3>
      <button class="modal-close" id="closeCart" aria-label="إغلاق">✕</button>
    </div>
    <div class="cart-items" id="cartItems"></div>
    <div class="cart-foot" id="cartFoot">
      <div class="promo">
        <input type="text" id="promoInput" placeholder="كود الخصم (جرب: SAVE10)">
        <button class="btn btn-outline" id="promoBtn">تطبيق</button>
      </div>
      <div class="totals">
        <div><span>المجموع الفرعي</span><span id="subtotal">0 ج.م</span></div>
        <div><span>الخصم</span><span id="discount">- 0 ج.م</span></div>
        <div><span>الشحن</span><span id="shipping">0 ج.م</span></div>
        <div class="grand"><span>الإجمالي</span><span id="total">0 ج.م</span></div>
      </div>
      <button class="btn btn-accent btn-block" id="checkoutBtn">إتمام الطلب ←</button>
    </div>
  </aside>
  <div class="overlay" id="overlay"></div>

  <!-- ===== نافذة المنتج ===== -->
  <div class="modal" id="productModal">
    <div class="modal-box product-modal">
      <button class="modal-close" id="closeModal" aria-label="إغلاق">✕</button>
      <div class="pm-img" id="pmImg"></div>
      <div class="pm-info">
        <span class="pm-cat" id="pmCat"></span>
        <h3 id="pmName"></h3>
        <div class="pm-rating" id="pmRating"></div>
        <div class="pm-price"><span class="now" id="pmPrice"></span> <del id="pmOldPrice"></del></div>
        <p id="pmDesc"></p>
        <div class="qty-row">
          <span>الكمية:</span>
          <div class="qty">
            <button type="button" id="qtyMinus">−</button>
            <span id="qtyVal">1</span>
            <button type="button" id="qtyPlus">+</button>
          </div>
        </div>
        <button class="btn btn-accent btn-block" id="pmAdd">أضف إلى السلة 🛒</button>
      </div>
    </div>
  </div>

  <!-- ===== نافذة إتمام الطلب ===== -->
  <div class="modal" id="checkoutModal">
    <div class="modal-box checkout-modal">
      <button class="modal-close" id="closeCheckout" aria-label="إغلاق">✕</button>
      <h3 class="co-title">إتمام الطلب</h3>
      <form id="checkoutForm">
        <label>الاسم الكامل *</label>
        <input type="text" id="fullName" placeholder="مثال: أحمد محمد" required>

        <label>رقم الهاتف *</label>
        <input type="tel" id="phone" placeholder="01xxxxxxxxx" required>

        <label>المدينة *</label>
        <input type="text" id="city" placeholder="مثال: القاهرة" required>

        <label>العنوان بالتفصيل *</label>
        <textarea id="address" rows="2" placeholder="الشارع، رقم المنزل، المنطقة..." required></textarea>

        <label>طريقة الدفع</label>
        <div class="pay-methods">
          <label class="pay-method"><input type="radio" name="pay" value="cod" checked><span>💵 عند الاستلام</span></label>
          <label class="pay-method"><input type="radio" name="pay" value="card"><span>💳 بطاقة بنكية</span></label>
          <label class="pay-method"><input type="radio" name="pay" value="wallet"><span>📱 محفظة إلكترونية</span></label>
        </div>

        <button type="submit" class="btn btn-accent btn-block co-submit">تأكيد الطلب ✓</button>
        <p style="text-align:center;font-size:13px;color:var(--muted);margin-top:10px">📲 بعد التأكيد هتتوجه تلقائياً للواتساب لإرسال الطلب</p>
      </form>
      <div id="orderSuccess" class="order-success" hidden>
        <div class="os-icon">✅</div>
        <h3>تم استلام طلبك بنجاح!</h3>
        <p>رقم الطلب: <strong id="orderNum"></strong></p>
        <p class="os-note">أرسل رسالة الطلب الجاهزة في واتساب لإتمامه ✅</p>
        <button class="btn btn-outline btn-block" id="continueShopping">متابعة التسوق</button>
      </div>
    </div>
  </div>

  <!-- ===== إشعار ===== -->
  <div id="toast" class="toast"></div>

  <script>
/* ============================================
   متجرنا — ملف الوظائف
   عدّل المنتجات والأسعار من مصفوفة products
============================================ */

/* ===== البيانات ===== */
const CATS = { electronics: 'إلكترونيات', fashion: 'أزياء', home: 'المنزل', accessories: 'إكسسوارات' };
const CUR = 'ج.م';              // ← غيّر العملة من هنا (مثلاً: '$')
const FREE_SHIP_LIMIT = 500;    // حد الشحن المجاني
const SHIP_FEE = 50;            // رسوم الشحن
const STORE_WHATSAPP = '201016946303'; // ← رقم واتسابك بالكود الدولي (بدون +)

const products = [
  { id: 1,  cat: 'electronics',  name: 'سماعات بلوتوث لاسلكية',  price: 899,   old: 1299,  rating: 4.6, reviews: 320,  badge: 'خصم 30%',  emoji: '🎧', bg: 'linear-gradient(135deg,#dbeafe,#bfdbfe)', desc: 'سماعات أذن لاسلكية بجودة صوت نقية، عمر بطارية حتى 30 ساعة مع علبة شحن محمولة.' },
  { id: 2,  cat: 'electronics',  name: 'ساعة ذكية رياضية',        price: 1499,  old: 1899,  rating: 4.4, reviews: 210,  badge: 'الأكثر مبيعاً', emoji: '⌚', bg: 'linear-gradient(135deg,#e0e7ff,#c7d2fe)', desc: 'ساعة ذكية تقيس نبضات القلب والخطوات والنوم، متوافقة مع أندرويد وآيفون، مقاومة للماء.' },
  { id: 3,  cat: 'electronics',  name: 'لابتوب محمول خفيف',        price: 18999, old: 21999, rating: 4.8, reviews: 96,   badge: 'خصم 14%',  emoji: '💻', bg: 'linear-gradient(135deg,#f3e8ff,#e9d5ff)', desc: 'لابتوب بشاشة 15.6 بوصة، معالج حديث، ذاكرة 16GB وقرص SSD سريع — مثالي للعمل والدراسة.' },
  { id: 4,  cat: 'fashion',      name: 'حذاء رياضي عصري',         price: 1099,  old: 1399,  rating: 4.5, reviews: 180,  badge: 'جديد',  emoji: '👟', bg: 'linear-gradient(135deg,#fee2e2,#fecaca)', desc: 'حذاء رياضي خفيف ومريح بنعل مرن، مثالي للجري والمشي اليومي، متوفر بمقاسات مختلفة.' },
  { id: 5,  cat: 'fashion',      name: 'تيشيرت قطني فاخر',        price: 299,   old: 399,   rating: 4.3, reviews: 450,  badge: 'خصم 25%',  emoji: '👕', bg: 'linear-gradient(135deg,#dcfce7,#bbf7d0)', desc: 'تيشيرت قطن 100% خامة فاخرة ومريحة، ألوان ثابتة لا تبهت مع الغسيل، مقاسات من S حتى XXL.' },
  { id: 6,  cat: 'fashion',      name: 'جاكيت شتوي أنيق',         price: 1299,  old: 1699,  rating: 4.7, reviews: 140,  badge: 'الأكثر مبيعاً', emoji: '🧥', bg: 'linear-gradient(135deg,#e2e8f0,#cbd5e1)', desc: 'جاكيت شتوي مبطن يحميك من البرد، تصميم عصري يناسب العمل والخروجات، جيوب داخلية واسعة.' },
  { id: 7,  cat: 'accessories',  name: 'نظارة شمسية بولارايزد',   price: 499,   old: 699,   rating: 4.2, reviews: 260,  badge: 'خصم 28%',  emoji: '🕶️', bg: 'linear-gradient(135deg,#fef3c7,#fde68a)', desc: 'نظارة شمسية بعدسات بولارايزد تحمي عينيك من الأشعة فوق البنفسجية، بإطار خفيف ومتين.' },
  { id: 8,  cat: 'accessories',  name: 'حقيبة جلدية رجالية',      price: 1599,  old: 1999,  rating: 4.6, reviews: 88,   badge: 'جديد',  emoji: '💼', bg: 'linear-gradient(135deg,#fed7aa,#fdba74)', desc: 'حقيبة يد جلدية فاخرة مصنوعة يدوياً، بمساحة واسعة للابتوب والأغراض الشخصية، تتحمل الاستخدام اليومي.' },
  { id: 9,  cat: 'accessories',  name: 'حقيبة ظهر عصرية',         price: 699,   old: 899,   rating: 4.4, reviews: 175,  badge: 'خصم 22%',  emoji: '🎒', bg: 'linear-gradient(135deg,#fce7f3,#fbcfe8)', desc: 'حقيبة ظهر مقاومة للماء بجيوب متعددة ومنفذ شحن USB، مثالية للدراسة والسفر والرحلات.' },
  { id: 10, cat: 'home',         name: 'مصباح مكتبي LED',         price: 349,   old: 450,   rating: 4.5, reviews: 310,  badge: 'خصم 22%',  emoji: '💡', bg: 'linear-gradient(135deg,#fef9c3,#fef08a)', desc: 'مصباح مكتبي LED بثلاث درجات إضاءة وشحن USB، يريح عينيك أثناء القراءة والعمل.' },
  { id: 11, cat: 'home',         name: 'ماكينة قهوة إسبريسو',     price: 2499,  old: 2999,  rating: 4.8, reviews: 120,  badge: 'الأكثر مبيعاً', emoji: '☕', bg: 'linear-gradient(135deg,#ffedd5,#fed7aa)', desc: 'ماكينة قهوة إسبريسو بسعة 1.2 لتر، تحضّر قهوة غنية بالكريمة في دقائق، سهلة التنظيف.' },
  { id: 12, cat: 'home',         name: 'طقم أواني مطبخ (12 قطعة)', price: 899,   old: 1099,  rating: 4.6, reviews: 200,  badge: 'جديد',  emoji: '🍳', bg: 'linear-gradient(135deg,#cffafe,#a5f3fc)', desc: 'طقم أواني مطبخ غير لاصقة من 12 قطعة، خامات آمنة على الصحة ومناسبة لجميع أنواع البوتاجاز.' },
];

/* ===== الحالة ===== */
let cart = JSON.parse(localStorage.getItem('cart') || '[]');
let promo = null;
let currentCat = 'all', query = '', sortBy = 'default';
let modalQty = 1, currentProduct = null;

const saveCart = () => localStorage.setItem('cart', JSON.stringify(cart));
const byId = id => products.find(p => p.id === id);
const fmt = n => n.toLocaleString('en-US');
const price = n => fmt(n) + ' ' + CUR;

/* ===== أدوات ===== */
const $ = id => document.getElementById(id);
const grid = $('productGrid'), chips = $('catChips'), cartItems = $('cartItems');
const cartDrawer = $('cartDrawer'), overlay = $('overlay');
const productModal = $('productModal'), checkoutModal = $('checkoutModal');

function stars(r) {
  const full = '★'.repeat(Math.round(r));
  const empty = '☆'.repeat(5 - Math.round(r));
  return '<span class="stars">' + full + empty + '</span>';
}

let toastTimer;
function toast(msg) {
  const t = $('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => t.classList.remove('show'), 2600);
}

/* ===== عرض المنتجات ===== */
function productCard(p, i) {
  return `
  <article class="product-card" data-id="${p.id}" style="animation-delay:${(i % 8) * 0.05}s">
    ${p.badge ? `<span class="badge">${p.badge}</span>` : ''}
    <div class="product-img" style="background:${p.bg}"><span class="emoji">${p.emoji}</span></div>
    <div class="product-body">
      <span class="p-cat">${CATS[p.cat]}</span>
      <h3 class="p-name">${p.name}</h3>
      <div class="p-rating">${stars(p.rating)}<span>(${p.reviews})</span></div>
      <div class="p-price"><span class="now">${price(p.price)}</span>${p.old ? `<del>${price(p.old)}</del>` : ''}</div>
    </div>
    <button class="btn add-btn" data-act="add" data-id="${p.id}">أضف للسلة 🛒</button>
  </article>`;
}

function renderProducts() {
  let list = products.filter(p => {
    const okCat = currentCat === 'all' || p.cat === currentCat;
    const okQuery = p.name.includes(query) || CATS[p.cat].includes(query);
    return okCat && okQuery;
  });
  if (sortBy === 'price-asc') list.sort((a, b) => a.price - b.price);
  else if (sortBy === 'price-desc') list.sort((a, b) => b.price - a.price);
  else if (sortBy === 'rating') list.sort((a, b) => b.rating - a.rating);

  grid.innerHTML = list.map(productCard).join('');
  $('emptyMsg').hidden = list.length > 0;
}

function setCategory(cat) {
  currentCat = cat;
  chips.querySelectorAll('.chip').forEach(ch => ch.classList.toggle('active', ch.dataset.cat === cat));
  renderProducts();
  document.getElementById('products').scrollIntoView({ behavior: 'smooth' });
}

/* ===== السلة ===== */
function updateBadge() {
  const count = cart.reduce((s, it) => s + it.qty, 0);
  const badge = $('cartBadge');
  badge.textContent = count;
  badge.classList.toggle('hidden', count === 0);
  badge.classList.add('pulse');
  setTimeout(() => badge.classList.remove('pulse'), 350);
}

function addToCart(id, qty = 1) {
  const found = cart.find(it => it.id === id);
  if (found) found.qty = Math.min(found.qty + qty, 99);
  else cart.push({ id, qty });
  saveCart(); renderCart(); updateBadge();
  openCart();
  toast('✓ تمت إضافة المنتج للسلة');
}

function renderCart() {
  const foot = $('cartFoot');
  if (!cart.length) {
    cartItems.innerHTML = `
      <div class="cart-empty">
        <span class="ce-icon">🛒</span>
        <p>سلتك فارغة حالياً</p>
        <button class="btn btn-outline" id="emptyShop">تصفح المنتجات</button>
      </div>`;
    $('emptyShop').onclick = closeCart;
    foot.classList.add('hidden');
    return;
  }
  foot.classList.remove('hidden');
  cartItems.innerHTML = cart.map(it => {
    const p = byId(it.id);
    return `
    <div class="cart-item">
      <div class="ci-img" style="background:${p.bg}"><span>${p.emoji}</span></div>
      <div class="ci-info">
        <h4>${p.name}</h4>
        <span class="ci-price">${price(p.price)}</span>
        <div class="ci-qty">
          <button data-act="minus" data-id="${p.id}">−</button>
          <span>${it.qty}</span>
          <button data-act="plus" data-id="${p.id}">+</button>
        </div>
      </div>
      <button class="ci-remove" data-act="remove" data-id="${p.id}" title="حذف">🗑</button>
    </div>`;
  }).join('');
  updateTotals();
}

function calcTotals() {
  const subtotal = cart.reduce((s, it) => s + byId(it.id).price * it.qty, 0);
  let discount = 0, shipFee = SHIP_FEE;
  if (promo) {
    if (promo.type === 'percent') discount = subtotal * promo.val / 100;
    else if (promo.type === 'ship') shipFee = 0;
  }
  const afterDiscount = subtotal - discount;
  if (afterDiscount >= FREE_SHIP_LIMIT) shipFee = 0;
  return { subtotal, discount, shipFee, total: afterDiscount + shipFee };
}

function updateTotals() {
  const { subtotal, discount, shipFee, total } = calcTotals();
  $('subtotal').textContent = price(subtotal);
  $('discount').textContent = '- ' + price(discount);
  $('shipping').textContent = shipFee === 0 ? 'مجاني 🎉' : price(shipFee);
  $('total').textContent = price(total);
}

function openCart() { cartDrawer.classList.add('open'); overlay.classList.add('show'); document.body.classList.add('lock'); }
function closeCart() { cartDrawer.classList.remove('open'); closeOverlay(); }
function closeOverlay() {
  overlay.classList.remove('show');
  document.body.classList.remove('lock');
}

/* ===== النافذة المنبثقة للمنتج ===== */
function openModal(id) {
  const p = byId(id);
  if (!p) return;
  currentProduct = p; modalQty = 1;
  $('qtyVal').textContent = modalQty;
  $('pmImg').style.background = p.bg;
  $('pmImg').innerHTML = '<span class="emoji" style="font-size:110px">' + p.emoji + '</span>';
  $('pmCat').textContent = CATS[p.cat];
  $('pmName').textContent = p.name;
  $('pmRating').innerHTML = stars(p.rating) + '<span>(' + p.reviews + ' تقييم)</span>';
  $('pmPrice').textContent = price(p.price);
  $('pmOldPrice').textContent = p.old ? price(p.old) : '';
  $('pmDesc').textContent = p.desc;
  productModal.classList.add('open');
  overlay.classList.add('show');
  document.body.classList.add('lock');
}
function closeModal() { productModal.classList.remove('open'); closeOverlay(); }

/* ===== الأحداث ===== */
// فلاتر الفئات (في الهيدر والفوتر)
document.addEventListener('click', e => {
  const c = e.target.closest('[data-cat]');
  if (c) { e.preventDefault(); setCategory(c.dataset.cat); }
});

// شبكة المنتجات
grid.addEventListener('click', e => {
  const addBtn = e.target.closest('[data-act="add"]');
  if (addBtn) { e.stopPropagation(); addToCart(+addBtn.dataset.id); return; }
  const card = e.target.closest('.product-card');
  if (card) openModal(+card.dataset.id);
});

// البحث والترتيب
$('searchInput').addEventListener('input', e => { query = e.target.value.trim(); renderProducts(); });
$('sortSelect').addEventListener('change', e => { sortBy = e.target.value; renderProducts(); });

// السلة
$('cartBtn').onclick = () => { if (cart.length) openCart(); else toast('سلتك فارغة حالياً 🛒'); };
$('closeCart').onclick = closeCart;
cartItems.addEventListener('click', e => {
  const btn = e.target.closest('[data-act]');
  if (!btn) return;
  const id = +btn.dataset.id;
  const item = cart.find(it => it.id === id);
  if (!item) return;
  if (btn.dataset.act === 'plus') item.qty = Math.min(item.qty + 1, 99);
  else if (btn.dataset.act === 'minus') { item.qty--; if (item.qty < 1) cart = cart.filter(it => it.id !== id); }
  else if (btn.dataset.act === 'remove') cart = cart.filter(it => it.id !== id);
  saveCart(); renderCart(); updateBadge();
});

// كود الخصم
$('promoBtn').onclick = () => {
  const code = $('promoInput').value.trim().toUpperCase();
  const PROMOS = { SAVE10: { type: 'percent', val: 10 }, FREESHIP: { type: 'ship' } };
  if (PROMOS[code]) { promo = PROMOS[code]; updateTotals(); toast('🎉 تم تفعيل كود الخصم'); }
  else toast('كود الخصم غير صحيح ❌');
};

// النافذة المنبثقة
$('closeModal').onclick = closeModal;
$('qtyMinus').onclick = () => { modalQty = Math.max(1, modalQty - 1); $('qtyVal').textContent = modalQty; };
$('qtyPlus').onclick = () => { modalQty = Math.min(99, modalQty + 1); $('qtyVal').textContent = modalQty; };
$('pmAdd').onclick = () => { addToCart(currentProduct.id, modalQty); closeModal(); };

// إتمام الطلب
$('checkoutBtn').onclick = () => { closeCart(); checkoutModal.classList.add('open'); overlay.classList.add('show'); document.body.classList.add('lock'); };
$('closeCheckout').onclick = () => { checkoutModal.classList.remove('open'); closeOverlay(); };

$('checkoutForm').addEventListener('submit', e => {
  e.preventDefault();
  const name = $('fullName').value.trim();
  const phone = $('phone').value.trim();
  const city = $('city').value.trim();
  const address = $('address').value.trim();
  if (name.length < 3) return toast('اكتب اسمك الكامل من فضلك');
  if (!/^01\d{9}$/.test(phone)) return toast('رقم الهاتف غير صحيح (11 رقم يبدأ بـ 01)');
  if (!city) return toast('اكتب اسم المدينة');
  if (address.length < 10) return toast('اكتب العنوان بالتفصيل');

  // تجهيز رسالة الطلب وإرسالها للواتساب
  const t = calcTotals();
  const pay = (document.querySelector('input[name="pay"]:checked') || {}).value || 'cod';
  const payNames = { cod: 'الدفع عند الاستلام 💵', card: 'بطاقة بنكية 💳', wallet: 'محفظة إلكترونية 📱' };
  const itemsText = cart.map(it => {
    const p = byId(it.id);
    return '• ' + p.name + ' × ' + it.qty + ' = ' + price(p.price * it.qty);
  }).join('\n');
  const msg = '🛒 طلب جديد من متجرنا B\n'
    + '━━━━━━━━━━━━━\n'
    + '👤 الاسم: ' + name + '\n'
    + '📱 الموبايل: ' + phone + '\n'
    + '🏙️ المدينة: ' + city + '\n'
    + '📍 العنوان: ' + address + '\n'
    + '━━━━━━━━━━━━━\n'
    + itemsText + '\n'
    + '━━━━━━━━━━━━━\n'
    + '💰 المجموع الفرعي: ' + price(t.subtotal) + '\n'
    + '🏷️ الخصم: - ' + price(t.discount) + '\n'
    + '🚚 الشحن: ' + (t.shipFee === 0 ? 'مجاني 🎉' : price(t.shipFee)) + '\n'
    + '✅ الإجمالي: ' + price(t.total) + '\n'
    + '💳 الدفع: ' + (payNames[pay] || pay) + '\n'
    + '━━━━━━━━━━━━━\n'
    + 'برجاء تأكيد الطلب 🙏';
  window.open('https://wa.me/' + STORE_WHATSAPP + '?text=' + encodeURIComponent(msg), '_blank');

  $('checkoutForm').hidden = true;
  $('orderSuccess').hidden = false;
  $('orderNum').textContent = '#' + Date.now().toString().slice(-6);
  cart = []; promo = null; $('promoInput').value = '';
  saveCart(); renderCart(); updateBadge();
});

$('continueShopping').onclick = () => {
  checkoutModal.classList.remove('open'); closeOverlay();
  $('checkoutForm').hidden = false;
  $('orderSuccess').hidden = true;
  $('checkoutForm').reset();
};

// النشرة البريدية
$('nlForm').addEventListener('submit', e => { e.preventDefault(); toast('✓ تم الاشتراك في النشرة البريدية'); e.target.reset(); });

// القائمة الجوال
$('menuToggle').onclick = () => $('mainNav').classList.toggle('open');
$('mainNav').addEventListener('click', e => { if (e.target.tagName === 'A') $('mainNav').classList.remove('open'); });

// إغلاق الطبقات
overlay.onclick = () => { closeCart(); closeModal(); checkoutModal.classList.remove('open'); closeOverlay(); };
document.addEventListener('keydown', e => { if (e.key === 'Escape') { closeCart(); closeModal(); checkoutModal.classList.remove('open'); closeOverlay(); } });

// ===== تشغيل أولي =====
$('year').textContent = new Date().getFullYear();
renderProducts();
renderCart();
updateBadge();
</script>
</body>
</html>
