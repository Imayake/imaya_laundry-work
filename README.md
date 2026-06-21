# imaya_laundry-work
laundry 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Imaya Laundry - Premium Laundry Services</title>
    
    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" />
    <!-- Font Awesome 6 -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet" />
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet" />
    
    <style>
        :root {
            --primary: #00d4ff;
            --secondary: #7b2ffc;
            --whatsapp: #25D366;
            --dark: #0a0a1a;
            --gray-500: #8a8aaa;
            --gray-300: #c4c4d4;
            --white: #ffffff;
            --glass: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
            --font-future: 'Orbitron', sans-serif;
        }
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Inter', sans-serif;
            color: var(--white);
            background: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }
        a { text-decoration: none; color: var(--primary); }
        
        /* Background Animation */
        .bg-animation {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
            overflow: hidden;
            background: var(--dark);
        }
        .bg-animation .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.12;
            animation: orbFloat 20s ease-in-out infinite;
        }
        .bg-animation .orb:nth-child(1) {
            width: 500px; height: 500px;
            background: var(--primary);
            top: -100px; left: -100px;
        }
        .bg-animation .orb:nth-child(2) {
            width: 400px; height: 400px;
            background: var(--secondary);
            bottom: -100px; right: -100px;
            animation-delay: -7s;
        }
        .bg-animation .orb:nth-child(3) {
            width: 300px; height: 300px;
            background: #ffd700;
            top: 50%; left: 50%;
            transform: translate(-50%, -50%);
            animation-delay: -14s;
        }
        @keyframes orbFloat {
            0%, 100% { transform: translate(0, 0) scale(1); }
            25% { transform: translate(100px, -50px) scale(1.2); }
            50% { transform: translate(-50px, 100px) scale(0.8); }
            75% { transform: translate(50px, -100px) scale(1.1); }
        }
        
        /* Notification Bar */
        .notification-bar {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--white);
            padding: 10px 0;
            text-align: center;
            font-size: 0.9rem;
            font-weight: 500;
            position: fixed;
            top: 0; left: 0; right: 0;
            z-index: 1060;
            animation: slideDown 0.5s ease;
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.3);
        }
        @keyframes slideDown {
            from { transform: translateY(-100%); }
            to { transform: translateY(0); }
        }
        .notification-bar .highlight { color: #ffd700; font-weight: 700; }
        .notification-bar .close-btn {
            position: absolute;
            right: 20px; top: 50%;
            transform: translateY(-50%);
            background: none; border: none;
            color: rgba(255,255,255,0.6);
            cursor: pointer;
            font-size: 1.2rem;
        }
        .notification-bar .close-btn:hover { color: white; }
        
        /* Navigation */
        .navbar-custom {
            background: rgba(10, 10, 26, 0.85);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(0, 212, 255, 0.1);
            padding: 12px 0;
            transition: all 0.3s ease;
            position: fixed;
            top: 44px; left: 0; right: 0;
            z-index: 1050;
            box-shadow: 0 4px 30px rgba(0,0,0,0.3);
        }
        .navbar-custom.scrolled { top: 0; }
        .navbar-custom .brand {
            font-family: var(--font-future);
            font-weight: 900;
            font-size: 1.6rem;
            color: var(--white);
            display: flex;
            align-items: center;
            gap: 12px;
        }
        .navbar-custom .brand .brand-icon {
            width: 44px; height: 44px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 1.4rem;
            box-shadow: 0 0 30px rgba(0, 212, 255, 0.3);
            animation: pulse-icon 2s ease-in-out infinite;
        }
        @keyframes pulse-icon {
            0%, 100% { box-shadow: 0 0 20px rgba(0, 212, 255, 0.3); }
            50% { box-shadow: 0 0 50px rgba(0, 212, 255, 0.3); }
        }
        .navbar-custom .nav-link {
            font-weight: 600;
            color: var(--gray-300) !important;
            padding: 8px 18px !important;
            transition: all 0.3s ease;
            text-transform: uppercase;
            font-size: 0.8rem;
            letter-spacing: 1px;
        }
        .navbar-custom .nav-link:hover { color: var(--primary) !important; }
        .btn-whatsapp-nav {
            background: var(--whatsapp);
            color: var(--white) !important;
            border-radius: 50px;
            padding: 8px 24px !important;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 0 30px rgba(37, 211, 102, 0.3);
        }
        .btn-whatsapp-nav:hover {
            background: #1DA851;
            transform: translateY(-3px) scale(1.05);
        }
        
        /* Hero Section */
        .hero-section {
            padding: 160px 0 80px;
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        .hero-section .grid-overlay {
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background-image: 
                linear-gradient(rgba(0, 212, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 212, 255, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
            pointer-events: none;
            animation: gridMove 20s linear infinite;
        }
        @keyframes gridMove {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }
        .hero-content { position: relative; z-index: 2; }
        .hero-content h1 {
            font-family: var(--font-future);
            font-size: 4.2rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 20px;
        }
        .hero-content h1 .highlight {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero-content .sub-headline {
            font-size: 1.2rem;
            color: var(--gray-300);
            max-width: 520px;
            margin-bottom: 30px;
        }
        .btn-primary-custom {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--white);
            padding: 16px 44px;
            border-radius: 50px;
            font-weight: 600;
            border: none;
            transition: all 0.3s ease;
            display: inline-block;
            font-size: 1rem;
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
        }
        .btn-primary-custom:hover {
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 0 60px rgba(0, 212, 255, 0.3);
            color: var(--white);
        }
        .btn-outline-custom {
            border: 2px solid var(--primary);
            color: var(--primary);
            padding: 16px 44px;
            border-radius: 50px;
            font-weight: 600;
            background: transparent;
            transition: all 0.3s ease;
            display: inline-block;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            cursor: pointer;
            margin-left: 10px;
        }
        .btn-outline-custom:hover {
            background: var(--primary);
            color: var(--white);
            transform: translateY(-4px) scale(1.05);
        }
        .hero-stats {
            display: flex;
            gap: 48px;
            flex-wrap: wrap;
            margin-top: 40px;
        }
        .hero-stats .stat-item .number {
            font-size: 2.2rem;
            font-weight: 800;
            color: var(--primary);
            display: block;
        }
        .hero-stats .stat-item .label {
            font-size: 0.85rem;
            color: var(--gray-500);
            font-weight: 500;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .hero-image { position: relative; z-index: 2; }
        .hero-image .main-image {
            border-radius: 24px;
            box-shadow: 0 0 60px rgba(0, 212, 255, 0.1);
            width: 100%;
            max-width: 550px;
            border: 1px solid rgba(0, 212, 255, 0.1);
        }
        
        /* Services Section */
        .services-section { padding: 80px 0; }
        .section-header {
            text-align: center;
            max-width: 700px;
            margin: 0 auto 56px;
        }
        .section-header .subtitle {
            display: inline-block;
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.2);
            color: var(--primary);
            padding: 4px 18px;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 12px;
        }
        .section-header h2 {
            font-family: var(--font-future);
            font-size: 2.8rem;
            font-weight: 900;
            color: var(--white);
        }
        .section-header h2 span {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .section-header p { color: var(--gray-500); font-size: 1.1rem; }
        
        .service-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 32px 24px;
            text-align: center;
            transition: all 0.3s ease;
            height: 100%;
        }
        .service-card:hover {
            transform: translateY(-12px);
            border-color: var(--primary);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.2);
        }
        .service-card .icon-wrapper {
            width: 80px; height: 80px;
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 18px;
            font-size: 34px;
            color: var(--primary);
            transition: all 0.3s ease;
        }
        .service-card:hover .icon-wrapper {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--white);
            transform: rotate(-8deg) scale(1.1);
        }
        .service-card h5 { font-weight: 700; margin-bottom: 8px; color: var(--white); font-size: 1.2rem; }
        .service-card p { color: var(--gray-500); font-size: 0.95rem; }
        .service-card .price {
            display: inline-block;
            background: rgba(0, 212, 255, 0.1);
            border: 1px solid rgba(0, 212, 255, 0.2);
            padding: 4px 16px;
            border-radius: 50px;
            font-weight: 700;
            color: var(--primary);
            margin-top: 12px;
        }
        
        /* Pricing Section */
        .pricing-section { padding: 80px 0; background: #111128; }
        .pricing-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 32px 24px;
            text-align: center;
            transition: all 0.3s ease;
            height: 100%;
            position: relative;
        }
        .pricing-card.popular {
            border-color: var(--primary);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.2);
            transform: scale(1.02);
        }
        .pricing-card.popular::before {
            content: '🔥 Most Popular';
            position: absolute;
            top: 12px; right: 12px;
            background: linear-gradient(135deg, #ffd700, #ff6b35);
            color: var(--white);
            padding: 4px 14px;
            border-radius: 50px;
            font-size: 0.7rem;
            font-weight: 700;
        }
        .pricing-card:hover {
            transform: translateY(-8px);
            border-color: var(--primary);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.2);
        }
        .pricing-card.popular:hover { transform: translateY(-8px) scale(1.02); }
        .pricing-card .pricing-icon { font-size: 48px; color: var(--primary); margin-bottom: 16px; }
        .pricing-card h4 { font-family: var(--font-future); color: var(--white); margin-bottom: 8px; }
        .pricing-card .price {
            font-size: 3rem;
            font-weight: 900;
            color: var(--primary);
        }
        .pricing-card .price span { font-size: 1rem; color: var(--gray-500); font-weight: 400; }
        .pricing-card .features {
            list-style: none;
            padding: 0;
            margin: 20px 0;
            text-align: left;
        }
        .pricing-card .features li {
            padding: 8px 0;
            color: var(--gray-300);
            border-bottom: 1px solid var(--glass-border);
        }
        .pricing-card .features li:last-child { border-bottom: none; }
        .pricing-card .features li i { color: var(--primary); margin-right: 10px; width: 20px; }
        .btn-pricing {
            width: 100%;
            padding: 12px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border: none;
            border-radius: 50px;
            color: var(--white);
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .btn-pricing:hover {
            transform: scale(1.03);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.3);
        }
        
        /* Testimonials */
        .testimonials-section { padding: 80px 0; background: var(--dark); }
        .testimonial-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 28px;
            height: 100%;
            transition: all 0.3s ease;
        }
        .testimonial-card:hover {
            border-color: var(--primary);
            box-shadow: 0 0 40px rgba(0, 212, 255, 0.2);
            transform: translateY(-4px);
        }
        .testimonial-card .stars { color: #ffd700; font-size: 1rem; margin-bottom: 10px; }
        .testimonial-card blockquote {
            font-style: italic;
            color: var(--gray-300);
            font-size: 0.98rem;
            line-height: 1.7;
            margin-bottom: 16px;
        }
        .testimonial-card .client { display: flex; align-items: center; gap: 14px; }
        .testimonial-card .client .avatar {
            width: 48px; height: 48px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 1.1rem;
            flex-shrink: 0;
        }
        .testimonial-card .client .info .name { font-weight: 600; color: var(--white); margin: 0; }
        .testimonial-card .client .info .location { color: var(--gray-500); font-size: 0.85rem; }
        
        /* Location Section */
        .location-section { padding: 80px 0; background: #111128; }
        .location-card {
            background: var(--glass);
            backdrop-filter: blur(20px);
            border: 1px solid var(--glass-border);
            border-radius: 16px;
            padding: 32px;
            height: 100%;
        }
        .location-card h4 { font-weight: 800; color: var(--white); margin-bottom: 20px; }
        .location-card .detail { display: flex; gap: 14px; margin-bottom: 16px; }
        .location-card .detail i { font-size: 20px; color: var(--primary); min-width: 28px; margin-top: 2px; }
        .location-card .detail p { margin: 0; color: var(--gray-300); }
        .location-card .detail strong { color: var(--white); }
        .map-wrapper {
            border-radius: 16px;
            overflow: hidden;
            height: 350px;
            background: #1a1a3a;
            border: 1px solid var(--glass-border);
        }
        .map-wrapper iframe { width: 100%; height: 100%; border: 0; }
        
        /* Footer */
        .footer-section {
            background: #111128;
            color: var(--gray-500);
            padding: 60px 0 30px;
            border-top: 1px solid var(--glass-border);
        }
        .footer-section .brand {
            font-family: var(--font-future);
            font-size: 2rem;
            font-weight: 900;
            color: var(--white);
            display: block;
        }
        .footer-section h5 { color: var(--white); font-weight: 700; margin-bottom: 18px; }
        .footer-section a { color: var(--gray-500); transition: all 0.3s ease; display: inline-block; }
        .footer-section a:hover { color: var(--primary); transform: translateX(4px); }
        .footer-section .social-links { display: flex; gap: 10px; }
        .footer-section .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px; height: 40px;
            border-radius: 50%;
            background: var(--glass);
            border: 1px solid var(--glass-border);
            transition: all 0.3s ease;
        }
        .footer-section .social-links a:hover {
            background: var(--whatsapp);
            border-color: var(--whatsapp);
            color: var(--white);
            transform: translateY(-3px);
        }
        .footer-section .footer-bottom {
            border-top: 1px solid var(--glass-border);
            padding-top: 24px;
            margin-top: 36px;
            text-align: center;
            font-size: 0.9rem;
        }
        
        /* WhatsApp Float */
        .whatsapp-float {
            position: fixed;
            bottom: 28px;
            right: 28px;
            z-index: 9999;
            width: 64px; height: 64px;
            background: var(--whatsapp);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-size: 34px;
            box-shadow: 0 0 40px rgba(37, 211, 102, 0.3);
            transition: all 0.3s ease;
            text-decoration: none;
            animation: pulse-whatsapp 2.5s infinite;
        }
        .whatsapp-float:hover {
            transform: scale(1.1) rotate(-5deg);
            background: #1DA851;
            color: var(--white);
        }
        @keyframes pulse-whatsapp {
            0% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0.4); }
            70% { box-shadow: 0 0 0 25px rgba(37, 211, 102, 0); }
            100% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0); }
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero-section { padding: 140px 0 60px; }
            .hero-content h1 { font-size: 3rem; }
            .section-header h2 { font-size: 2.2rem; }
        }
        @media (max-width: 768px) {
            .hero-section { padding: 120px 0 40px; text-align: center; }
            .hero-content h1 { font-size: 2.2rem; }
            .hero-content .sub-headline { max-width: 100%; }
            .hero-stats { justify-content: center; gap: 24px; }
            .hero-stats .stat-item .number { font-size: 1.6rem; }
            .hero-image .main-image { max-width: 100%; }
            .section-header h2 { font-size: 1.8rem; }
            .btn-outline-custom { margin-left: 0; margin-top: 10px; }
            .pricing-card.popular { transform: scale(1); }
            .map-wrapper { height: 220px; margin-top: 20px; }
            .whatsapp-float { width: 56px; height: 56px; font-size: 28px; bottom: 20px; right: 20px; }
        }
        @media (max-width: 480px) {
            .hero-content h1 { font-size: 1.8rem; }
            .btn-primary-custom, .btn-outline-custom { display: block; width: 100%; text-align: center; }
            .btn-outline-custom { margin-left: 0; margin-top: 10px; }
            .section-header h2 { font-size: 1.5rem; }
            .pricing-card .price { font-size: 2.2rem; }
        }
    </style>
</head>
<body>

<!-- ===== ANIMATED BACKGROUND ===== -->
<div class="bg-animation">
    <div class="orb"></div>
    <div class="orb"></div>
    <div class="orb"></div>
</div>

<!-- ===== NOTIFICATION BAR ===== -->
<div class="notification-bar" id="notificationBar">
    🚀 <span class="highlight">20% OFF</span> Your First Order! Use Code: <span class="highlight">IMAYA20</span>
    <button class="close-btn" onclick="document.getElementById('notificationBar').style.display='none'">
        <i class="fas fa-times"></i>
    </button>
</div>

<!-- ===== NAVIGATION ===== -->
<nav class="navbar navbar-expand-lg navbar-custom" id="navbar">
    <div class="container">
        <a class="brand" href="#">
            <span class="brand-icon"><i class="fas fa-robot"></i></span>
            <span>IMAYA <span style="font-size: 0.5rem; font-weight: 600; color: var(--primary); letter-spacing: 4px; text-transform: uppercase; display: block;">AI Laundry</span></span>
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarMain">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarMain">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0 align-items-lg-center">
                <li class="nav-item"><a class="nav-link" href="#home">Home</a></li>
                <li class="nav-item"><a class="nav-link" href="#services">Services</a></li>
                <li class="nav-item"><a class="nav-link" href="#pricing">Pricing</a></li>
                <li class="nav-item"><a class="nav-link" href="#testimonials">Reviews</a></li>
                <li class="nav-item"><a class="nav-link" href="#location">Contact</a></li>
                <li class="nav-item">
                    <a class="nav-link btn-whatsapp-nav" href="https://wa.me/254700000000?text=Hi%20Imaya!%20I'd%20like%20to%20book%20a%20pickup." target="_blank">
                        <i class="fab fa-whatsapp"></i> Chat
                    </a>
                </li>
            </ul>
        </div>
    </div>
</nav>

<!-- ===== HERO SECTION ===== -->
<section class="hero-section" id="home">
    <div class="grid-overlay"></div>
    <div class="container">
        <div class="row align-items-center">
            <div class="col-lg-6">
                <div class="hero-content">
                    <h1>
                        <span class="highlight">Imaya</span><br />
                        Smart Laundry<br />
                        Made Simple
                    </h1>
                    <p class="sub-headline">
                        Experience premium laundry services with AI-powered efficiency. 
                        Free pickup & delivery, eco-friendly, and 100% satisfaction guaranteed.
                    </p>
                    <div>
                        <a href="#pricing" class="btn-primary-custom"><i class="fas fa-calendar-check"></i> Book Now</a>
                        <a href="#services" class="btn-outline-custom"><i class="fas fa-chevron-right"></i> Explore</a>
                    </div>
                    <div class="hero-stats">
                        <div class="stat-item">
                            <span class="number">5,000+</span>
                            <span class="label">Happy Customers</span>
                        </div>
                        <div class="stat-item">
                            <span class="number">99%</span>
                            <span class="label">On-Time Delivery</span>
                        </div>
                        <div class="stat-item">
                            <span class="number">4.9★</span>
                            <span class="label">Average Rating</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-lg-6">
                <div class="hero-image">
                    <img src="https://images.unsplash.com/photo-1545173168-9f1947eebb7f?w=600&h=400&fit=crop&crop=center" 
                         alt="Imaya Laundry Service" class="main-image" />
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ===== SERVICES SECTION ===== -->
<section class="services-section" id="services">
    <div class="container">
        <div class="section-header">
            <div class="subtitle"><i class="fas fa-star"></i> Premium Services</div>
            <h2>What <span>Imaya</span> Offers</h2>
            <p>AI-powered laundry solutions designed for modern lifestyles</p>
        </div>
        <div class="row g-4">
            <div class="col-md-6 col-lg-3">
                <div class="service-card">
                    <div class="icon-wrapper"><i class="fas fa-tshirt"></i></div>
                    <h5>Wash & Fold</h5>
                    <p>AI-optimized wash, dry, and fold for everyday clothes.</p>
                    <div class="price">from <span style="font-size:1.3rem;">$10</span>/bag</div>
                </div>
            </div>
            <div class="col-md-6 col-lg-3">
                <div class="service-card">
                    <div class="icon-wrapper"><i class="fas fa-shirt"></i></div>
                    <h5>Dry Cleaning</h5>
                    <p>Expert dry cleaning for suits, dresses, and delicate fabrics.</p>
                    <div class="price">from <span style="font-size:1.3rem;">$15</span>/item</div>
                </div>
            </div>
            <div class="col-md-6 col-lg-3">
                <div class="service-card">
                    <div class="icon-wrapper"><i class="fas fa-iron"></i></div>
                    <h5>Ironing Service</h5>
                    <p>Crisp, professional ironing for all your garments.</p>
                    <div class="price">from <span style="font-size:1.3rem;">$5</span>/item</div>
                </div>
            </div>
            <div class="col-md-6 col-lg-3">
                <div class="service-card">
                    <div class="icon-wrapper"><i class="fas fa-truck"></i></div>
                    <h5>Pickup & Delivery</h5>
                    <p>AI-routed free pickup and delivery within our service area.</p>
                    <div class="price"><span style="font-size:1.3rem;">Free</span></div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ===== PRICING SECTION ===== -->
<section class="pricing-section" id="pricing">
    <div class="container">
        <div class="section-header">
            <div class="subtitle"><i class="fas fa-tags"></i> Pricing Plans</div>
            <h2>Choose Your <span>Package</span></h2>
            <p>Flexible plans designed to fit your lifestyle and budget</p>
        </div>
        <div class="row g-4">
            <div class="col-md-4">
                <div class="pricing-card">
                    <div class="pricing-icon"><i class="fas fa-user"></i></div>
                    <h4>Basic</h4>
                    <div class="price">$29 <span>/month</span></div>
                    <ul class="features">
                        <li><i class="fas fa-check"></i> 10 Items Wash & Fold</li>
                        <li><i class="fas fa-check"></i> Standard Delivery</li>
                        <li><i class="fas fa-check"></i> 24/7 Support</li>
                        <li><i class="fas fa-times" style="color:#555;"></i> Priority Pickup</li>
                    </ul>
                    <button class="btn-pricing" onclick="alert('Starting Basic Plan!')">Get Started</button>
                </div>
            </div>
            <div class="col-md-4">
                <div class="pricing-card popular">
                    <div class="pricing-icon"><i class="fas fa-crown"></i></div>
                    <h4>Premium</h4>
                    <div class="price">$59 <span>/month</span></div>
                    <ul class="features">
                        <li><i class="fas fa-check"></i> 30 Items Wash & Fold</li>
                        <li><i class="fas fa-check"></i> Priority Delivery</li>
                        <li><i class="fas fa-check"></i> AI Copilot Access</li>
                        <li><i class="fas fa-check"></i> Free Pickup & Delivery</li>
                    </ul>
                    <button class="btn-pricing" onclick="alert('Starting Premium Plan!')">Get Started</button>
                </div>
            </div>
            <div class="col-md-4">
                <div class="pricing-card">
                    <div class="pricing-icon"><i class="fas fa-building"></i></div>
                    <h4>Enterprise</h4>
                    <div class="price">$99 <span>/month</span></div>
                    <ul class="features">
                        <li><i class="fas fa-check"></i> Unlimited Items</li>
                        <li><i class="fas fa-check"></i> Same-Day Delivery</li>
                        <li><i class="fas fa-check"></i> Dedicated AI Copilot</li>
                        <li><i class="fas fa-check"></i> Priority Support</li>
                    </ul>
                    <button class="btn-pricing" onclick="alert('Contact us for Enterprise Plan!')">Contact Sales</button>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ===== TESTIMONIALS SECTION ===== -->
<section class="testimonials-section" id="testimonials">
    <div class="container">
        <div class="section-header">
            <div class="subtitle"><i class="fas fa-comments"></i> Testimonials</div>
            <h2>What Our <span>Customers</span> Say</h2>
            <p>Real reviews from real people who trust Imaya</p>
        </div>
        <div class="row g-4">
            <div class="col-md-4">
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <blockquote>"Imaya is incredible! AI-powered booking, same-day delivery, and my clothes smell amazing."</blockquote>
                    <div class="client">
                        <div class="avatar">JM</div>
                        <div class="info">
                            <p class="name">James M.</p>
                            <span class="location">Westlands, Nairobi</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <blockquote>"The AI technology makes it so efficient! I've never had such a seamless laundry experience."</blockquote>
                    <div class="client">
                        <div class="avatar">AK</div>
                        <div class="info">
                            <p class="name">Alice K.</p>
                            <span class="location">Kilimani, Nairobi</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <blockquote>"Imaya's eco-friendly approach and AI precision saved me time and money. Highly recommended!"</blockquote>
                    <div class="client">
                        <div class="avatar">BO</div>
                        <div class="info">
                            <p class="name">Brian O.</p>
                            <span class="location">Lavington, Nairobi</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ===== LOCATION SECTION ===== -->
<section class="location-section" id="location">
    <div class="container">
        <div class="row g-4">
            <div class="col-lg-5">
                <div class="location-card">
                    <h4><i class="fas fa-location-dot" style="color: var(--primary);"></i> Contact <span style="color: var(--primary);">Imaya</span></h4>
                    <div class="detail">
                        <i class="fas fa-map-pin"></i>
                        <p><strong>Address:</strong> 123 Laundry Street, Nairobi, Kenya</p>
                    </div>
                    <div class="detail">
                        <i class="fas fa-phone"></i>
                        <p><strong>Phone:</strong> <a href="tel:+254700000000" style="color: var(--primary);">+254 700 000 000</a></p>
                    </div>
                    <div class="detail">
                        <i class="fas fa-envelope"></i>
                        <p><strong>Email:</strong> <a href="mailto:info@imayalaundry.com" style="color: var(--primary);">info@imayalaundry.com</a></p>
                    </div>
                    <div class="detail">
                        <i class="fas fa-clock"></i>
                        <p><strong>Hours:</strong> Mon-Sun: 7:00 AM - 9:00 PM</p>
                    </div>
                    <div class="mt-3">
                        <a href="https://wa.me/254700000000?text=Hi%20Imaya!%20I'd%20like%20to%20book%20a%20pickup." target="_blank" class="btn-primary-custom" style="width:100%; justify-content:center; display:flex;">
                            <i class="fab fa-whatsapp"></i> Chat on WhatsApp
                        </a>
                    </div>
                </div>
            </div>
            <div class="col-lg-7">
                <div class="map-wrapper">
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d15955.234567890123!2d36.8219!3d-1.2921!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x182f1745c5d4e6a9%3A0x8e3f5e7a2d0c1b3!2sNairobi%2C%20Kenya!5e0!3m2!1sen!2s!4v1234567890123" 
                            allowfullscreen="" loading="lazy"></iframe>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- ===== FOOTER ===== -->
<footer class="footer-section">
    <div class="container">
        <div class="row g-4">
            <div class="col-md-4">
                <span class="brand">IMAYA</span>
                <p style="color: var(--gray-500); margin-top: 10px;">AI-powered laundry solutions for the modern world.</p>
                <div class="social-links mt-3">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-whatsapp"></i></a>
                </div>
            </div>
            <div class="col-md-2">
                <h5>Quick Links</h5>
                <ul style="list-style:none; padding:0;">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#pricing">Pricing</a></li>
                    <li><a href="#location">Contact</a></li>
                </ul>
            </div>
            <div class="col-md-2">
                <h5>Services</h5>
                <ul style="list-style:none; padding:0;">
                    <li><a href="#services">Wash & Fold</a></li>
                    <li><a href="#services">Dry Cleaning</a></li>
                    <li><a href="#services">Ironing</a></li>
                    <li><a href="#services">Pickup</a></li>
                </ul>
            </div>
            <div class="col-md-4">
                <h5>Newsletter</h5>
                <p style="color: var(--gray-500);">Subscribe for exclusive deals</p>
                <div class="input-group">
                    <input type="email" class="form-control" placeholder="Your email" style="background: var(--glass); border: 1px solid var(--glass-border); color: var(--white); border-radius: 50px 0 0 50px; padding: 10px 20px;">
                    <button class="btn" style="background: linear-gradient(135deg, var(--primary), var(--secondary)); color: var(--white); border-radius: 0 50px 50px 0; padding: 10px 20px;">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 <strong style="color: var(--primary);">Imaya Laundry</strong>. All rights reserved. 🚀 AI-Powered</p>
        </div>
    </div>
</footer>

<!-- ===== WHATSAPP FLOATING BUTTON ===== -->
<a href="https://wa.me/254700000000?text=Hi%20Imaya!%20I'd%20like%20to%20book%20a%20pickup." target="_blank" class="whatsapp-float">
    <i class="fab fa-whatsapp"></i>
</a>

<!-- ===== BOOTSTRAP JS ===== -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>

<script>
    // Navbar scroll effect
    window.addEventListener('scroll', function() {
        const navbar = document.getElementById('navbar');
        if (window.scrollY > 50) {
            navbar.classList.add('scrolled');
        } else {
            navbar.classList.remove('scrolled');
        }
    });

    // Smooth scroll for navigation
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
            e.preventDefault();
            const target = document.querySelector(this.getAttribute('href'));
            if (target) {
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });
    });

    // Pricing button clicks
    document.querySelectorAll('.btn-pricing').forEach(btn => {
        btn.addEventListener('click', function() {
            const plan = this.closest('.pricing-card').querySelector('h4').textContent;
            alert('🚀 You selected the ' + plan + ' plan! Our team will contact you shortly.');
        });
    });

    console.log('🚀 Imaya Laundry is live!');
</script>
</body>
</html>
