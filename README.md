<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EcoPaws Cafe & Green Living Hub</title>
    <style>
        /* CSS RESET & VARIABLES */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        :root {
            --bg-warm: #fdfbf7;
            --card-bg: #ffffff;
            --primary: #059669;
            --primary-dark: #047857;
            --primary-light: #e6f4ea;
            --amber: #d97706;
            --amber-light: #fef3c7;
            --text-main: #1c1917;
            --text-muted: #57534e;
            --border-color: #e7e5e4;
            --shadow-sm: 0 2px 8px rgba(0,0,0,0.05);
            --shadow-lg: 0 12px 24px rgba(0,0,0,0.08);
            --radius-lg: 20px;
            --radius-md: 12px;
            --radius-full: 999px;
        }

        html {
            scroll-behavior: smooth;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            background-color: var(--bg-warm);
            color: var(--text-main);
            line-height: 1.6;
        }

        body {
            overflow-x: hidden;
        }

        /* TYPOGRAPHY & BUTTONS */
        h1, h2, h3, h4 {
            line-height: 1.25;
            color: var(--text-main);
            font-weight: 800;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 12px 24px;
            border-radius: var(--radius-full);
            font-weight: 700;
            font-size: 14px;
            border: none;
            cursor: pointer;
            transition: all 0.2s ease;
            touch-action: manipulation;
        }

        .btn-primary {
            background-color: var(--primary);
            color: white;
            box-shadow: 0 4px 12px rgba(5, 150, 105, 0.25);
        }

        .btn-primary:hover, .btn-primary:active {
            background-color: var(--primary-dark);
            transform: translateY(-1px);
        }

        .btn-amber {
            background-color: var(--amber);
            color: white;
            box-shadow: 0 4px 12px rgba(217, 119, 6, 0.25);
        }

        .btn-amber:hover, .btn-amber:active {
            background-color: #b45309;
            transform: translateY(-1px);
        }

        .btn-outline {
            background-color: white;
            color: var(--text-main);
            border: 1px solid var(--border-color);
        }

        .btn-outline:hover {
            background-color: var(--bg-warm);
            border-color: var(--primary);
        }

        /* NAVBAR */
        nav {
            position: sticky;
            top: 0;
            z-index: 100;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            padding: 12px 20px;
        }

        .nav-container {
            max-width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 800;
            font-size: 20px;
            color: var(--primary-dark);
        }

        .logo-badge {
            width: 38px;
            height: 38px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            box-shadow: var(--shadow-sm);
        }

        .nav-links {
            display: flex;
            gap: 22px;
            align-items: center;
        }

        .nav-links a {
            font-size: 14px;
            font-weight: 600;
            color: var(--text-muted);
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .hamburger {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            cursor: pointer;
            padding: 6px;
            color: var(--text-main);
        }

        /* MOBILE MENU */
        #mobile-menu {
            display: none;
            background-color: white;
            border-bottom: 1px solid var(--border-color);
            padding: 15px 20px;
            flex-direction: column;
            gap: 12px;
        }

        #mobile-menu.active {
            display: flex;
        }

        #mobile-menu a {
            font-weight: 600;
            font-size: 15px;
            padding: 8px 0;
            border-bottom: 1px solid #f5f5f4;
        }

        /* CONTAINER LAYOUTS */
        .section-container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        .section-header {
            text-align: center;
            max-width: 650px;
            margin: 0 auto 40px auto;
        }

        .section-header span.tag {
            background-color: var(--primary-light);
            color: var(--primary-dark);
            font-size: 12px;
            font-weight: 800;
            padding: 4px 12px;
            border-radius: var(--radius-full);
            text-transform: uppercase;
            display: inline-block;
            margin-bottom: 10px;
        }

        .section-header h2 {
            font-size: 32px;
            margin-bottom: 10px;
        }

        .section-header p {
            color: var(--text-muted);
            font-size: 15px;
        }

        /* HERO SECTION */
        .hero-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .hero-tag {
            background-color: var(--amber-light);
            color: #92400e;
            padding: 6px 14px;
            border-radius: var(--radius-full);
            font-size: 12px;
            font-weight: 800;
            display: inline-block;
            margin-bottom: 16px;
        }

        .hero-content h1 {
            font-size: 44px;
            margin-bottom: 16px;
        }

        .hero-content p {
            color: var(--text-muted);
            font-size: 16px;
            margin-bottom: 28px;
        }

        .hero-actions {
            display: flex;
            gap: 14px;
            flex-wrap: wrap;
            margin-bottom: 32px;
        }

        .hero-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 16px;
            padding-top: 24px;
            border-top: 1px solid var(--border-color);
        }

        .stat-val {
            font-size: 26px;
            font-weight: 800;
            color: var(--primary-dark);
            display: block;
        }

        .stat-lbl {
            font-size: 12px;
            color: var(--text-muted);
            font-weight: 600;
        }

        .hero-visual {
            position: relative;
        }

        .hero-img-wrap {
            width: 100%;
            height: 380px;
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: var(--shadow-lg);
            background-color: var(--primary);
            position: relative;
        }

        .hero-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .hero-img-caption {
            position: absolute;
            bottom: 16px;
            left: 16px;
            right: 16px;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(8px);
            padding: 12px 16px;
            border-radius: var(--radius-md);
            font-size: 12px;
            font-weight: 700;
            color: var(--text-main);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* ECO CALCULATOR SECTION */
        .calculator-bg {
            background-color: #064e3b;
            color: white;
            border-radius: 30px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: var(--shadow-lg);
        }

        .calc-grid {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 30px;
            align-items: center;
        }

        .calc-controls {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        .calc-group label {
            display: flex;
            justify-content: space-between;
            font-weight: 700;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .calc-group span.val {
            color: #f59e0b;
            font-size: 16px;
        }

        input[type="range"] {
            width: 100%;
            accent-color: #f59e0b;
            height: 6px;
            background: #047857;
            border-radius: 4px;
            outline: none;
            cursor: pointer;
        }

        .calc-display {
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.15);
            padding: 24px;
            border-radius: var(--radius-lg);
            text-align: center;
        }

        .calc-display h4 {
            color: #a7f3d0;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 16px;
        }

        .calc-numbers {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
        }

        .calc-num-card {
            background: rgba(0, 0, 0, 0.2);
            padding: 16px;
            border-radius: var(--radius-md);
        }

        .calc-num-card .big-num {
            font-size: 28px;
            font-weight: 900;
            color: #f59e0b;
            display: block;
        }

        .calc-num-card span.sub {
            font-size: 11px;
            color: #d1fae5;
        }

        /* CAT GALLERY SECTION */
        .filter-bar {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .filter-btn {
            background-color: white;
            color: var(--text-muted);
            border: 1px solid var(--border-color);
            padding: 8px 20px;
            border-radius: var(--radius-full);
            font-weight: 700;
            font-size: 13px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .filter-btn.active, .filter-btn:hover {
            background-color: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 28px;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: transform 0.2s, box-shadow 0.2s;
            cursor: pointer;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-4px);
            box-shadow: var(--shadow-lg);
        }

        .card-img-wrap {
            position: relative;
            height: 220px;
            background-color: #f5f5f4;
        }

        .card-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .status-badge {
            position: absolute;
            top: 12px;
            left: 12px;
            background-color: var(--amber-light);
            color: #92400e;
            font-size: 11px;
            font-weight: 800;
            padding: 4px 12px;
            border-radius: var(--radius-full);
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .status-badge.resident {
            background-color: var(--primary-light);
            color: var(--primary-dark);
        }

        .card-body {
            padding: 20px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            flex-grow: 1;
        }

        .card-body h3 {
            font-size: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-body .sub-info {
            font-size: 12px;
            color: var(--text-muted);
            font-weight: 600;
        }

        .card-body p {
            font-size: 13px;
            color: var(--text-muted);
            line-height: 1.5;
        }

        .card-footer {
            padding: 0 20px 20px 20px;
        }

        .btn-view {
            width: 100%;
            padding: 10px;
            border-radius: var(--radius-md);
            border: 1px solid var(--border-color);
            background: white;
            font-weight: 700;
            font-size: 12px;
            color: var(--primary-dark);
            cursor: pointer;
            transition: background 0.2s;
        }

        .card:hover .btn-view {
            background: var(--primary-light);
            border-color: var(--primary);
        }

        /* CAFE MENU SECTION */
        .menu-bg {
            background-color: var(--amber-light);
            border-radius: 30px;
            padding: 50px 20px;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .menu-item {
            background: white;
            border: 1px solid rgba(217, 119, 6, 0.2);
            padding: 20px;
            border-radius: var(--radius-md);
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            transition: border-color 0.2s, transform 0.2s;
        }

        .menu-item:hover {
            border-color: var(--amber);
            transform: translateY(-2px);
        }

        .menu-info h4 {
            font-size: 16px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .tag-pill {
            font-size: 10px;
            font-weight: 800;
            padding: 2px 8px;
            border-radius: 4px;
            background: var(--primary-light);
            color: var(--primary-dark);
        }

        .menu-info p {
            font-size: 12px;
            color: var(--text-muted);
            margin-top: 4px;
        }

        .menu-price {
            font-size: 18px;
            font-weight: 800;
            color: var(--primary-dark);
            white-space: nowrap;
            margin-left: 12px;
        }

        /* GREEN TIPS SECTION */
        .tips-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 24px;
        }

        .tip-card {
            background-color: white;
            border: 1px solid var(--border-color);
            padding: 28px 24px;
            border-radius: var(--radius-lg);
            text-align: left;
        }

        .tip-icon {
            font-size: 32px;
            margin-bottom: 14px;
            display: inline-block;
        }

        .tip-card h3 {
            font-size: 18px;
            margin-bottom: 8px;
        }

        .tip-card p {
            font-size: 13px;
            color: var(--text-muted);
        }

        /* RESERVATION FORM SECTION */
        .booking-wrap {
            max-width: 650px;
            margin: 0 auto;
            background-color: white;
            border: 1px solid var(--border-color);
            border-radius: var(--radius-lg);
            padding: 40px;
            box-shadow: var(--shadow-sm);
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 16px;
            margin-bottom: 16px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 6px;
            margin-bottom: 16px;
        }

        .form-group label {
            font-size: 12px;
            font-weight: 700;
            color: var(--text-main);
        }

        .form-group input, .form-group select {
            padding: 12px 14px;
            border-radius: var(--radius-md);
            border: 1px solid var(--border-color);
            font-size: 14px;
            font-family: inherit;
            outline: none;
            transition: border-color 0.2s;
        }

        .form-group input:focus, .form-group select:focus {
            border-color: var(--primary);
        }

        /* FOOTER */
        footer {
            background-color: #1c1917;
            color: #a8a29e;
            padding: 40px 20px;
            font-size: 13px;
            text-align: center;
            border-top: 1px solid #292524;
        }

        footer strong {
            color: white;
            font-size: 16px;
            display: block;
            margin-bottom: 8px;
        }

        /* MODAL POPUP DIALOGS */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.65);
            backdrop-filter: blur(4px);
            z-index: 1000;
            display: none;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .modal-overlay.open {
            display: flex;
        }

        .modal-box {
            background: white;
            border-radius: var(--radius-lg);
            max-width: 480px;
            width: 100%;
            overflow: hidden;
            box-shadow: var(--shadow-lg);
            position: relative;
            animation: modalIn 0.25s cubic-bezier(0.16, 1, 0.3, 1);
        }

        @keyframes modalIn {
            from { opacity: 0; transform: scale(0.95) translateY(10px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .modal-close-btn {
            position: absolute;
            top: 14px;
            right: 14px;
            background: rgba(255, 255, 255, 0.9);
            border: none;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            font-weight: bold;
            cursor: pointer;
            z-index: 10;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            box-shadow: var(--shadow-sm);
        }

        .modal-img-wrap {
            height: 220px;
            background: #f5f5f4;
            width: 100%;
        }

        .modal-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .modal-body {
            padding: 24px;
        }

        .modal-body h3 {
            font-size: 24px;
            margin-bottom: 4px;
        }

        .modal-body .meta {
            font-size: 12px;
            color: var(--text-muted);
            font-weight: 700;
            margin-bottom: 14px;
        }

        .modal-body p {
            font-size: 13.5px;
            color: var(--text-muted);
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .toast-notif {
            position: fixed;
            bottom: 24px;
            right: 24px;
            background: #064e3b;
            color: white;
            padding: 14px 20px;
            border-radius: var(--radius-md);
            font-weight: 700;
            font-size: 13px;
            box-shadow: var(--shadow-lg);
            z-index: 2000;
            display: none;
            align-items: center;
            gap: 10px;
        }

        .toast-notif.active {
            display: flex;
        }

        /* RESPONSIVE MEDIA QUERIES */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hamburger {
                display: block;
            }

            .hero-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-content h1 {
                font-size: 34px;
            }

            .hero-actions {
                justify-content: center;
            }

            .calc-grid {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .booking-wrap {
                padding: 24px;
            }

            .calculator-bg {
                padding: 24px;
            }
        }
    </style>
</head>
<body>

    <!-- NAVBAR -->
    <nav>
        <div class="nav-container">
            <a href="#about" class="brand-logo">
                <span class="logo-badge">🐾</span>
                <span>EcoPaws</span>
            </a>
            
            <div class="nav-links">
                <a href="#about">Tentang</a>
                <a href="#calculator">Kalkulator Eco</a>
                <a href="#cats">Kucing Kami</a>
                <a href="#menu">Menu Cafe</a>
                <a href="#tips">Tips Eco</a>
                <a href="#booking">Reservasi</a>
            </div>

            <a href="#booking" class="btn btn-primary" style="padding: 9px 18px; font-size: 13px;">Reservasi Meja</a>
            
            <button class="hamburger" onclick="toggleMobileMenu()" aria-label="Toggle Menu">☰</button>
        </div>
    </nav>

    <!-- MOBILE DROPDOWN -->
    <div id="mobile-menu">
        <a href="#about" onclick="toggleMobileMenu()">Tentang Kami</a>
        <a href="#calculator" onclick="toggleMobileMenu()">Kalkulator Eco 📊</a>
        <a href="#cats" onclick="toggleMobileMenu()">Kucing Kami 🐱</a>
        <a href="#menu" onclick="toggleMobileMenu()">Menu Cafe ☕</a>
        <a href="#tips" onclick="toggleMobileMenu()">Tips Eco 🌿</a>
        <a href="#booking" onclick="toggleMobileMenu()">Reservasi Meja 📅</a>
    </div>

    <!-- HERO SECTION -->
    <section id="about" class="section-container">
        <div class="hero-grid">
            <div class="hero-content">
                <span class="hero-tag">🌱 100% Zero-Waste & Pet Rescue Hub</span>
                <h1>Bersantai Bareng <span class="text-emerald">Anabul</span>, Menjaga Masa Depan <span class="text-amber">Bumi</span>.</h1>
                <p>EcoPaws Cafe adalah kafe kucing ramah lingkungan pertama tempat kamu bisa menikmati racikan kopi organik, bersantai dengan kucing-kucing adopsi, serta belajar gaya hidup zero-waste.</p>
                
                <div class="hero-actions">
                    <a href="#cats" class="btn btn-amber">Lihat Kucing Adopsi 🐱</a>
                    <a href="#calculator" class="btn btn-outline">Hitung Jejak Hijaumu 📊</a>
                </div>

                <div class="hero-stats">
                    <div>
                        <span class="stat-val">35+</span>
                        <span class="stat-lbl">Kucing Teradopsi</span>
                    </div>
                    <div>
                        <span class="stat-val">100%</span>
                        <span class="stat-lbl">Bahan Organik</span>
                    </div>
                    <div>
                        <span class="stat-val">0g</span>
                        <span class="stat-lbl">Sampah Plastik</span>
                    </div>
                </div>
            </div>

            <div class="hero-visual">
                <div class="hero-img-wrap">
                    <img src="https://images.unsplash.com/photo-1514888286974-6c03e2ca1dba?auto=format&fit=crop&w=800&q=80" alt="Kucing di EcoPaws Cafe">
                    <div class="hero-img-caption">
                        <span style="font-size: 18px;">🐾</span>
                        <span>Dukung penyelamatan hewan terlantarkan sambil menikmati sajian organik!</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- KALKULATOR ECO INTERAKTIF -->
    <section id="calculator" class="section-container" style="padding-top: 0; padding-bottom: 0;">
        <div class="calculator-bg">
            <div class="calc-grid">
                <div class="calc-controls">
                    <div>
                        <span style="color: #a7f3d0; font-size: 12px; font-weight: 800; text-transform: uppercase;">Simulasi Interaktif</span>
                        <h2 style="font-size: 28px; color: white; margin-top: 4px;">Kalkulator Dampak Hijau Kunjunganmu</h2>
                        <p style="color: #d1fae5; font-size: 13px; margin-top: 6px;">Geser slider di bawah untuk menghitung penghematan sampah & emisi karbonmu!</p>
                    </div>

                    <div class="calc-group">
                        <label>
                            <span>Estimasi Kunjungan / Bulan:</span>
                            <span id="slider-visits-val" class="val">4 kali</span>
                        </label>
                        <input type="range" id="slider-visits" min="1" max="15" value="4" oninput="runEcoCalc()">
                    </div>

                    <div class="calc-group">
                        <label>
                            <span>Cangkir Minuman / Kunjungan:</span>
                            <span id="slider-cups-val" class="val">2 cangkir</span>
                        </label>
                        <input type="range" id="slider-cups" min="1" max="6" value="2" oninput="runEcoCalc()">
                    </div>
                </div>

                <div class="calc-display">
                    <h4>Kontribusi Pertahun Kamu:</h4>
                    <div class="calc-numbers">
                        <div class="calc-num-card">
                            <span id="calc-res-cups" class="big-num">96</span>
                            <span class="sub">Gelas Plastik Dihemat</span>
                        </div>
                        <div class="calc-num-card">
                            <span id="calc-res-co2" class="big-num">24 kg</span>
                            <span class="sub">Pengurangan Emisi CO2</span>
                        </div>
                    </div>
                    <p style="font-size: 11px; color: #a7f3d0; margin-top: 14px; font-style: italic;">
                        🌳 Setara dengan menanam <strong id="calc-res-trees" style="color: white;">4</strong> pohon baru setiap tahun!
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- GALERI KUCING & HUB ADOPSI -->
    <section id="cats" class="section-container">
        <div class="section-header">
            <span class="tag">Anabul Rescue Hub</span>
            <h2>Kucing Kami di EcoPaws</h2>
            <p>Semua kucing dirawat dengan penuh kasih sayang. Klik foto kucing untuk melihat profil lengkap & mengajukan adopsi!</p>
        </div>

        <div class="filter-bar">
            <button class="filter-btn active" onclick="filterCats('all', this)">Semua Kucing</button>
            <button class="filter-btn" onclick="filterCats('adoptable', this)">Siap Diadopsi 🏡</button>
            <button class="filter-btn" onclick="filterCats('resident', this)">Penghuni Cafe ☕</button>
        </div>

        <div class="cards-grid" id="cats-grid">
            <!-- Milo -->
            <div class="card cat-item adoptable" onclick="openCatModal('Milo 🧡', 'Domestik Mix', '1.5 Tahun', 'Siap Diadopsi', 'Milo adalah kucing rescue yang sangat ramah dan suka tidur di pangkuan pengunjung saat menikmati kopi. Sudah divaksinasi lengkap & steril.', 'https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80')">
                <div class="card-img-wrap">
                    <span class="status-badge">Siap Diadopsi</span>
                    <img src="https://images.unsplash.com/photo-1573865526739-10659fec78a5?auto=format&fit=crop&w=600&q=80" alt="Milo">
                </div>
                <div class="card-body">
                    <h3>Milo 🧡</h3>
                    <div class="sub-info">Ras: Domestik Mix • 1.5 Tahun</div>
                    <p>Ramah banget, suka duduk di pangkuan pengunjung. (Klik untuk detail)</p>
                </div>
                <div class="card-footer">
                    <button class="btn-view">Lihat Detail & Adopsi 🐾</button>
                </div>
            </div>

            <!-- Luna -->
            <div class="card cat-item resident" onclick="openCatModal('Luna 🤍', 'Persian Cross', '3 Tahun', 'Penghuni Cafe', 'Luna adalah ratu di cafe kami! Suka tidur di dekat jendela sambil berjemur matahari pagi. Menjadi maskot kesayangan pengunjung.', 'https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=600&q=80')">
                <div class="card-img-wrap">
                    <span class="status-badge resident">Penghuni Cafe</span>
                    <img src="https://images.unsplash.com/photo-1533738363-b7f9aef128ce?auto=format&fit=crop&w=600&q=80" alt="Luna">
                </div>
                <div class="card-body">
                    <h3>Luna 🤍</h3>
                    <div class="sub-info">Ras: Persian Cross • 3 Tahun</div>
                    <p>Ratu cafe! Suka berjemur santai di dekat jendela utama. (Klik untuk detail)</p>
                </div>
                <div class="card-footer">
                    <button class="btn-view">Lihat Detail Profil 🐾</button>
                </div>
            </div>

            <!-- Oreo -->
            <div class="card cat-item adoptable" onclick="openCatModal('Oreo 🖤', 'Tuxedo Cat', '8 Bulan', 'Siap Diadopsi', 'Oreo sangat lincah, penuh energi, dan senang bermain mengejar bola kertas daur ulang. Cocok untuk keluarga aktif.', 'https://images.unsplash.com/photo-1543852786-1cf6624b9987?auto=format&fit=crop&w=600&q=80')">
                <div class="card-img-wrap">
                    <span class="status-badge">Siap Diadopsi</span>
                    <img src="https://images.unsplash.com/photo-1543852786-1cf6624b9987?auto=format&fit=crop&w=600&q=80" alt="Oreo">
                </div>
                <div class="card-body">
                    <h3>Oreo 🖤</h3>
                    <div class="sub-info">Ras: Tuxedo Cat • 8 Bulan</div>
                    <p>Aktif & lincah, selalu siap diajak bermain mainan tali. (Klik untuk detail)</p>
                </div>
                <div class="card-footer">
                    <button class="btn-view">Lihat Detail & Adopsi 🐾</button>
                </div>
            </div>
        </div>
    </section>

    <!-- MENU CAFE ORGANIK -->
    <section id="menu" class="section-container" style="padding-top: 0;">
        <div class="menu-bg">
            <div class="section-header">
                <span class="tag" style="background: white;">100% Organik & Zero Plastic</span>
                <h2>Menu Kafe Ramah Lingkungan</h2>
                <p>Disajikan tanpa wadah sekali pakai. Nikmati rasa otentik bahan lokal berkualitas.</p>
            </div>

            <div class="menu-grid">
                <div class="menu-item" onclick="openMenuToast('Matcha Oat Latte 🍵', 'Matcha Uji Organik + Susu Oat Lokal', 'Rp 32.000')">
                    <div class="menu-info">
                        <h4>Matcha Oat Latte 🍵 <span class="tag-pill">Best Seller</span></h4>
                        <p>Matcha Jepang organik + Susu Oat lokal</p>
                    </div>
                    <div class="menu-price">32k</div>
                </div>

                <div class="menu-item" onclick="openMenuToast('Espresso Paw-ccino ☕', 'Houseblend Organik dengan foam art tapak kucing', 'Rp 28.000')">
                    <div class="menu-info">
                        <h4>Espresso Paw-ccino ☕ <span class="tag-pill">Eco-Beans</span></h4>
                        <p>Kopi Houseblend dengan foam art tapak kucing</p>
                    </div>
                    <div class="menu-price">28k</div>
                </div>

                <div class="menu-item" onclick="openMenuToast('Plant-Based Croissant 🥐', 'Croissant renyah mentega nabati vegan', 'Rp 25.000')">
                    <div class="menu-info">
                        <h4>Plant-Based Croissant 🥐 <span class="tag-pill">Vegan</span></h4>
                        <p>Croissant renyah berbahan mentega nabati</p>
                    </div>
                    <div class="menu-price">25k</div>
                </div>

                <div class="menu-item" onclick="openMenuToast('Herbal Chamomile Tea 🌼', 'Teh daun utuh organik penyegar pikiran', 'Rp 24.000')">
                    <div class="menu-info">
                        <h4>Herbal Chamomile Tea 🌼 <span class="tag-pill">Organic</span></h4>
                        <p>Teh penenang stres disajikan teko kaca</p>
                    </div>
                    <div class="menu-price">24k</div>
                </div>
            </div>
        </div>
    </section>

    <!-- TIPS ECO-LIVING -->
    <section id="tips" class="section-container">
        <div class="section-header">
            <span class="tag">Edukasi Berkelanjutan</span>
            <h2>Tips Gaya Hidup Hijau Pecinta Anabul</h2>
            <p>Langkah mudah merawat anabul kesayangan tanpa mengotori bumi.</p>
        </div>

        <div class="tips-grid">
            <div class="tip-card">
                <span class="tip-icon">🌾</span>
                <h3>Pasir Kucing Organik</h3>
                <p>Gunakan pasir berbasis tahu (*soya litter*) atau serat kayu daur ulang yang biodegradable dan aman diurai tanah.</p>
            </div>

            <div class="tip-card">
                <span class="tip-icon">🧶</span>
                <h3>Mainan DIY Upcycled</h3>
                <p>Kucing lebih menyukai kardus bekas packing atau kain perca daripada mainan plastik mahal baru.</p>
            </div>

            <div class="tip-card">
                <span class="tip-icon">🍲</span>
                <h3>Wadah Stainless / Kaca</h3>
                <p>Mangkuk stainless steel tahan lama puluhan tahun, higienis, dan bebas dari bahaya limbah mikroplastik.</p>
            </div>
        </div>
    </section>

    <!-- FORM RESERVASI MEJA -->
    <section id="booking" class="section-container" style="padding-top: 0;">
        <div class="booking-wrap">
            <div style="text-align: center; margin-bottom: 24px;">
                <span class="tag" style="background: var(--amber-light); color: #92400e;">Reservasi Tempat</span>
                <h2 style="font-size: 26px; margin-top: 4px;">Pesan Meja Kunjungan</h2>
                <p style="font-size: 13px; color: var(--text-muted);">Pilih sesi kunjungan untuk menjamin ketersediaan meja bermain bersama kucing.</p>
            </div>

            <form onsubmit="submitBooking(event)">
                <div class="form-row">
                    <div class="form-group">
                        <label for="book-name">Nama Lengkap</label>
                        <input type="text" id="book-name" required placeholder="Contoh: Amelia Nur">
                    </div>
                    <div class="form-group">
                        <label for="book-phone">Nomor WhatsApp</label>
                        <input type="tel" id="book-phone" required placeholder="0812xxxxxxx">
                    </div>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label for="book-date">Tanggal Kunjungan</label>
                        <input type="date" id="book-date" required>
                    </div>
                    <div class="form-group">
                        <label for="book-guests">Jumlah Tamu</label>
                        <select id="book-guests">
                            <option value="1 Orang">1 Orang</option>
                            <option value="2 Orang" selected>2 Orang</option>
                            <option value="3-4 Orang">3-4 Orang</option>
                            <option value="Grup (>5 Orang)">Grup (>5 Orang)</option>
                        </select>
                    </div>
                </div>

                <div class="form-group">
                    <label for="book-time">Sesi Jam</label>
                    <select id="book-time">
                        <option value="Sesi Pagi (10:00 - 12:00)">Sesi Pagi (10:00 - 12:00)</option>
                        <option value="Sesi Siang (13:00 - 15:00)" selected>Sesi Siang (13:00 - 15:00)</option>
                        <option value="Sesi Sore (16:00 - 18:00)">Sesi Sore (16:00 - 18:00)</option>
                    </select>
                </div>

                <button type="submit" class="btn btn-primary" style="width: 100%; padding: 14px; font-size: 15px; margin-top: 8px;">
                    Konfirmasi Reservasi Meja ✨
                </button>
            </form>
        </div>
    </section>

    <!-- FOOTER -->
    <footer>
        <div style="max-width: 1100px; margin: 0 auto;">
            <strong>🐾 EcoPaws Cat Cafe & Green Living Hub</strong>
            <p>Jl. Margonda Raya No. 108, Depok • Buka Setiap Hari (10:00 - 21:00 WIB)</p>
            <p style="margin-top: 12px; font-size: 11px; opacity: 0.6;">© 2026 EcoPaws Cafe. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- MODAL DIALOG POPUP (CAT DETAILS & ADOPTION) -->
    <div id="cat-modal" class="modal-overlay" onclick="closeModalOnBg(event, 'cat-modal')">
        <div class="modal-box">
            <button class="modal-close-btn" onclick="closeCatModal()">✕</button>
            <div class="modal-img-wrap">
                <img id="modal-cat-img" src="" alt="">
            </div>
            <div class="modal-body">
                <h3 id="modal-cat-name">Milo</h3>
                <div id="modal-cat-meta" class="meta">Ras: Domestik Mix • 1.5 Tahun</div>
                <p id="modal-cat-desc">Deskripsi lengkap kucing.</p>
                <button class="btn btn-amber" style="width: 100%;" onclick="triggerAdoptionSubmit()">Ajukan Adopsi Anabul Ini 🏡</button>
            </div>
        </div>
    </div>

    <!-- MODAL DIALOG RECEIPT (BOOKING RECEIPT) -->
    <div id="booking-modal" class="modal-overlay" onclick="closeModalOnBg(event, 'booking-modal')">
        <div class="modal-box" style="padding: 30px; text-align: center;">
            <div style="font-size: 48px; margin-bottom: 10px;">🎉</div>
            <h3 style="font-size: 22px; margin-bottom: 6px;">Reservasi Berhasil!</h3>
            <p style="font-size: 13px; color: var(--text-muted); margin-bottom: 20px;">Tiket konfirmasi kunjunganmu telah diterbitkan:</p>
            
            <div id="booking-receipt-body" style="background: var(--bg-warm); padding: 16px; border-radius: var(--radius-md); text-align: left; font-size: 13px; line-height: 1.8; margin-bottom: 20px; border: 1px solid var(--border-color);">
            </div>

            <button class="btn btn-primary" style="width: 100%;" onclick="closeBookingModal()">Mengerti & Tutup</button>
        </div>
    </div>

    <!-- TOAST NOTIFICATION -->
    <div id="toast-notif" class="toast-notif">
        <span id="toast-msg">Minuman berhasil ditambahkan!</span>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        
        // 1. MOBILE MENU TOGGLE
        function toggleMobileMenu() {
            var menu = document.getElementById('mobile-menu');
            menu.classList.toggle('active');
        }

        // 2. ECO IMPACT CALCULATOR LOGIC
        function runEcoCalc() {
            var visits = parseInt(document.getElementById('slider-visits').value) || 1;
            var cups = parseInt(document.getElementById('slider-cups').value) || 1;

            document.getElementById('slider-visits-val').innerText = visits + " kali";
            document.getElementById('slider-cups-val').innerText = cups + " cangkir";

            var yearlyCups = visits * cups * 12;
            var co2Kg = (yearlyCups * 0.25).toFixed(0);
            var trees = Math.max(1, Math.round(co2Kg / 6));

            document.getElementById('calc-res-cups').innerText = yearlyCups;
            document.getElementById('calc-res-co2').innerText = co2Kg + " kg";
            document.getElementById('calc-res-trees').innerText = trees;
        }

        // 3. CAT GALLERY FILTER
        function filterCats(category, btnElement) {
            var buttons = document.querySelectorAll('.filter-btn');
            buttons.forEach(function(b) { b.classList.remove('active'); });
            btnElement.classList.add('active');

            var items = document.querySelectorAll('.cat-item');
            items.forEach(function(item) {
                if (category === 'all' || item.classList.contains(category)) {
                    item.style.display = 'flex';
                } else {
                    item.style.display = 'none';
                }
            });
        }

        // 4. CAT MODAL LOGIC
        function openCatModal(name, breed, age, status, desc, imgUrl) {
            document.getElementById('modal-cat-name').innerText = name;
            document.getElementById('modal-cat-meta').innerText = "Ras: " + breed + " • Umur: " + age + " (" + status + ")";
            document.getElementById('modal-cat-desc').innerText = desc;
            document.getElementById('modal-cat-img').src = imgUrl;

            document.getElementById('cat-modal').classList.add('open');
        }

        function closeCatModal() {
            document.getElementById('cat-modal').classList.remove('open');
        }

        function triggerAdoptionSubmit() {
            closeCatModal();
            showToast('🐾 Formulir minat adopsi terkirim! Tim EcoPaws akan menghubungi WA kamu.');
        }

        // 5. MENU TOAST LOGIC
        function openMenuToast(title, desc, price) {
            showToast('☕ ' + title + ' (' + price + '): ' + desc);
        }

        function showToast(msg) {
            var toast = document.getElementById('toast-notif');
            document.getElementById('toast-msg').innerText = msg;
            toast.classList.add('active');

            setTimeout(function() {
                toast.classList.remove('active');
            }, 3500);
        }

        // 6. BOOKING FORM LOGIC
        function submitBooking(e) {
            e.preventDefault();

            var name = document.getElementById('book-name').value;
            var phone = document.getElementById('book-phone').value;
            var date = document.getElementById('book-date').value;
            var guests = document.getElementById('book-guests').value;
            var time = document.getElementById('book-time').value;

            var ticketCode = 'EP-' + Math.floor(1000 + Math.random() * 9000);

            var receiptHtml = '<strong>Nama:</strong> ' + name + '<br>' +
                              '<strong>WhatsApp:</strong> ' + phone + '<br>' +
                              '<strong>Tanggal:</strong> ' + date + '<br>' +
                              '<strong>Jumlah Tamu:</strong> ' + guests + '<br>' +
                              '<strong>Sesi:</strong> ' + time + '<br>' +
                              '<div style="margin-top:8px; color:#047857; font-weight:bold;">Kode Tiket: ' + ticketCode + '</div>';

            document.getElementById('booking-receipt-body').innerHTML = receiptHtml;
            document.getElementById('booking-modal').classList.add('open');
        }

        function closeBookingModal() {
            document.getElementById('booking-modal').classList.remove('open');
        }

        function closeModalOnBg(e, modalId) {
            if (e.target.id === modalId) {
                document.getElementById(modalId).classList.remove('open');
            }
        }

        // INITIALIZE ON LOAD
        window.onload = function() {
            runEcoCalc();

            // Set minimum date for booking input to today
            var today = new Date().toISOString().split('T')[0];
            var dateInput = document.getElementById('book-date');
            if (dateInput) {
                dateInput.min = today;
                dateInput.value = today;
            }
        };
    </script>
</body>
</html>
