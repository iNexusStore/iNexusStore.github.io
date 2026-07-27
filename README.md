<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iNexus Store | iPhones & AirPods Mexico</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background: #050505;
            color: #e0e0e0;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }
        body.light-mode {
            background: #F5F5F7;
            color: #1D1D1F;
        }
        .container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }

        /* TOP BAR */
        .top-bar {
            background: linear-gradient(90deg, #007AFF, #0051D5);
            padding: 8px 24px;
            text-align: center;
            font-size: 13px;
            font-weight: 500;
            color: white;
            letter-spacing: 0.3px;
        }
        .top-bar span { opacity: 0.9; }
        .top-bar strong { font-weight: 700; }

        /* FLOATING GLASS NAVBAR */
        .nav-glass {
            position: sticky;
            top: 16px;
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 28px;
            margin: 16px auto 32px;
            max-width: 1100px;
            background: rgba(20,20,20,0.7);
            backdrop-filter: blur(24px) saturate(180%);
            -webkit-backdrop-filter: blur(24px) saturate(180%);
            border: 1px solid rgba(255,255,255,0.08);
            border-radius: 100px;
            box-shadow: 0 4px 30px rgba(0,0,0,0.4), inset 0 1px 0 rgba(255,255,255,0.05);
            animation: navSlide 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .light-mode .nav-glass {
            background: rgba(255,255,255,0.7);
            border: 1px solid rgba(0,0,0,0.08);
            box-shadow: 0 4px 30px rgba(0,0,0,0.1), inset 0 1px 0 rgba(255,255,255,0.5);
        }
        @keyframes navSlide {
            from { transform: translateY(-20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        .nav-logo { font-size: 22px; font-weight: 800; color: #fff; letter-spacing: -0.5px; text-decoration: none; }
        .light-mode .nav-logo { color: #1D1D1F; }
        .nav-logo span { color: #007AFF; }
        .nav-links { display: flex; gap: 32px; list-style: none; margin: 0; padding: 0; }
        .nav-links a {
            font-size: 14px; font-weight: 500; color: #aaa; text-decoration: none;
            position: relative; transition: color 0.3s; padding: 4px 0;
        }
        .light-mode .nav-links a { color: #555; }
        .nav-links a::after {
            content: ''; position: absolute; bottom: -2px; left: 0; width: 0; height: 2px;
            background: #007AFF; border-radius: 1px;
            transition: width 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .nav-links a:hover { color: #fff; }
        .light-mode .nav-links a:hover { color: #1D1D1F; }
        .nav-links a:hover::after { width: 100%; }
        .nav-actions { display: flex; align-items: center; gap: 12px; }
        .theme-toggle {
            width: 40px; height: 40px; border-radius: 50%;
            background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
            display: flex; align-items: center; justify-content: center;
            font-size: 18px; cursor: pointer; transition: all 0.3s; color: #aaa;
        }
        .light-mode .theme-toggle {
            background: rgba(0,0,0,0.06); border: 1px solid rgba(0,0,0,0.1); color: #555;
        }
        .theme-toggle:hover {
            background: #007AFF; border-color: #007AFF; color: white;
            transform: scale(1.1); box-shadow: 0 0 20px rgba(0,122,255,0.3);
        }
        .nav-search-btn {
            width: 40px; height: 40px; border-radius: 50%;
            background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
            display: flex; align-items: center; justify-content: center;
            font-size: 18px; cursor: pointer; transition: all 0.3s; color: #aaa;
        }
        .light-mode .nav-search-btn {
            background: rgba(0,0,0,0.06); border: 1px solid rgba(0,0,0,0.1); color: #555;
        }
        .nav-search-btn:hover {
            background: #007AFF; border-color: #007AFF; color: white;
            transform: scale(1.1); box-shadow: 0 0 20px rgba(0,122,255,0.3);
        }
        .nav-cart {
            width: 40px; height: 40px; border-radius: 50%;
            background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
            display: flex; align-items: center; justify-content: center;
            font-size: 18px; cursor: pointer; transition: all 0.3s; color: #aaa;
        }
        .light-mode .nav-cart {
            background: rgba(0,0,0,0.06); border: 1px solid rgba(0,0,0,0.1); color: #555;
        }
        .nav-cart:hover {
            background: #007AFF; border-color: #007AFF; color: white;
            transform: scale(1.1); box-shadow: 0 0 20px rgba(0,122,255,0.3);
        }

        /* SEARCH OVERLAY */
        .search-overlay {
            position: fixed; top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(5,5,5,0.95); backdrop-filter: blur(20px);
            z-index: 200; display: none; align-items: center; justify-content: center;
            padding: 24px; opacity: 0; transition: opacity 0.3s;
        }
        .light-mode .search-overlay { background: rgba(245,245,247,0.95); }
        .search-overlay.active { display: flex; opacity: 1; }
        .search-overlay-inner { width: 100%; max-width: 700px; }
        .search-close {
            position: absolute; top: 24px; right: 24px;
            width: 48px; height: 48px; border-radius: 50%;
            background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
            color: #aaa; font-size: 24px; cursor: pointer; display: flex;
            align-items: center; justify-content: center; transition: all 0.3s;
        }
        .search-close:hover { background: #007AFF; color: white; }
        .search-overlay input {
            width: 100%; padding: 24px 32px;
            background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.1);
            border-radius: 20px; color: #fff; font-size: 20px;
            font-family: 'Inter', sans-serif; outline: none;
            transition: all 0.4s;
        }
        .light-mode .search-overlay input {
            background: rgba(0,0,0,0.05); border: 1px solid rgba(0,0,0,0.1); color: #1D1D1F;
        }
        .search-overlay input:focus {
            border-color: rgba(0,122,255,0.4);
            box-shadow: 0 0 0 4px rgba(0,122,255,0.08);
        }
        .search-overlay input::placeholder { color: #444; }
        .light-mode .search-overlay input::placeholder { color: #999; }

        /* STICKY WHATSAPP */
        .sticky-wa {
            position: fixed; bottom: 24px; right: 24px;
            z-index: 90; display: flex; align-items: center; gap: 10px;
            background: linear-gradient(135deg, #25D366, #128C7E);
            padding: 14px 24px; border-radius: 100px;
            box-shadow: 0 8px 30px rgba(37,211,102,0.3);
            text-decoration: none; color: white; font-weight: 600; font-size: 15px;
            transition: all 0.3s; animation: waPulse 2s ease-in-out infinite;
        }
        .sticky-wa:hover {
            transform: scale(1.05) translateY(-2px);
            box-shadow: 0 12px 40px rgba(37,211,102,0.4);
        }
        @keyframes waPulse {
            0%, 100% { box-shadow: 0 8px 30px rgba(37,211,102,0.3); }
            50% { box-shadow: 0 8px 40px rgba(37,211,102,0.5); }
        }
        .sticky-wa .wa-icon { font-size: 22px; }

        /* HERO */
        .hero-apple {
            position: relative; border-radius: 32px; overflow: hidden;
            min-height: 520px; display: flex; align-items: center; justify-content: center;
            margin-bottom: 60px;
            background: linear-gradient(135deg, #0a0a0a 0%, #111 40%, #0d0d0d 100%);
            border: 1px solid rgba(255,255,255,0.04);
        }
        .light-mode .hero-apple {
            background: linear-gradient(135deg, #fff 0%, #f0f0f5 40%, #e8e8ed 100%);
            border: 1px solid rgba(0,0,0,0.06);
        }
        .hero-apple::before {
            content: ''; position: absolute; inset: 0;
            background: radial-gradient(ellipse at 25% 20%, rgba(0,122,255,0.06) 0%, transparent 50%),
                        radial-gradient(ellipse at 75% 80%, rgba(0,122,255,0.04) 0%, transparent 40%);
            pointer-events: none;
        }
        .hero-apple::after {
            content: ''; position: absolute; width: 500px; height: 500px; border-radius: 50%;
            background: radial-gradient(circle, rgba(0,122,255,0.08) 0%, transparent 60%);
            top: 50%; left: 50%; transform: translate(-50%, -50%);
            animation: heroPulse 7s ease-in-out infinite; pointer-events: none;
        }
        @keyframes heroPulse {
            0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.5; }
            50% { transform: translate(-50%, -50%) scale(1.4); opacity: 1; }
        }
        .hero-content { position: relative; z-index: 2; text-align: center; padding: 60px 24px; }
        .hero-badge {
            display: inline-block; padding: 8px 20px; border-radius: 100px;
            background: rgba(0,122,255,0.1);
            backdrop-filter: blur(20px) saturate(180%);
            -webkit-backdrop-filter: blur(20px) saturate(180%);
            border: 1px solid rgba(0,122,255,0.2);
            font-size: 12px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase;
            color: #007AFF; margin-bottom: 24px;
            animation: badgeFloat 3s ease-in-out infinite;
        }
        .light-mode .hero-badge {
            background: rgba(0,122,255,0.08); border: 1px solid rgba(0,122,255,0.15);
        }
        @keyframes badgeFloat {
            0%, 100% { transform: translateY(0); } 50% { transform: translateY(-5px); }
        }
        .hero-title {
            font-size: clamp(40px, 8vw, 72px); font-weight: 900; letter-spacing: -3px;
            line-height: 1.05; margin: 0 0 16px;
            background: linear-gradient(180deg, #fff 0%, #888 100%);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        .light-mode .hero-title {
            background: linear-gradient(180deg, #1D1D1F 0%, #555 100%);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        .hero-subtitle {
            font-size: clamp(16px, 3vw, 22px); font-weight: 400; color: #666;
            margin: 0 auto 40px; max-width: 500px;
        }
        .light-mode .hero-subtitle { color: #555; }
        .hero-cta {
            display: inline-flex; align-items: center; gap: 10px;
            padding: 16px 36px; border-radius: 100px; background: #007AFF; color: white;
            font-size: 16px; font-weight: 600; border: none; cursor: pointer;
            position: relative; overflow: hidden;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            box-shadow: 0 4px 30px rgba(0,122,255,0.3);
            text-decoration: none;
        }
        .hero-cta::before {
            content: ''; position: absolute; inset: 0;
            background: radial-gradient(circle at var(--x, 50%) var(--y, 50%), rgba(255,255,255,0.25) 0%, transparent 60%);
            opacity: 0; transition: opacity 0.3s;
        }
        .hero-cta:hover {
            transform: scale(1.05) translateY(-2px);
            box-shadow: 0 8px 40px rgba(0,122,255,0.4), 0 0 80px rgba(0,122,255,0.1);
        }
        .hero-cta:hover::before { opacity: 1; }
        .hero-cta:active { transform: scale(0.97); }

        /* SECTION LABELS */
        .section-label {
            font-size: 13px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase;
            color: #444; margin-bottom: 24px; display: flex; align-items: center; gap: 12px;
        }
        .light-mode .section-label { color: #888; }
        .section-label::after {
            content: ''; flex: 1; height: 1px;
            background: linear-gradient(90deg, #1a1a1a, transparent);
        }
        .light-mode .section-label::after {
            background: linear-gradient(90deg, #ddd, transparent);
        }
        .section-title {
            font-size: clamp(24px, 4vw, 32px); font-weight: 800; color: #fff;
            margin: 0 0 8px; letter-spacing: -1px;
        }
        .light-mode .section-title { color: #1D1D1F; }
        .section-subtitle { color: #555; font-size: 15px; margin-bottom: 32px; }
        .light-mode .section-subtitle { color: #666; }

        /* FEATURE PILLS */
        .feature-strip {
            display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; margin-bottom: 60px;
        }
        .feature-pill {
            background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.06);
            border-radius: 20px; padding: 28px 20px; text-align: center;
            position: relative; overflow: hidden;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94); cursor: default;
        }
        .light-mode .feature-pill {
            background: rgba(0,0,0,0.02); border: 1px solid rgba(0,0,0,0.06);
        }
        .feature-pill::before {
            content: ''; position: absolute; top: 0; left: -100%; width: 100%; height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0,122,255,0.03), transparent);
            transition: left 0.7s;
        }
        .feature-pill:hover::before { left: 100%; }
        .feature-pill:hover {
            border-color: rgba(0,122,255,0.2); transform: translateY(-4px);
            box-shadow: 0 12px 30px rgba(0,0,0,0.3), 0 0 0 1px rgba(0,122,255,0.08);
            background: rgba(255,255,255,0.04);
        }
        .light-mode .feature-pill:hover {
            background: rgba(0,0,0,0.04); box-shadow: 0 12px 30px rgba(0,0,0,0.08);
        }
        .feature-pill .feat-icon {
            width: 52px; height: 52px; border-radius: 16px;
            background: linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
            border: 1px solid rgba(255,255,255,0.06);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 14px; font-size: 24px; transition: transform 0.3s;
        }
        .light-mode .feature-pill .feat-icon {
            background: linear-gradient(135deg, rgba(0,0,0,0.06), rgba(0,0,0,0.02));
            border: 1px solid rgba(0,0,0,0.06);
        }
        .feature-pill:hover .feat-icon {
            transform: scale(1.1) rotate(-5deg); border-color: rgba(0,122,255,0.2);
        }
        .feature-pill .feat-title { font-size: 14px; font-weight: 700; color: #ddd; margin: 0 0 4px; }
        .light-mode .feature-pill .feat-title { color: #333; }
        .feature-pill .feat-desc { font-size: 12px; color: #555; margin: 0; }
        .light-mode .feature-pill .feat-desc { color: #777; }

        /* PRODUCT GRID */
        .product-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 24px; margin-bottom: 60px;
        }

        /* CARD TYPE A: FLAGSHIP */
        .card-flagship {
            background: linear-gradient(145deg, #141414, #0a0a0a); border-radius: 28px;
            padding: 40px 32px; position: relative; overflow: hidden;
            transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer; border: 1px solid rgba(255,255,255,0.05); grid-column: span 2;
        }
        .light-mode .card-flagship {
            background: linear-gradient(145deg, #fff, #f5f5f7);
            border: 1px solid rgba(0,0,0,0.06);
        }
        .card-flagship:hover {
            transform: translateY(-8px) scale(1.01);
            box-shadow: 0 30px 60px rgba(0,0,0,0.5), 0 0 0 1px rgba(0,122,255,0.1);
            border-color: rgba(0,122,255,0.15);
        }
        .light-mode .card-flagship:hover {
            box-shadow: 0 20px 40px rgba(0,0,0,0.1), 0 0 0 1px rgba(0,122,255,0.1);
        }
        .card-flagship .card-glow {
            position: absolute; width: 300px; height: 300px; border-radius: 50%;
            background: radial-gradient(circle, rgba(0,122,255,0.12) 0%, transparent 70%);
            top: -80px; right: -80px;
            animation: glowDrift 10s ease-in-out infinite; pointer-events: none;
        }
        @keyframes glowDrift {
            0%, 100% { transform: translate(0, 0); }
            33% { transform: translate(-40px, 30px); }
            66% { transform: translate(30px, -20px); }
        }
        .card-flagship .card-label {
            font-size: 11px; font-weight: 800; letter-spacing: 1.5px; text-transform: uppercase;
            color: #007AFF; margin-bottom: 12px; position: relative; z-index: 1;
        }
        .card-flagship .card-title {
            font-size: 32px; font-weight: 800; color: #fff; margin: 0 0 10px;
            letter-spacing: -1px; position: relative; z-index: 1;
        }
        .light-mode .card-flagship .card-title { color: #1D1D1F; }
        .card-flagship .card-desc {
            font-size: 15px; color: #666; margin: 0 0 20px; max-width: 320px;
            line-height: 1.6; position: relative; z-index: 1;
        }
        .light-mode .card-flagship .card-desc { color: #555; }
        .card-flagship .product-specs { margin-bottom: 20px; position: relative; z-index: 1; }
        .card-flagship .spec-tag {
            background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08); color: #888;
        }
        .light-mode .card-flagship .spec-tag {
            background: rgba(0,0,0,0.04); border: 1px solid rgba(0,0,0,0.08); color: #666;
        }
        .card-flagship .product-price {
            font-size: 28px; font-weight: 800; color: #34C759; margin-bottom: 20px;
            position: relative; z-index: 1;
        }
        .card-flagship .product-price span { font-size: 13px; color: #444; font-weight: 500; display: block; margin-top: 4px; }
        .light-mode .card-flagship .product-price span { color: #777; }
        .card-flagship .product-price .old-price {
            font-size: 18px; color: #555; text-decoration: line-through; margin-right: 8px;
        }
        .light-mode .card-flagship .product-price .old-price { color: #999; }
        .card-flagship .card-btn {
            display: inline-flex; align-items: center; gap: 8px;
            padding: 14px 28px; border-radius: 100px; background: #007AFF; color: white;
            font-size: 15px; font-weight: 600; border: none; cursor: pointer;
            transition: all 0.3s; text-decoration: none; position: relative; z-index: 1;
        }
        .card-flagship .card-btn:hover {
            background: #0051D5; transform: scale(1.05); box-shadow: 0 0 30px rgba(0,122,255,0.3);
        }
        .card-flagship .card-visual {
            position: absolute; right: 30px; bottom: 30px;
            width: 200px; height: 240px;
            background: linear-gradient(145deg, #1c1c1e, #111); border-radius: 24px;
            display: flex; align-items: center; justify-content: center;
            box-shadow: inset 0 2px 10px rgba(0,0,0,0.5), 0 10px 30px rgba(0,0,0,0.3);
            border: 1px solid rgba(255,255,255,0.04);
        }
        .light-mode .card-flagship .card-visual {
            background: linear-gradient(145deg, #e8e8ed, #ddd);
            border: 1px solid rgba(0,0,0,0.06);
        }
        .card-flagship .card-visual img {
            width: 100%; height: 100%; object-fit: cover; border-radius: 20px;
        }

        /* CARD TYPE B: GLASS */
        .card-glass {
            background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.06);
            border-radius: 24px; padding: 28px; position: relative; overflow: hidden;
            transition: all 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            cursor: pointer; display: flex; flex-direction: column;
        }
        .light-mode .card-glass {
            background: rgba(0,0,0,0.02); border: 1px solid rgba(0,0,0,0.06);
        }
        .card-glass:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4), 0 0 0 1px rgba(0,122,255,0.08);
            border-color: rgba(0,122,255,0.15);
            background: rgba(255,255,255,0.04);
        }
        .light-mode .card-glass:hover {
            background: rgba(0,0,0,0.04); box-shadow: 0 20px 40px rgba(0,0,0,0.08);
        }
        .card-glass .card-visual-glass {
            width: 100%; height: 180px; border-radius: 16px; margin-bottom: 20px;
            background: linear-gradient(145deg, #1c1c1e, #111); overflow: hidden;
            display: flex; align-items: center; justify-content: center;
            border: 1px solid rgba(255,255,255,0.04);
        }
        .light-mode .card-glass .card-visual-glass {
            background: linear-gradient(145deg, #e8e8ed, #ddd);
            border: 1px solid rgba(0,0,0,0.06);
        }
        .card-glass .card-visual-glass img {
            width: 100%; height: 100%; object-fit: cover;
        }
        .card-glass .card-title {
            font-size: 20px; font-weight: 700; color: #fff; margin: 0 0 8px;
        }
        .light-mode .card-glass .card-title { color: #1D1D1F; }
        .card-glass .card-desc {
            font-size: 13px; color: #666; margin: 0 0 16px; line-height: 1.5; flex: 1;
        }
        .light-mode .card-glass .card-desc { color: #555; }

        /* SPECS */
        .product-specs { display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 16px; }
        .spec-tag {
            font-size: 11px; font-weight: 600; padding: 4px 10px; border-radius: 100px;
            background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08);
            color: #888;
        }
        .light-mode .spec-tag {
            background: rgba(0,0,0,0.04); border: 1px solid rgba(0,0,0,0.08); color: #666;
        }

        /* COLOR DOTS */
        .color-dots { display: flex; gap: 8px; margin-bottom: 16px; }
        .color-dot {
            width: 20px; height: 20px; border-radius: 50%;
            border: 2px solid rgba(255,255,255,0.2); cursor: pointer;
            transition: all 0.3s; position: relative;
        }
        .light-mode .color-dot { border-color: rgba(0,0,0,0.2); }
        .color-dot:hover { transform: scale(1.2); }
        .color-dot.active { border-color: #007AFF; box-shadow: 0 0 0 2px rgba(0,122,255,0.3); }

        /* STOCK COUNTER */
        .stock-counter {
            font-size: 12px; font-weight: 600; color: #FF3B30;
            display: flex; align-items: center; gap: 6px; margin-bottom: 12px;
        }
        .pulse-dot {
            width: 8px; height: 8px; border-radius: 50%; background: #FF3B30;
            animation: pulse 1.5s ease-in-out infinite;
        }
        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.3); }
        }

        /* PRICE */
        .product-price { font-size: 22px; font-weight: 800; color: #34C759; margin-bottom: 16px; }
        .product-price .old-price {
            font-size: 15px; color: #555; text-decoration: line-through; margin-right: 8px; font-weight: 500;
        }
        .light-mode .product-price .old-price { color: #999; }

        /* BUTTONS */
        .card-actions { display: flex; gap: 10px; }
        .btn-primary {
            flex: 1; padding: 12px 20px; border-radius: 100px; background: #007AFF; color: white;
            font-size: 14px; font-weight: 600; border: none; cursor: pointer;
            text-align: center; text-decoration: none; transition: all 0.3s;
        }
        .btn-primary:hover { background: #0051D5; transform: scale(1.03); }
        .btn-ghost {
            padding: 12px 20px; border-radius: 100px;
            background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.1);
            color: #aaa; font-size: 14px; font-weight: 600; cursor: pointer;
            transition: all 0.3s;
        }
        .light-mode .btn-ghost {
            background: rgba(0,0,0,0.04); border: 1px solid rgba(0,0,0,0.1); color: #555;
        }
        .btn-ghost:hover { border-color: #007AFF; color: #007AFF; }

        /* LIGHTNING DEAL */
        .lightning-deal {
            background: linear-gradient(135deg, #1a0a00, #2d1b00); border: 1px solid rgba(255,159,10,0.2);
            border-radius: 28px; padding: 40px; text-align: center; margin-bottom: 60px;
            position: relative; overflow: hidden;
        }
        .light-mode .lightning-deal {
            background: linear-gradient(135deg, #fff5e6, #ffe8cc);
            border: 1px solid rgba(255,159,10,0.15);
        }
        .lightning-deal::before {
            content: ''; position: absolute; inset: 0;
            background: radial-gradient(circle at 50% 50%, rgba(255,159,10,0.08) 0%, transparent 60%);
        }
        .lightning-badge {
            display: inline-block; padding: 8px 20px; border-radius: 100px;
            background: rgba(255,159,10,0.15); border: 1px solid rgba(255,159,10,0.3);
            font-size: 12px; font-weight: 800; letter-spacing: 1px; text-transform: uppercase;
            color: #FF9F0A; margin-bottom: 16px;
        }
        .lightning-title { font-size: 28px; font-weight: 800; color: #fff; margin: 0 0 8px; }
        .light-mode .lightning-title { color: #1D1D1F; }
        .lightning-desc { color: #666; margin: 0 0 20px; }
        .light-mode .lightning-desc { color: #555; }
        .countdown-timer {
            font-size: 48px; font-weight: 900; color: #FF9F0A; letter-spacing: 4px;
            font-variant-numeric: tabular-nums; margin-bottom: 24px;
        }
        .lightning-btn {
            display: inline-flex; align-items: center; gap: 8px;
            padding: 16px 36px; border-radius: 100px; background: #FF9F0A; color: #000;
            font-size: 16px; font-weight: 700; text-decoration: none;
            transition: all 0.3s;
        }
        .lightning-btn:hover { transform: scale(1.05); box-shadow: 0 0 30px rgba(255,159,10,0.3); }

        /* TESTIMONIALS */
        .testimonials-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px; margin-bottom: 60px;
        }
        .testimonial-card {
            background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.06);
            border-radius: 24px; padding: 28px; text-align: center;
            transition: all 0.4s;
        }
        .light-mode .testimonial-card {
            background: rgba(0,0,0,0.02); border: 1px solid rgba(0,0,0,0.06);
        }
        .testimonial-card:hover {
            transform: translateY(-4px);
            border-color: rgba(0,122,255,0.15);
            box-shadow: 0 12px 30px rgba(0,0,0,0.2);
        }
        .testimonial-avatar {
            width: 56px; height: 56px; border-radius: 50%;
            background: linear-gradient(135deg, #007AFF, #0051D5);
            display: flex; align-items: center; justify-content: center;
            font-size: 28px; margin: 0 auto 12px;
        }
        .testimonial-name { font-size: 15px; font-weight: 700; color: #ddd; margin-bottom: 4px; }
        .light-mode .testimonial-name { color: #333; }
        .testimonial-stars { font-size: 14px; margin-bottom: 12px; }
        .testimonial-text { font-size: 13px; color: #888; line-height: 1.6; margin: 0 0 12px; font-style: italic; }
        .light-mode .testimonial-text { color: #666; }
        .testimonial-product { font-size: 12px; color: #007AFF; font-weight: 600; }

        /* SHIPPING */
        .shipping-grid {
            display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; margin-bottom: 60px;
        }
        .shipping-card {
            background: rgba(255,255,255,0.02); border: 1px solid rgba(255,255,255,0.06);
            border-radius: 20px; padding: 28px 20px; text-align: center;
            transition: all 0.4s;
        }
        .light-mode .shipping-card {
            background: rgba(0,0,0,0.02); border: 1px solid rgba(0,0,0,0.06);
        }
        .shipping-card:hover {
            transform: translateY(-4px); border-color: rgba(0,122,255,0.15);
        }
        .shipping-icon {
            width: 48px; height: 48px; border-radius: 14px;
            background: linear-gradient(135deg, rgba(0,122,255,0.1), rgba(0,122,255,0.05));
            border: 1px solid rgba(0,122,255,0.15);
            display: flex; align-items: center; justify-content: center;
            margin: 0 auto 12px; font-size: 22px;
        }
        .shipping-card h4 { font-size: 14px; font-weight: 700; color: #ddd; margin: 0 0 6px; }
        .light-mode .shipping-card h4 { color: #333; }
        .shipping-card p { font-size: 12px; color: #555; margin: 0; }
        .light-mode .shipping-card p { color: #777; }

        /* FIRST BUY BANNER */
        .first-buy-banner {
            background: linear-gradient(135deg, #007AFF, #0051D5);
            border-radius: 28px; padding: 40px; text-align: center; margin-bottom: 60px;
        }
        .first-buy-content h3 { font-size: 24px; font-weight: 800; color: white; margin: 0 0 8px; }
        .first-buy-content p { color: rgba(255,255,255,0.8); margin: 0 0 20px; }
        .first-buy-btn {
            display: inline-flex; align-items: center; gap: 8px;
            padding: 14px 32px; border-radius: 100px; background: white; color: #007AFF;
            font-size: 15px; font-weight: 700; text-decoration: none;
            transition: all 0.3s;
        }
        .first-buy-btn:hover { transform: scale(1.05); box-shadow: 0 10px 30px rgba(0,0,0,0.2); }

        /* MODAL */
        .modal-overlay {
            position: fixed; inset: 0; background: rgba(5,5,5,0.9);
            backdrop-filter: blur(20px); z-index: 300;
            display: none; align-items: center; justify-content: center;
            padding: 24px; opacity: 0; transition: opacity 0.3s;
        }
        .light-mode .modal-overlay { background: rgba(245,245,247,0.95); }
        .modal-overlay.active { display: flex; opacity: 1; }
        .modal-content {
            background: #141414; border: 1px solid rgba(255,255,255,0.08);
            border-radius: 28px; padding: 40px; max-width: 600px; width: 100%;
            max-height: 85vh; overflow-y: auto; position: relative;
            animation: modalIn 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .light-mode .modal-content {
            background: #fff; border: 1px solid rgba(0,0,0,0.08);
        }
        @keyframes modalIn {
            from { transform: scale(0.9) translateY(20px); opacity: 0; }
            to { transform: scale(1) translateY(0); opacity: 1; }
        }
        .modal-close {
            position: absolute; top: 16px; right: 16px;
            width: 40px; height: 40px; border-radius: 50%;
            background: rgba(255,255,255,0.06); border: 1px solid rgba(255,255,255,0.1);
            color: #aaa; font-size: 20px; cursor: pointer; display: flex;
            align-items: center; justify-content: center; transition: all 0.3s;
        }
        .modal-close:hover { background: #FF3B30; color: white; }
        .modal-header { margin-bottom: 24px; }
        .modal-title { font-size: 24px; font-weight: 800; color: #fff; margin: 0 0 8px; }
        .light-mode .modal-title { color: #1D1D1F; }
        .modal-price { font-size: 28px; font-weight: 800; color: #34C759; }
        .modal-price .old-price { font-size: 16px; color: #555; text-decoration: line-through; margin-right: 8px; }
        .light-mode .modal-price .old-price { color: #999; }
        .modal-section { margin-bottom: 24px; }
        .modal-section h4 { font-size: 14px; font-weight: 700; color: #888; margin: 0 0 12px; text-transform: uppercase; letter-spacing: 1px; }
        .light-mode .modal-section h4 { color: #666; }
        .modal-specs { list-style: none; padding: 0; margin: 0; }
        .modal-specs li { font-size: 14px; color: #aaa; padding: 6px 0; border-bottom: 1px solid rgba(255,255,255,0.04); }
        .light-mode .modal-specs li { color: #555; border-color: rgba(0,0,0,0.06); }
        .reviews-list { display: flex; flex-direction: column; gap: 16px; }
        .review-item { background: rgba(255,255,255,0.02); border-radius: 16px; padding: 16px; }
        .light-mode .review-item { background: rgba(0,0,0,0.02); }
        .review-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
        .review-name { font-size: 14px; font-weight: 700; color: #ddd; }
        .light-mode .review-name { color: #333; }
        .review-stars { font-size: 13px; }
        .review-text { font-size: 13px; color: #888; margin: 0; line-height: 1.5; font-style: italic; }
        .light-mode .review-text { color: #666; }

        /* FOOTER */
        footer {
            background: rgba(255,255,255,0.01); border-top: 1px solid rgba(255,255,255,0.06);
            padding: 60px 24px 40px; text-align: center; margin-top: 40px;
        }
        .light-mode footer {
            background: rgba(0,0,0,0.01); border-top: 1px solid rgba(0,0,0,0.06);
        }
        .footer-logo { font-size: 24px; font-weight: 800; color: #fff; margin-bottom: 12px; }
        .light-mode .footer-logo { color: #1D1D1F; }
        .footer-logo span { color: #007AFF; }
        footer > p { color: #555; font-size: 14px; margin-bottom: 24px; }
        .light-mode footer > p { color: #666; }
        .footer-links { display: flex; justify-content: center; gap: 24px; margin-bottom: 24px; flex-wrap: wrap; }
        .footer-links a { color: #888; text-decoration: none; font-size: 14px; font-weight: 500; transition: color 0.3s; }
        .light-mode .footer-links a { color: #555; }
        .footer-links a:hover { color: #007AFF; }
        .footer-copy { color: #333; font-size: 12px; }
        .light-mode .footer-copy { color: #999; }

        /* SCROLL ANIMATIONS */
        .scroll-animate { opacity: 0; transform: translateY(30px); transition: all 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94); }
        .scroll-animate.visible { opacity: 1; transform: translateY(0); }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            .feature-strip { grid-template-columns: repeat(2, 1fr); }
            .shipping-grid { grid-template-columns: repeat(2, 1fr); }
            .card-flagship { grid-column: span 1; }
            .card-flagship .card-visual { position: relative; right: auto; bottom: auto; width: 100%; height: 200px; margin-top: 20px; }
            .nav-links { display: none; }
            .countdown-timer { font-size: 32px; }
        }
    </style>
</head>
<body>
    <!-- TOP BAR -->
    <div class="top-bar">
        <span>&#128666; <strong>Envio gratis</strong> en compras mayores a $10,000 | &#9889; <strong>10% OFF</strong> pagando por transferencia | &#127873; <strong>5% OFF</strong> en tu primera compra</span>
    </div>

    <!-- STICKY WHATSAPP -->
    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20conocer%20sus%20productos" class="sticky-wa" target="_blank">
        <span class="wa-icon">&#128172;</span>
        <span>Cotizar por WhatsApp</span>
    </a>

    <!-- SEARCH OVERLAY -->
    <div class="search-overlay" id="searchOverlay">
        <button class="search-close" onclick="closeSearch()">&#10005;</button>
        <div class="search-overlay-inner">
            <input type="text" id="searchInput" placeholder="Busca iPhone, AirPods, accesorios..." oninput="filterProducts(this.value)">
        </div>
    </div>

    <div class="container">
        <nav class="nav-glass">
            <a href="#" class="nav-logo">i<span>Nexus</span></a>
            <ul class="nav-links">
                <li><a href="#iphones">iPhone</a></li>
                <li><a href="#airpods">AirPods</a></li>
                <li><a href="#accesorios">Accesorios</a></li>
                <li><a href="#garantia">Garantia</a></li>
                <li><a href="#reviews">Resenas</a></li>
            </ul>
            <div class="nav-actions">
                <button class="theme-toggle" onclick="toggleTheme()" title="Cambiar tema">&#127769;</button>
                <button class="nav-search-btn" onclick="openSearch()" title="Buscar">&#128269;</button>
                <button class="nav-cart" title="Carrito">&#128722;</button>
            </div>
        </nav>
    </div>

    <div class="container">
        <section class="hero-apple">
            <div class="hero-content">
                <div class="hero-badge">MX CDMX - Envio Nacional DHL</div>
                <h1 class="hero-title">iNexus Store</h1>
                <p class="hero-subtitle">iPhones &amp; AirPods de calidad garantizada. Equipos revisados, baterias al 100% y envios a todo Mexico.</p>
                <a href="#iphones" class="hero-cta" onmousemove="this.style.setProperty('--x', (event.offsetX/this.offsetWidth)*100+'%'); this.style.setProperty('--y', (event.offsetY/this.offsetHeight)*100+'%')">Ver catalogo &#8594;</a>
            </div>
        </section>

        <div class="section-label">Por que comprar en iNexus</div>
        <div class="feature-strip">
            <div class="feature-pill">
                <div class="feat-icon">&#128666;</div>
                <div class="feat-title">Envio gratis DHL</div>
                <div class="feat-desc">2-3 dias a todo Mexico</div>
            </div>
            <div class="feature-pill">
                <div class="feat-icon">&#9889;</div>
                <div class="feat-title">Express 24h</div>
                <div class="feat-desc">Solo +$150 pesos</div>
            </div>
            <div class="feature-pill">
                <div class="feat-icon">&#128737;</div>
                <div class="feat-title">Garantia real</div>
                <div class="feat-desc">30 dias de prueba</div>
            </div>
            <div class="feature-pill">
                <div class="feat-icon">&#128267;</div>
                <div class="feat-title">Bateria 100%</div>
                <div class="feat-desc">Reemplazo garantizado</div>
            </div>
        </div>

        <div class="section-label" id="iphones">Catalogo</div>
        <h2 class="section-title">&#128241; iPhones</h2>
        <p class="section-subtitle">Equipos revisados, desbloqueados y listos para usar con cualquier operador en Mexico.</p>
        
        <div class="product-grid" id="productGrid">
            <!-- iPhone 15 Pro Max -->
            <div class="product-card card-flagship" data-name="iPhone 15 Pro Max">
                <div class="card-glow"></div>
                <div class="card-label">Mas vendido</div>
                <h3 class="card-title">iPhone 15 Pro Max</h3>
                <p class="card-desc">Titanio natural. Chip A17 Pro. Pantalla Super Retina XDR de 6.7". La bestia de Apple con camara deslumbrante de 48 MP.</p>
                <div class="product-specs">
                    <span class="spec-tag">A17 Pro</span>
                    <span class="spec-tag">256 GB</span>
                    <span class="spec-tag">Titanio</span>
                    <span class="spec-tag">USB-C</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#5C5B57" title="Titanio Natural"></div>
                    <div class="color-dot" style="background:#2A2A2A" title="Titanio Negro"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Titanio Blanco"></div>
                    <div class="color-dot" style="background:#3B4C6B" title="Titanio Azul"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 8 unidades</div>
                <div class="product-price"><span class="old-price">$12,999</span>$10,499</div>
                <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2015%20Pro%20Max" class="card-btn" target="_blank">Cotizar por WhatsApp &#8594;</a>
                <div class="card-visual">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-15-pro-max-model-unselect-gallery-1-202309?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1693011129000" alt="iPhone 15 Pro Max" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
            </div>

            <!-- iPhone 15 Pro -->
            <div class="product-card card-glass" data-name="iPhone 15 Pro">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-15-pro-model-unselect-gallery-1-202309?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1693011129000" alt="iPhone 15 Pro" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 15 Pro</h3>
                <p class="card-desc">Diseno titanio de grado aeroespacial. Camara Pro de 48 MP con zoom optico 3x. El equilibrio perfecto.</p>
                <div class="product-specs">
                    <span class="spec-tag">A17 Pro</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">USB-C</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#5C5B57" title="Titanio Natural"></div>
                    <div class="color-dot" style="background:#2A2A2A" title="Titanio Negro"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Titanio Blanco"></div>
                    <div class="color-dot" style="background:#3B4C6B" title="Titanio Azul"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 6 unidades</div>
                <div class="product-price"><span class="old-price">$10,499</span>$8,499</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2015%20Pro" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('15pro')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 15 -->
            <div class="product-card card-glass" data-name="iPhone 15">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-15-model-unselect-gallery-1-202309?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1693011129000" alt="iPhone 15" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 15</h3>
                <p class="card-desc">USB-C por primera vez. Dynamic Island. Gran camara de 48 MP. El iPhone mas versatil del momento.</p>
                <div class="product-specs">
                    <span class="spec-tag">A16</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">USB-C</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#2C2C2E" title="Negro"></div>
                    <div class="color-dot" style="background:#E3E4E5" title="Azul"></div>
                    <div class="color-dot" style="background:#FCEBD4" title="Amarillo"></div>
                    <div class="color-dot" style="background:#F2ADDA" title="Rosa"></div>
                    <div class="color-dot" style="background:#A3C9A8" title="Verde"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 10 unidades</div>
                <div class="product-price"><span class="old-price">$9,999</span>$8,499</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2015" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('15')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 14 Pro Max -->
            <div class="product-card card-glass" data-name="iPhone 14 Pro Max">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-14-pro-max-model-unselect-gallery-1-202209?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1660753619946" alt="iPhone 14 Pro Max" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 14 Pro Max</h3>
                <p class="card-desc">Dynamic Island. Chip A16 Bionic. Pantalla siempre activa. Sistema de camara Pro con zoom 3x.</p>
                <div class="product-specs">
                    <span class="spec-tag">A16</span>
                    <span class="spec-tag">256 GB</span>
                    <span class="spec-tag">Dynamic Island</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#4A4A4C" title="Negro Espacial"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Plata"></div>
                    <div class="color-dot" style="background:#F5E0D0" title="Dorado"></div>
                    <div class="color-dot" style="background:#5B4F7A" title="Morado Profundo"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 7 unidades</div>
                <div class="product-price"><span class="old-price">$9,799</span>$8,299</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2014%20Pro%20Max" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('14pm')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 14 -->
            <div class="product-card card-glass" data-name="iPhone 14">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-14-model-unselect-gallery-1-202209?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1660753619946" alt="iPhone 14" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 14</h3>
                <p class="card-desc">Camara dual de 12 MP con modo accion. Chip A15 Bionic. Gran rendimiento a precio accesible.</p>
                <div class="product-specs">
                    <span class="spec-tag">A15</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">Modo Accion</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#2C2C2E" title="Medianoche"></div>
                    <div class="color-dot" style="background:#E3E4E5" title="Estrella"></div>
                    <div class="color-dot" style="background:#A3C9A8" title="Verde"></div>
                    <div class="color-dot" style="background:#6B8FA8" title="Azul"></div>
                    <div class="color-dot" style="background:#D4A5D4" title="Morado"></div>
                    <div class="color-dot" style="background:#F5E0A0" title="Amarillo"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 9 unidades</div>
                <div class="product-price"><span class="old-price">$6,499</span>$5,299</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2014" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('14')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 13 Pro Max -->
            <div class="product-card card-glass" data-name="iPhone 13 Pro Max">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-13-pro-max-model-unselect-gallery-1-202109?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1637589178000" alt="iPhone 13 Pro Max" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 13 Pro Max</h3>
                <p class="card-desc">Pantalla ProMotion 120Hz. Sistema de camara Pro con modo macro. Aun una bestia en 2026.</p>
                <div class="product-specs">
                    <span class="spec-tag">A15</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">ProMotion</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#4A4A4C" title="Grafito"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Plata"></div>
                    <div class="color-dot" style="background:#F5E0D0" title="Oro"></div>
                    <div class="color-dot" style="background:#6B8FA8" title="Sierra Blue"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 6 unidades</div>
                <div class="product-price"><span class="old-price">$7,499</span>$5,999</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2013%20Pro%20Max" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('13pm')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 13 -->
            <div class="product-card card-glass" data-name="iPhone 13">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-13-model-unselect-gallery-1-202109?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1637589178000" alt="iPhone 13" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 13</h3>
                <p class="card-desc">Chip A15 Bionic. Camara dual avanzada con estabilizacion sensor-shift. Gran autonomia de bateria.</p>
                <div class="product-specs">
                    <span class="spec-tag">A15</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">Cinematic</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#2C2C2E" title="Medianoche"></div>
                    <div class="color-dot" style="background:#E3E4E5" title="Estrella"></div>
                    <div class="color-dot" style="background:#A3C9A8" title="Verde"></div>
                    <div class="color-dot" style="background:#F2ADDA" title="Rosa"></div>
                    <div class="color-dot" style="background:#6B8FA8" title="Azul"></div>
                    <div class="color-dot" style="background:#C4302B" title="Product Red"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 8 unidades</div>
                <div class="product-price"><span class="old-price">$4,499</span>$2,999</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2013" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('13')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 12 Pro Max -->
            <div class="product-card card-glass" data-name="iPhone 12 Pro Max">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-12-pro-max-model-unselect-gallery-1-202010?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1633022292000" alt="iPhone 12 Pro Max" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 12 Pro Max</h3>
                <p class="card-desc">Pantalla Super Retina XDR de 6.7". Sistema de camara Pro con LiDAR. Diseno de acero inoxidable.</p>
                <div class="product-specs">
                    <span class="spec-tag">A14</span>
                    <span class="spec-tag">128 GB</span>
                    <span class="spec-tag">LiDAR</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#4A4A4C" title="Grafito"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Plata"></div>
                    <div class="color-dot" style="background:#F5E0D0" title="Oro"></div>
                    <div class="color-dot
" style="background:#6B8FA8" title="Azul Pacifico"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 7 unidades</div>
                <div class="product-price"><span class="old-price">$5,999</span>$4,499</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2012%20Pro%20Max" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('12pm')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 12 -->
            <div class="product-card card-glass" data-name="iPhone 12">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-12-model-unselect-gallery-1-202010?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1633022292000" alt="iPhone 12" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 12</h3>
                <p class="card-desc">Primer iPhone con 5G. Chip A14 Bionic. Diseno de borde plano. Camara dual de 12 MP.</p>
                <div class="product-specs">
                    <span class="spec-tag">A14</span>
                    <span class="spec-tag">64 GB</span>
                    <span class="spec-tag">5G</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#2C2C2E" title="Negro"></div>
                    <div class="color-dot" style="background:#E3E4E5" title="Blanco"></div>
                    <div class="color-dot" style="background:#6B8FA8" title="Azul"></div>
                    <div class="color-dot" style="background:#A3C9A8" title="Verde"></div>
                    <div class="color-dot" style="background:#D4A5D4" title="Morado"></div>
                    <div class="color-dot" style="background:#C4302B" title="Product Red"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 10 unidades</div>
                <div class="product-price"><span class="old-price">$3,999</span>$2,199</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2012" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('12')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 11 Pro Max -->
            <div class="product-card card-glass" data-name="iPhone 11 Pro Max">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-11-pro-max-model-unselect-gallery-1-201909?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1567208469000" alt="iPhone 11 Pro Max" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 11 Pro Max</h3>
                <p class="card-desc">Triple camara 12 MP. Pantalla Super Retina XDR de 6.5". Bateria que dura todo el dia. Aun una bestia.</p>
                <div class="product-specs">
                    <span class="spec-tag">A13</span>
                    <span class="spec-tag">64 GB</span>
                    <span class="spec-tag">Triple cam</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#4A4A4C" title="Gris Espacial"></div>
                    <div class="color-dot" style="background:#C4C4C4" title="Plata"></div>
                    <div class="color-dot" style="background:#F5E0D0" title="Oro"></div>
                    <div class="color-dot" style="background:#1C3A1C" title="Verde Noche"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 8 unidades</div>
                <div class="product-price"><span class="old-price">$4,999</span>$3,499</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2011%20Pro%20Max" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('11pm')">Ver mas</button>
                </div>
            </div>

            <!-- iPhone 11 -->
            <div class="product-card card-glass" data-name="iPhone 11">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/iphone-11-model-unselect-gallery-1-201909?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1567208469000" alt="iPhone 11" onerror="this.style.display='none'; this.parentElement.innerHTML='&#128241;'">
                </div>
                <h3 class="card-title">iPhone 11</h3>
                <p class="card-desc">Camara dual 12 MP con modo noche. Chip A13 Bionic. El iPhone mas vendido de la historia. Excelente precio.</p>
                <div class="product-specs">
                    <span class="spec-tag">A13</span>
                    <span class="spec-tag">64 GB</span>
                    <span class="spec-tag">Modo Noche</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#2C2C2E" title="Negro"></div>
                    <div class="color-dot" style="background:#E3E4E5" title="Blanco"></div>
                    <div class="color-dot" style="background:#A3C9A8" title="Verde"></div>
                    <div class="color-dot" style="background:#F5E0A0" title="Amarillo"></div>
                    <div class="color-dot" style="background:#D4A5D4" title="Morado"></div>
                    <div class="color-dot" style="background:#C4302B" title="Product Red"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 9 unidades</div>
                <div class="product-price"><span class="old-price">$2,499</span>$1,599</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20iPhone%2011" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('11')">Ver mas</button>
                </div>
            </div>
        </div>

        <!-- OFERTA RELAMPAGO -->
        <div class="lightning-deal" id="oferta">
            <div class="lightning-badge">&#9889; Oferta Relampago</div>
            <h3 class="lightning-title">iPhone 11 - Precio de locura</h3>
            <p class="lightning-desc">Solo por hoy. Quedan pocas unidades. No dejes pasar esta oportunidad.</p>
            <div class="countdown-timer">23:59:59</div>
            <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Vi%20la%20oferta%20relampago%20del%20iPhone%2011" class="lightning-btn" target="_blank">Aprovechar oferta &#8594;</a>
        </div>

        <!-- AIRPODS SECTION -->
        <div class="section-label" id="airpods">Audio</div>
        <h2 class="section-title">&#127911; AirPods</h2>
        <p class="section-subtitle">Audio premium de Apple. Cancelacion de ruido, audio espacial y mas.</p>

        <div class="product-grid">
            <!-- AirPods Pro 2 USB-C -->
            <div class="product-card card-glass" data-name="AirPods Pro 2 USB-C">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/airpods-pro-2-hero-select-202309?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1693083223266" alt="AirPods Pro 2" onerror="this.style.display='none'; this.parentElement.innerHTML='&#127911;'">
                </div>
                <h3 class="card-title">AirPods Pro 2 USB-C</h3>
                <p class="card-desc">Chip H2. Cancelacion de ruido 2x mejor. Audio adaptativo. El mejor audio de Apple.</p>
                <div class="product-specs">
                    <span class="spec-tag">H2</span>
                    <span class="spec-tag">ANC 2x</span>
                    <span class="spec-tag">USB-C</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#F5F5F7" title="Blanco"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 7 unidades</div>
                <div class="product-price"><span class="old-price">$4,499</span>$2,999</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20los%20AirPods%20Pro%202%20USB-C" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('ap4anc')">Ver mas</button>
                </div>
            </div>

            <!-- AirPods 3 -->
            <div class="product-card card-glass" data-name="AirPods 3">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/airpods-3rd-gen-select-202110?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1632922776000" alt="AirPods 3" onerror="this.style.display='none'; this.parentElement.innerHTML='&#127911;'">
                </div>
                <h3 class="card-title">AirPods 3</h3>
                <p class="card-desc">Audio espacial con seguimiento dinamico. Resistencia al agua. Ajuste personalizado.</p>
                <div class="product-specs">
                    <span class="spec-tag">H1</span>
                    <span class="spec-tag">Spatial</span>
                    <span class="spec-tag">MagSafe</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#F5F5F7" title="Blanco"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 8 unidades</div>
                <div class="product-price"><span class="old-price">$2,799</span>$1,899</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesan%20los%20AirPods%203" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('ap3pro')">Ver mas</button>
                </div>
            </div>

            <!-- AirPods Pro 1ra Gen -->
            <div class="product-card card-glass" data-name="AirPods Pro">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/airpods-pro-select-202206?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1655384503000" alt="AirPods Pro" onerror="this.style.display='none'; this.parentElement.innerHTML='&#127911;'">
                </div>
                <h3 class="card-title">AirPods Pro</h3>
                <p class="card-desc">Cancelacion activa de ruido. Audio espacial. Modo transparencia. Gran precio calidad.</p>
                <div class="product-specs">
                    <span class="spec-tag">H1</span>
                    <span class="spec-tag">ANC</span>
                    <span class="spec-tag">Wireless</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#F5F5F7" title="Blanco"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 6 unidades</div>
                <div class="product-price"><span class="old-price">$2,199</span>$1,499</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesan%20los%20AirPods%20Pro" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('ap2pro')">Ver mas</button>
                </div>
            </div>

            <!-- AirPods 2 -->
            <div class="product-card card-glass" data-name="AirPods 2">
                <div class="card-visual-glass">
                    <img src="https://store.storeimages.cdn-apple.com/4982/as-images.apple.com/is/airpods-2nd-gen-select-201903?wid=5120&amp;hei=2880&amp;fmt=webp&amp;qlt=70&amp;.v=1551489688000" alt="AirPods 2" onerror="this.style.display='none'; this.parentElement.innerHTML='&#127911;'">
                </div>
                <h3 class="card-title">AirPods 2</h3>
                <p class="card-desc">Hey Siri siempre activo. Conexion instantanea. Hasta 5 horas de audio. Basicos pero potentes.</p>
                <div class="product-specs">
                    <span class="spec-tag">H1</span>
                    <span class="spec-tag">Siri</span>
                    <span class="spec-tag">5h audio</span>
                </div>
                <div class="color-dots">
                    <div class="color-dot active" style="background:#F5F5F7" title="Blanco"></div>
                </div>
                <div class="stock-counter"><span class="pulse-dot"></span>Solo quedan 10 unidades</div>
                <div class="product-price"><span class="old-price">$1,799</span>$1,199</div>
                <div class="card-actions">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesan%20los%20AirPods%202" class="btn-primary" target="_blank">Cotizar</a>
                    <button class="btn-ghost" onclick="openModal('ap2')">Ver mas</button>
                </div>
            </div>
        </div>

        <!-- TESTIMONIOS -->
        <div class="section-label" id="reviews">Opiniones</div>
        <h2 class="section-title">&#128172; Testimonios</h2>
        <p class="section-subtitle">Lo que dicen nuestros clientes reales.</p>

        <div class="testimonials-grid">
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128104;</div>
                <div class="testimonial-name">Carlos M.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"Excelente equipo, llego super rapido y en perfecto estado. La bateria al 100% como dijeron. 100% recomendado!"</p>
                <div class="testimonial-product">iPhone 15 Pro</div>
            </div>
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128105;</div>
                <div class="testimonial-name">Mariana S.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"Amo el color rosa, se ve hermoso. El dynamic island es super util. Envio gratis DHL genial."</p>
                <div class="testimonial-product">iPhone 15</div>
            </div>
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128104;</div>
                <div class="testimonial-name">Eduardo N.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"El 120Hz se nota brutalmente. La camara macro es una locura. Excelente compra, iNexus nunca falla."</p>
                <div class="testimonial-product">iPhone 13 Pro Max</div>
            </div>
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128105;</div>
                <div class="testimonial-name">Fernando J.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"La cancelacion de ruido es brutal, no escucho nada en el metro. Vale cada peso. Envio rapidisimo."</p>
                <div class="testimonial-product">AirPods Pro 2</div>
            </div>
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128104;</div>
                <div class="testimonial-name">Martin C.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"Excelente telefono para empezar en iOS. El amarillo es muy llamativo. Todo funciona al 100, muy satisfecho."</p>
                <div class="testimonial-product">iPhone 11</div>
            </div>
            <div class="testimonial-card">
                <div class="testimonial-avatar">&#128105;</div>
                <div class="testimonial-name">Valentina R.</div>
                <div class="testimonial-stars">&#11088;&#11088;&#11088;&#11088;&#11088;</div>
                <p class="testimonial-text">"El verde noche es el color mas bonito que he visto. La triple camara sigue siendo excelente. Super recomendado."</p>
                <div class="testimonial-product">iPhone 11 Pro Max</div>
            </div>
        </div>

        <!-- ENVIO / GARANTIA -->
        <div class="section-label" id="garantia">Confianza</div>
        <h2 class="section-title">&#128666; Envio Seguro</h2>
        <p class="section-subtitle">Te entregamos guia de rastreo en cada compra. Sigue tu paquete en tiempo real.</p>

        <div class="shipping-grid">
            <div class="shipping-card">
                <div class="shipping-icon">&#127758;</div>
                <h4>Envio Gratis DHL</h4>
                <p>Llega hasta tu domicilio. Envios a todo Mexico. 2-3 dias habiles.</p>
            </div>
            <div class="shipping-card">
                <div class="shipping-icon">&#9889;</div>
                <h4>Express 24h</h4>
                <p>Solo +$150 pesos. Llega al dia siguiente. Costo extra pero velocidad maxima.</p>
            </div>
            <div class="shipping-card">
                <div class="shipping-icon">&#128274;</div>
                <h4>Pago Seguro</h4>
                <p>Efectivo en OXXO, PayPal, transferencia bancaria. 10% OFF pagando por transferencia.</p>
            </div>
            <div class="shipping-card">
                <div class="shipping-icon">&#128737;</div>
                <h4>Garantia 30 Dias</h4>
                <p>30 dias de prueba. Si no te convence, devolucion garantizada. Sin preguntas.</p>
            </div>
        </div>

        <!-- DESCUENTO PRIMERA COMPRA -->
        <div class="first-buy-banner">
            <div class="first-buy-content">
                <h3>&#127873; 5% de descuento en tu primera compra</h3>
                <p>Escribenos por WhatsApp y menciona "PRIMERACOMPRA" para obtener tu descuento.</p>
                <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Quiero%20mi%205%25%20de%20descuento%20en%20mi%20primera%20compra" class="first-buy-btn" target="_blank">Obtener descuento &#8594;</a>
            </div>
        </div>
    </div>

    <!-- MODAL -->
    <div class="modal-overlay" id="productModal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeModal()">&#10005;</button>
            <div id="modalBody"></div>
        </div>
    </div>

    <footer>
        <div class="footer-logo">i<span>Nexus</span> Store</div>
        <p>iPhones &amp; AirPods de calidad garantizada. Envios a todo Mexico.</p>
        <div class="footer-links">
            <a href="https://wa.me/528136800550" target="_blank">WhatsApp</a>
            <a href="#iphones">iPhones</a>
            <a href="#airpods">AirPods</a>
            <a href="#garantia">Garantia</a>
        </div>
        <div class="footer-copy">
            &copy; 2026 iNexus Store. Todos los derechos reservados. | CDMX, Mexico
        </div>
    </footer>

    <script>
        // ========== THEME TOGGLE ==========
        function toggleTheme() {
            document.body.classList.toggle('light-mode');
            localStorage.setItem('theme', document.body.classList.contains('light-mode') ? 'light' : 'dark');
        }
        if (localStorage.getItem('theme') === 'light') document.body.classList.add('light-mode');

        // ========== SEARCH ==========
        function openSearch() {
            document.getElementById('searchOverlay').classList.add('active');
            document.getElementById('searchInput').focus();
        }
        function closeSearch() {
            document.getElementById('searchOverlay').classList.remove('active');
        }
        function filterProducts(query) {
            const cards = document.querySelectorAll('.product-card');
            cards.forEach(card => {
                const name = card.getAttribute('data-name').toLowerCase();
                card.style.display = name.includes(query.toLowerCase()) ? 'block' : 'none';
            });
        }

        // ========== MODAL DATA ==========
        const modalData = {
            '15pro': {
                title: 'iPhone 15 Pro',
                specs: ['Chip A17 Pro - El mas potente de Apple', 'Titanio de grado aeroespacial', 'Camara Pro 48 MP con zoom 3x', 'Pantalla Super Retina XDR 6.1"', 'USB-C - Primera vez en iPhone', 'Action Button personalizable'],
                colors: ['Titanio Natural', 'Titanio Negro', 'Titanio Blanco', 'Titanio Azul'],
                reviews: [
                    {name: 'Carlos M.', stars: 5, text: 'Excelente equipo, llego super rapido y en perfecto estado. La bateria al 100% como dijeron. 100% recomendado!'},
                    {name: 'Ana G.', stars: 4, text: 'Muy buen precio, el titanio se ve increible. Unico detalle es que la caja no venia sellada pero el equipo esta impecable.'},
                    {name: 'Luis R.', stars: 5, text: 'Segunda compra aqui, nunca me han fallado. El envio DHL fue rapidisimo, 2 dias a Guadalajara.'}
                ],
                stock: 6,
                oldPrice: '$10,499',
                price: '$8,499'
            },
            '15': {
                title: 'iPhone 15',
                specs: ['Chip A16 Bionic', 'Dynamic Island - Primera vez en base', 'Camara principal 48 MP', 'USB-C universal', 'Ceramic Shield frontal', 'Resistencia al agua IP68'],
                colors: ['Negro', 'Azul', 'Amarillo', 'Rosa', 'Verde'],
                reviews: [
                    {name: 'Mariana S.', stars: 5, text: 'Amo el color rosa, se ve hermoso. El dynamic island es super util para las notificaciones. Envio gratis DHL genial.'},
                    {name: 'Pedro H.', stars: 4, text: 'Buen telefono, la camara me sorprendio. Llego bien empacado y con mica de regalo. Gracias iNexus!'},
                    {name: 'Diana K.', stars: 5, text: 'Compre el amarillo, es mas bonito en persona. Todo funciona perfecto, Face ID rapidisimo.'}
                ],
                stock: 10,
                oldPrice: '$9,999',
                price: '$8,499'
            },
            '14pm': {
                title: 'iPhone 14 Pro Max',
                specs: ['Chip A16 Bionic', 'Dynamic Island revolucionario', 'Pantalla siempre activa', 'Camara Pro 48 MP', 'Zoom optico 3x', 'Deteccion de choques'],
                colors: ['Negro Espacial', 'Plata', 'Dorado', 'Morado Profundo'],
                reviews: [
                    {name: 'Roberto F.', stars: 5, text: 'El morado profundo es una locura de bonito. La pantalla siempre activa es super util. Muy satisfecho con la compra.'},
                    {name: 'Sofia L.', stars: 4, text: 'Gran telefono, la camara es espectacular de noche. El envio express de 24hrs valio la pena, llego al otro dia temprano.'},
                    {name: 'Jorge T.', stars: 5, text: 'El mejor iPhone que he tenido. La bateria me dura todo el dia y mas. iNexus siempre cumple.'}
                ],
                stock: 7,
                oldPrice: '$9,799',
                price: '$8,299'
            },
            '14': {
                title: 'iPhone 14',
                specs: ['Chip A15 Bionic', 'Camara dual 12 MP', 'Modo Accion para video', 'Deteccion de choques', 'Ceramic Shield', 'Resistencia IP68'],
                colors: ['Medianoche', 'Estrella', 'Verde', 'Azul', 'Morado', 'Amarillo'],
                reviews: [
                    {name: 'Fernanda P.', stars: 4, text: 'Muy buen telefono por el precio. El modo accion para videos es increible. Recomiendo el color verde, se ve elegante.'},
                    {name: 'Miguel A.', stars: 5, text: 'Compre dos, uno para mi y otro para mi esposa. Ambos llegaron perfectos. El descuento por transferencia ayudo bastante.'},
                    {name: 'Lucia V.', stars: 4, text: 'Todo bien, el telefono funciona al 100. Solo que tardaron un poco en responder por whatsapp pero al final todo salio bien.'}
                ],
                stock: 9,
                oldPrice: '$6,499',
                price: '$5,299'
            },
            '13pm': {
                title: 'iPhone 13 Pro Max',
                specs: ['Chip A15 Bionic', 'Pantalla ProMotion 120Hz', 'Camara Pro con modo macro', 'Zoom optico 3x', 'Bateria de larga duracion', 'Ceramic Shield'],
                colors: ['Grafito', 'Plata', 'Oro', 'Sierra Blue'],
                reviews: [
                    {name: 'Eduardo N.', stars: 5, text: 'El 120Hz se nota brutalmente. Todo se ve mas fluido. La camara macro es una locura para fotos de detalles. Excelente compra.'},
                    {name: 'Patricia C.', stars: 5, text: 'Mi tercer iPhone comprado aqui. Nunca una queja. El sierra blue es precioso en persona, las fotos no le hacen justicia.'},
                    {name: 'Andres W.', stars: 4, text: 'Gran telefono, la bateria es increible me dura dia y medio. El envio fue rapido y bien empacado.'}
                ],
                stock: 6,
                oldPrice: '$7,499',
                price: '$5,999'
            },
            '13': {
                title: 'iPhone 13',
                specs: ['Chip A15 Bionic', 'Camara dual avanzada', 'Estabilizacion sensor-shift', 'Modo Cinematic', 'Bateria mejorada', '5G ultraveloz'],
                colors: ['Medianoche', 'Estrella', 'Verde', 'Rosa', 'Azul', 'Product Red'],
                reviews: [
                    {name: 'Gabriela R.', stars: 5, text: 'El modo cinematic es una locura, parece pelicula profesional. Muy feliz con mi compra, el rosa esta divino.'},
                    {name: 'Hector S.', stars: 4, text: 'Buen equipo, todo funciona perfecto. El precio esta muy competitivo comparado con otros lados. Recomendado.'},
                    {name: 'Natalia B.', stars: 5, text: 'Llego en 2 dias a Monterrey! El telefono impecable, parece nuevo. La garantia de 30 dias me dio mucha confianza.'}
                ],
                stock: 8,
                oldPrice: '$4,499',
                price: '$2,999'
            },
            '12pm': {
                title: 'iPhone 12 Pro Max',
                specs: ['Chip A14 Bionic', 'Pantalla 6.7" Super Retina XDR', 'Camara Pro con LiDAR', 'Zoom optico 2.5x', 'Acero inoxidable', '5G'],
                colors: ['Grafito', 'Plata', 'Oro', 'Azul Pacifico'],
                reviews: [
                    {name: 'Ricardo D.', stars: 5, text: 'El LiDAR es genial para escanear habitaciones. El telefono sigue siendo una bestia en 2026. Gran precio iNexus.'},
                    {name: 'Monica J.', stars: 4, text: 'El azul pacifico es hermoso. Todo funciona al 100, camara excelente. Unico detalle la caja un poco golpeada pero el equipo perfecto.'},
                    {name: 'Daniel K.', stars: 5, text: 'Segunda compra, esta vez para mi hermano. El grafito se ve super elegante y profesional. Envio gratis DHL excelente.'}
                ],
                stock: 7,
                oldPrice: '$5,999',
                price: '$4,499'
            },
            '12': {
                title: 'iPhone 12',
                specs: ['Chip A14 Bionic - Primer 5nm', '5G de alta velocidad', 'Diseno de borde plano', 'Camara dual 12 MP', 'Ceramic Shield', 'Resistencia IP68'],
                colors: ['Negro', 'Blanco', 'Azul', 'Verde', 'Morado', 'Product Red'],
                reviews: [
                    {name: 'Alejandro M.', stars: 4, text: 'Mi primer iPhone y estoy encantado. El morado es precioso y el 5G vuela. Buen servicio de iNexus, respondieron todas mis dudas.'},
                    {name: 'Carmen H.', stars: 5, text: 'Los compre para mi hermana y le encantaron. Faciles de usar y buen sonido. El envio fue rapidisimo a Puebla.'},
                    {name: 'Bruno P.', stars: 4, text: 'Buen telefono para el precio. La camara es muy buena de dia, de noche un poco ruidosa pero normal para el modelo. Recomendado.'}
                ],
                stock: 10,
                oldPrice: '$3,999',
                price: '$2,199'
            },
            '11pm': {
                title: 'iPhone 11 Pro Max',
                specs: ['Chip A13 Bionic', 'Triple camara 12 MP', 'Pantalla Super Retina XDR 6.5"', 'Bateria todo el dia', 'Resistencia IP68', 'Face ID avanzado'],
                colors: ['Gris Espacial', 'Plata', 'Oro', 'Verde Noche'],
                reviews: [
                    {name: 'Valentina R.', stars: 5, text: 'El verde noche es el color mas bonito que he visto en un iPhone. La triple camara sigue siendo excelente. Super recomendado.'},
                    {name: 'Oscar L.', stars: 4, text: 'Gran telefono, la bateria dura muchisimo. El envio fue rapido y seguro. iNexus muy confiables.'},
                    {name: 'Isabela T.', stars: 5, text: 'Para el precio esta increible. El telefono funciona perfecto, camara excelente. El 10% de descuento por transferencia genial.'}
                ],
                stock: 8,
                oldPrice: '$4,999',
                price: '$3,499'
            },
            '11': {
                title: 'iPhone 11',
                specs: ['Chip A13 Bionic', 'Camara dual 12 MP', 'Pantalla Liquid Retina 6.1"', 'Bateria de larga duracion', 'Face ID', 'Resistencia IP68'],
                colors: ['Negro', 'Blanco', 'Verde', 'Amarillo', 'Morado', 'Product Red'],
                reviews: [
                    {name: 'Martin C.', stars: 5, text: 'Excelente telefono para empezar en iOS. El amarillo es muy llamativo y bonito. Todo funciona al 100, muy satisfecho.'},
                    {name: 'Paula G.', stars: 4, text: 'Buen precio, buen telefono. La camara es mejor de lo que esperaba para ser un 11. El envio DHL fue puntual.'},
                    {name: 'Santiago V.', stars: 5, text: 'Compre el morado para mi mama y esta feliz. Facil de usar, camara buena y bateria que dura todo el dia. Gracias iNexus!'}
                ],
                stock: 9,
                oldPrice: '$2,499',
                price: '$1,599'
            },
            'ap4anc': {
                title: 'AirPods Pro 2 (USB-C)',
                specs: ['Chip H2 de Apple', 'Cancelacion activa de ruido 2x mejor', 'Audio adaptativo', 'Modo transparencia', 'Estuche con MagSafe y altavoz', 'Hasta 6 horas de audio'],
                colors: ['Blanco'],
                reviews: [
                    {name: 'Fernando J.', stars: 5, text: 'La cancelacion de ruido es brutal, no escucho nada en el metro. El audio es increiblemente claro. Vale cada peso.'},
                    {name: 'Camila D.', stars: 5, text: 'Los mejores audifonos que he tenido. El estuche con altavoz para encontrarlos es genial. Envio super rapido iNexus.'},
                    {name: 'Raul M.', stars: 4, text: 'Muy buenos, el audio adaptativo es una locura. A veces se desconectan un segundo pero se reconectan solos. Recomendados.'}
                ],
                stock: 7,
                oldPrice: '$4,499',
                price: '$2,999'
            },
            'ap3pro': {
                title: 'AirPods 3',
                specs: ['Chip H1', 'Audio espacial con seguimiento dinamico', 'Resistencia al sudor y agua', 'Hasta 6 horas de audio', 'Estuche de carga MagSafe', 'Ajuste personalizado'],
                colors: ['Blanco'],
                reviews: [
                    {name: 'Laura P.', stars: 5, text: 'El audio espacial es una experiencia increible. Se escuchan super bien y son comodos. Perfectos para el gym.'},
                    {name: 'Diego N.', stars: 4, text: 'Buenos audifonos, el ajuste es mejor que los anteriores. El audio espacial para peliculas es genial. Recomendados.'},
                    {name: 'Ximena R.', stars: 5, text: 'Llegaron en 2 dias, sellados y originales. El estuche MagSafe carga rapidisimo. Muy feliz con la compra.'}
                ],
                stock: 8,
                oldPrice: '$2,799',
                price: '$1,899'
            },
            'ap2pro': {
                title: 'AirPods Pro (1ra Gen)',
                specs: ['Chip H1', 'Cancelacion activa de ruido', 'Audio espacial', 'Modo transparencia', 'Estuche inalambrico', 'Hasta 4.5 horas de audio'],
                colors: ['Blanco'],
                reviews: [
                    {name: 'Tomas B.', stars: 5, text: 'Para el precio estan increibles. La cancelacion de ruido sigue siendo muy buena. Perfectos para trabajar en casa.'},
                    {name: 'Renata S.', stars: 4, text: 'Buen sonido, comodos para usar horas. El estuche carga bien. El envio fue gratis y rapido. Recomendado iNexus.'},
                    {name: 'Ivan H.', stars: 5, text: 'Segunda vez que compro aqui, esta vez los AirPods. Todo perfecto, originales y funcionando al 100. Gracias!'}
                ],
                stock: 6,
                oldPrice: '$2,199',
                price: '$1,499'
            },
            'ap2': {
                title: 'AirPods 2',
                specs: ['Chip H1', 'Hey Siri siempre activo', 'Conexion instantanea', 'Estuche de carga', 'Hasta 5 horas de audio', 'Doble toque para controles'],
                colors: ['Blanco'],
                reviews: [
                    {name: 'Julia M.', stars: 4, text: 'Basicos pero cumplen perfecto. Se conectan rapidisimo al iPhone. Buenos para llamadas y musica. Buen precio.'},
                    {name: 'Esteban K.', stars: 5, text: 'Los compre para mi hermana y le encantaron. Faciles de usar y buen sonido. El envio fue rapidisimo a Puebla.'},
                    {name: 'Marisol A.', stars: 4, text: 'Simples y funcionales. Para el precio no se puede pedir mas. iNexus siempre entrega lo que promete.'}
                ],
                stock: 10,
                oldPrice: '$1,799',
                price: '$1,199'
            }
        };

        // ========== MODAL FUNCTIONS ==========
        function openModal(id) {
            const d = modalData[id];
            if (!d) return;
            let reviewsHtml = '';
            d.reviews.forEach(r => {
                let s = '';
                for(let i=0;i<5;i++) s += i < r.stars ? '&#11088;' : '&#9734;';
                reviewsHtml += `<div class="review-item"><div class="review-header"><span class="review-name">${r.name}</span><span class="review-stars">${s}</span></div><p class="review-text">"${r.text}"</p></div>`;
            });
            let colorsHtml = d.colors.map((c,i) => `<div class="color-dot ${i===0?'active':''}" style="background:${getColorHex(c)}" title="${c}"></div>`).join('');
            let specsHtml = d.specs.map(s => `<li>${s}</li>`).join('');

            document.getElementById('modalBody').innerHTML = `
                <div class="modal-header">
                    <h2 class="modal-title">${d.title}</h2>
                    <div class="modal-price"><span class="old-price">${d.oldPrice}</span>${d.price}</div>
                </div>
                <div class="modal-section">
                    <h4>Especificaciones</h4>
                    <ul class="modal-specs">${specsHtml}</ul>
                </div>
                <div class="modal-section">
                    <h4>Colores disponibles</h4>
                    <div class="color-dots">${colorsHtml}</div>
                </div>
                <div class="stock-counter" style="margin:20px 0;"><span class="pulse-dot"></span>Solo quedan ${d.stock} unidades</div>
                <div class="modal-section">
                    <h4>Resenas de clientes</h4>
                    <div class="reviews-list">${reviewsHtml}</div>
                </div>
                <div style="text-align:center;margin-top:24px;">
                    <a href="https://wa.me/528136800550?text=Hola%20iNexus!%20Me%20interesa%20el%20${encodeURIComponent(d.title)}" class="card-btn" target="_blank" style="display:inline-flex;">Cotizar por WhatsApp &#8594;</a>
                    <p style="margin-top:12px;font-size:13px;color:#555;">O escribenos para dejar tu resena por WhatsApp</p>
                </div>
            `;
            document.getElementById('productModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }
        function closeModal() {
            document.getElementById('productModal').classList.remove('active');
            document.body.style.overflow = '';
        }
        function getColorHex(name) {
            const map = {
                'Titanio Natural':'#5C5B57','Titanio Negro':'#2A2A2A','Titanio Blanco':'#C4C4C4','Titanio Azul':'#3B4C6B',
                'Negro':'#2C2C2E','Negro Espacial':'#4A4A4C','Gris Espacial':'#4A4A4C','Medianoche':'#2C2C2E',
                'Blanco':'#E3E4E5','Estrella':'#E3E4E5','Plata':'#C4C4C4',
                'Azul':'#6B8FA8','Azul Pacifico':'#6B8FA8','Sierra Blue':'#6B8FA8',
                'Verde':'#A3C9A8','Verde Noche':'#1C3A1C',
                'Amarillo':'#F5E0A0','Rosa':'#F2ADDA','Morado':'#D4A5D4','Morado Profundo':'#5B4F7A',
                'Dorado':'#F5E0D0','Oro':'#F5E0D0','Grafito':'#4A4A4C',
                'Product Red':'#C4302B','Blanco':'#F5F5F7'
            };
            return map[name] || '#999';
        }

        // ========== SCROLL ANIMATIONS ==========
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1 });
        document.querySelectorAll('.product-card, .feature-pill, .testimonial-card, .shipping-card').forEach(el => {
            el.classList.add('scroll-animate');
            observer.observe(el);
        });

        // ========== LIGHTNING DEAL COUNTDOWN ==========
        function updateCountdown() {
            const end = new Date();
            end.setHours(23, 59, 59, 999);
            const now = new Date();
            const diff = end - now;
            const h = Math.floor(diff / 3600000);
            const m = Math.floor((diff % 3600000) / 60000);
            const s = Math.floor((diff % 60000) / 1000);
            document.querySelectorAll('.countdown-timer').forEach(el => {
                el.textContent = `${String(h).padStart(2,'0')}:${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
            });
        }
        setInterval(updateCountdown, 1000);
        updateCountdown();

        // ========== COLOR DOTS INTERACTION ==========
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('color-dot')) {
                e.target.parentElement.querySelectorAll('.color-dot').forEach(d => d.classList.remove('active'));
                e.target.classList.add('active');
            }
        });

        // ========== CLOSE MODAL ON ESCAPE ==========
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') closeModal();
        });
        document.getElementById('productModal').addEventListener('click', function(e) {
            if (e.target === this) closeModal();
        });
    </script>
</body>
</html>
