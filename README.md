<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
    <title>ركن الرجل | صالون الحلاقة الفاخر للرجال</title>
    <!-- PWA Meta Tags -->
    <meta name="theme-color" content="#000000">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <link rel="manifest" href="manifest.json">
    
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Swiper JS for Mobile Sliders -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css">
    
    <style>
        :root {
            --gold: #D4AF37;
            --gold-light: #F5DEB3;
            --dark: #0a0a0a;
            --darker: #050505;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }
        
        body {
            font-family: 'Cairo', sans-serif;
            background-color: var(--dark);
            color: white;
            overflow-x: hidden;
            direction: rtl;
        }
        
        /* Enhanced Mobile Nav */
        .mobile-nav {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            padding: 15px 20px;
            border-bottom: 1px solid rgba(212, 175, 55, 0.2);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .logo-icon {
            width: 45px;
            height: 45px;
            background: linear-gradient(135deg, var(--gold), var(--gold-light));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }
        
        .logo-text {
            font-size: 1.4rem;
            font-weight: 900;
            letter-spacing: -0.5px;
            background: linear-gradient(to right, var(--gold), var(--gold-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .hamburger {
            width: 45px;
            height: 45px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .hamburger span {
            width: 25px;
            height: 2px;
            background: var(--gold);
            border-radius: 10px;
            transition: all 0.3s ease;
        }
        
        .hamburger.active span:nth-child(1) {
            transform: rotate(45deg) translate(6px, 6px);
        }
        
        .hamburger.active span:nth-child(2) {
            opacity: 0;
        }
        
        .hamburger.active span:nth-child(3) {
            transform: rotate(-45deg) translate(6px, -6px);
        }
        
        .mobile-menu {
            position: fixed;
            top: 75px;
            right: -100%;
            width: 85%;
            height: calc(100vh - 75px);
            background: rgba(5, 5, 5, 0.98);
            backdrop-filter: blur(30px);
            z-index: 999;
            padding: 30px;
            transition: right 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55);
            border-left: 1px solid rgba(212, 175, 55, 0.2);
            display: flex;
            flex-direction: column;
        }
        
        .mobile-menu.active {
            right: 0;
        }
        
        .menu-item {
            padding: 20px 0;
            font-size: 1.2rem;
            font-weight: 700;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            align-items: center;
            gap: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .menu-item i {
            color: var(--gold);
            width: 24px;
        }
        
        .menu-item:hover {
            color: var(--gold);
            padding-right: 10px;
        }
        
        .call-btn-mobile {
            margin-top: auto;
            background: linear-gradient(135deg, var(--gold), #B8860B);
            color: black;
            padding: 18px;
            border-radius: 15px;
            font-weight: 900;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            box-shadow: 0 5px 20px rgba(212, 175, 55, 0.4);
            transition: all 0.3s ease;
        }
        
        .call-btn-mobile:active {
            transform: scale(0.97);
        }
        
        /* Hero Section for Mobile */
        .hero-mobile {
            min-height: 100vh;
            padding: 120px 20px 50px;
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        .hero-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.9)), 
                        url('https://images.unsplash.com/photo-1585747860715-2ba37e788b70?auto=format&fit=crop&q=80&w=1600');
            background-size: cover;
            background-position: center;
            z-index: -1;
        }
        
        .hero-tag {
            color: var(--gold);
            font-weight: 800;
            font-size: 0.9rem;
            letter-spacing: 2px;
            margin-bottom: 20px;
            display: inline-block;
            padding: 8px 15px;
            background: rgba(212, 175, 55, 0.1);
            border-radius: 50px;
            border: 1px solid rgba(212, 175, 55, 0.3);
        }
        
        .hero-title {
            font-size: 2.8rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 25px;
        }
        
        .hero-title span {
            background: linear-gradient(to right, var(--gold), var(--gold-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-style: italic;
        }
        
        .hero-desc {
            font-size: 1.1rem;
            line-height: 1.6;
            color: rgba(255, 255, 255, 0.7);
            margin-bottom: 40px;
        }
        
        .cta-buttons {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-bottom: 40px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--gold), #B8860B);
            color: black;
            padding: 20px 30px;
            border-radius: 15px;
            font-weight: 900;
            font-size: 1.1rem;
            text-align: center;
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.3);
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .btn-primary:active {
            transform: scale(0.97);
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.3);
        }
        
        .btn-secondary {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: white;
            padding: 20px 30px;
            border-radius: 15px;
            font-weight: 700;
            font-size: 1.1rem;
            text-align: center;
            transition: all 0.3s ease;
        }
        
        .btn-secondary:active {
            background: rgba(255, 255, 255, 0.1);
        }
        
        /* Quick Stats */
        .quick-stats {
            display: flex;
            justify-content: space-between;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            padding: 20px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .stat-item {
            text-align: center;
            flex: 1;
        }
        
        .stat-number {
            font-size: 1.8rem;
            font-weight: 900;
            color: var(--gold);
            display: block;
        }
        
        .stat-label {
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.5);
            margin-top: 5px;
        }
        
        /* Services Section - Mobile Optimized */
        .services-section {
            padding: 60px 20px;
            background: var(--darker);
        }
        
        .section-title {
            font-size: 2.2rem;
            font-weight: 900;
            margin-bottom: 40px;
            text-align: center;
        }
        
        .section-title span {
            color: var(--gold);
        }
        
        .services-tabs {
            display: flex;
            overflow-x: auto;
            gap: 10px;
            margin-bottom: 30px;
            padding-bottom: 10px;
            -webkit-overflow-scrolling: touch;
        }
        
        .services-tabs::-webkit-scrollbar {
            height: 4px;
        }
        
        .tab-btn {
            white-space: nowrap;
            padding: 15px 25px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 50px;
            font-weight: 700;
            font-size: 1rem;
            border: none;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .tab-btn.active {
            background: linear-gradient(135deg, var(--gold), #B8860B);
            color: black;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
        }
        
        .service-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            padding: 25px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .service-card:active {
            transform: scale(0.98);
        }
        
        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 4px;
            height: 100%;
            background: var(--gold);
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .service-card:hover::before {
            opacity: 1;
        }
        
        .service-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .service-name {
            font-size: 1.2rem;
            font-weight: 800;
        }
        
        .service-price {
            font-size: 1.4rem;
            font-weight: 900;
            color: var(--gold);
        }
        
        .service-duration {
            display: flex;
            align-items: center;
            gap: 8px;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
            margin-top: 10px;
        }
        
        .book-service-btn {
            width: 100%;
            margin-top: 20px;
            padding: 15px;
            background: rgba(212, 175, 55, 0.1);
            border: 1px solid rgba(212, 175, 55, 0.3);
            color: var(--gold);
            border-radius: 12px;
            font-weight: 800;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .book-service-btn:active {
            background: rgba(212, 175, 55, 0.2);
        }
        
        /* Mobile Booking Slider */
        .booking-section {
            padding: 60px 20px;
            background: var(--dark);
        }
        
        .barbers-slider {
            margin: 30px 0;
        }
        
        .swiper {
            width: 100%;
            padding: 10px 0 40px !important;
        }
        
        .barber-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 25px;
            padding: 25px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.3s ease;
            height: auto;
        }
        
        .barber-card.selected {
            border-color: var(--gold);
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.2);
        }
        
        .barber-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            overflow: hidden;
            margin: 0 auto 20px;
            border: 3px solid transparent;
            transition: all 0.3s ease;
        }
        
        .barber-card.selected .barber-img {
            border-color: var(--gold);
        }
        
        .barber-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .barber-name {
            font-size: 1.4rem;
            font-weight: 900;
            margin-bottom: 5px;
        }
        
        .barber-title {
            color: var(--gold);
            font-weight: 700;
            font-size: 0.9rem;
            margin-bottom: 15px;
        }
        
        .barber-rating {
            display: flex;
            justify-content: center;
            gap: 5px;
            margin-bottom: 15px;
        }
        
        .star {
            color: #FFD700;
            font-size: 1.1rem;
        }
        
        /* Time Slots */
        .time-slots {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin: 25px 0;
        }
        
        .time-slot {
            padding: 15px 5px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 12px;
            text-align: center;
            font-weight: 700;
            border: 1px solid rgba(255, 255, 255, 0.05);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .time-slot.selected {
            background: rgba(212, 175, 55, 0.2);
            border-color: var(--gold);
            color: var(--gold);
        }
        
        /* Bottom Booking Bar - Fixed for Mobile */
        .booking-bar {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            padding: 15px 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
            transform: translateY(100%);
            transition: transform 0.4s ease;
            z-index: 1000;
        }
        
        .booking-bar.active {
            transform: translateY(0);
        }
        
        .booking-details {
            flex: 1;
        }
        
        .booking-summary {
            font-size: 0.95rem;
            margin-bottom: 5px;
        }
        
        .booking-price {
            font-size: 1.3rem;
            font-weight: 900;
            color: var(--gold);
        }
        
        .confirm-booking {
            background: linear-gradient(135deg, var(--gold), #B8860B);
            color: black;
            padding: 15px 25px;
            border-radius: 12px;
            font-weight: 900;
            font-size: 1rem;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .confirm-booking:active {
            transform: scale(0.95);
        }
        
        /* Footer Mobile */
        .mobile-footer {
            background: var(--darker);
            padding: 50px 20px 30px;
            margin-bottom: 80px;
        }
        
        .footer-section {
            margin-bottom: 40px;
        }
        
        .footer-title {
            font-size: 1.3rem;
            font-weight: 900;
            margin-bottom: 20px;
            color: var(--gold);
        }
        
        .branch-card {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .branch-name {
            font-weight: 800;
            margin-bottom: 5px;
        }
        
        .branch-hours {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.5);
            display: flex;
            align-items: center;
            gap: 8px;
            margin-top: 10px;
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icon {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            color: var(--gold);
            transition: all 0.3s ease;
        }
        
        .social-icon:active {
            background: rgba(212, 175, 55, 0.1);
            transform: scale(0.95);
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: rgba(255, 255, 255, 0.4);
            font-size: 0.85rem;
        }
        
        /* Modal */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            padding: 20px;
            opacity: 0;
            visibility: hidden;
            transition: all 0.4s ease;
        }
        
        .modal.active {
            opacity: 1;
            visibility: visible;
        }
        
        .modal-content {
            background: var(--darker);
            border-radius: 25px;
            padding: 40px 30px;
            max-width: 400px;
            width: 100%;
            border: 1px solid rgba(212, 175, 55, 0.2);
            text-align: center;
            transform: translateY(30px);
            transition: transform 0.4s ease;
        }
        
        .modal.active .modal-content {
            transform: translateY(0);
        }
        
        .modal-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--gold), #B8860B);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 25px;
            font-size: 2.5rem;
            color: black;
        }
        
        .modal-title {
            font-size: 1.8rem;
            font-weight: 900;
            margin-bottom: 15px;
        }
        
        .modal-message {
            color: rgba(255, 255, 255, 0.7);
            line-height: 1.6;
            margin-bottom: 30px;
        }
        
        .modal-btn {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, var(--gold), #B8860B);
            color: black;
            border-radius: 15px;
            font-weight: 900;
            font-size: 1.1rem;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .modal-btn:active {
            transform: scale(0.97);
        }
        
        /* Responsive Adjustments */
        @media (min-width: 768px) {
            .hero-title {
                font-size: 3.5rem;
            }
            
            .cta-buttons {
                flex-direction: row;
            }
            
            .services-grid {
                grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            }
            
            .time-slots {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        
        @media (min-width: 1024px) {
            .mobile-nav, .mobile-menu, .booking-bar {
                display: none;
            }
            
            .hero-mobile {
                padding: 100px 50px;
            }
        }
        
        /* Add to Home Screen Prompt */
        .add-to-home {
            position: fixed;
            bottom: 100px;
            left: 20px;
            right: 20px;
            background: var(--darker);
            border-radius: 20px;
            padding: 20px;
            border: 1px solid rgba(212, 175, 55, 0.3);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
            display: none;
            z-index: 1500;
            animation: slideUp 0.5s ease;
        }
        
        @keyframes slideUp {
            from {
                transform: translateY(100px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }
        
        .add-to-home-content {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .add-to-home-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--gold), #B8860B);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: black;
            flex-shrink: 0;
        }
        
        .add-to-home-text {
            flex: 1;
        }
        
        .add-to-home-title {
            font-weight: 900;
            margin-bottom: 5px;
        }
        
        .add-to-home-desc {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.6);
        }
        
        .add-to-home-close {
            background: none;
            border: none;
            color: rgba(255, 255, 255, 0.5);
            font-size: 1.2rem;
            cursor: pointer;
            padding: 5px;
        }
        
        .add-to-home-btn {
            background: rgba(212, 175, 55, 0.1);
            border: 1px solid rgba(212, 175, 55, 0.3);
            color: var(--gold);
            padding: 10px 20px;
            border-radius: 10px;
            font-weight: 800;
            margin-top: 15px;
            width: 100%;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .add-to-home-btn:active {
            background: rgba(212, 175, 55, 0.2);
        }
        
        /* Touch-friendly enhancements */
        button, .menu-item, .service-card, .barber-card, .time-slot {
            cursor: pointer;
            user-select: none;
        }
        
        /* Prevent zoom on input focus for iOS */
        @media (max-width: 768px) {
            input, select, textarea {
                font-size: 16px !important;
            }
        }
        
        /* Loading animation */
        .loader {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--dark);
            z-index: 3000;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            gap: 20px;
        }
        
        .loader.active {
            display: flex;
        }
        
        .spinner {
            width: 60px;
            height: 60px;
            border: 4px solid rgba(255, 255, 255, 0.1);
            border-top: 4px solid var(--gold);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Swipe hint for carousel */
        .swipe-hint {
            text-align: center;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
            margin-top: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .swipe-hint i {
            color: var(--gold);
            animation: swipe 2s infinite;
        }
        
        @keyframes swipe {
            0%, 100% { transform: translateX(0); }
            50% { transform: translateX(-10px); }
        }
    </style>
</head>
<body>
    <!-- Preloader -->
    <div class="loader" id="loader">
        <div class="spinner"></div>
        <div>جاري تحميل ركن الرجل...</div>
    </div>
    
    <!-- Mobile Navigation -->
    <nav class="mobile-nav">
        <div class="logo">
            <div class="logo-icon">
                <i class="fas fa-cut"></i>
            </div>
            <div class="logo-text">ركن الرجل</div>
        </div>
        
        <div class="hamburger" id="hamburger">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </nav>
    
    <!-- Mobile Menu -->
    <div class="mobile-menu" id="mobileMenu">
        <div class="menu-item" onclick="scrollToSection('hero')">
            <i class="fas fa-home"></i>
            الرئيسية
        </div>
        <div class="menu-item" onclick="scrollToSection('services')">
            <i class="fas fa-scissors"></i>
            الخدمات والأسعار
        </div>
        <div class="menu-item" onclick="scrollToSection('booking')">
            <i class="fas fa-calendar-check"></i>
            حجز موعد
        </div>
        <div class="menu-item" onclick="scrollToSection('branches')">
            <i class="fas fa-map-marker-alt"></i>
            الفروع
        </div>
        <div class="menu-item" onclick="scrollToSection('contact')">
            <i class="fas fa-phone-alt"></i>
            اتصل بنا
        </div>
        
        <a href="tel:0596160783" class="call-btn-mobile">
            <i class="fas fa-phone"></i>
            اتصل الآن: 0596160783
        </a>
    </div>
    
    <!-- Hero Section -->
    <section class="hero-mobile" id="hero">
        <div class="hero-bg"></div>
        
        <div class="hero-content">
            <div class="hero-tag">صالون الرجال الفاخر</div>
            <h1 class="hero-title">حلاقة <span>فاخرة</span> تجمع بين التقاليد والحداثة</h1>
            <p class="hero-desc">في ركن الرجل، نعيد تعريف أناقة الرجل بمزيج من الحرفية التقليدية وتقنيات العناية الحديثة. نحن لا نقص الشعر، بل نصنع مظهراً يعكس شخصيتك.</p>
            
            <div class="cta-buttons">
                <a href="#booking" class="btn-primary">
                    <i class="fas fa-calendar-alt"></i>
                    احجز موعدك الآن
                </a>
                <a href="#services" class="btn-secondary">تصفح الخدمات والأسعار</a>
            </div>
            
            <div class="quick-stats">
                <div class="stat-item">
                    <span class="stat-number">١٢٠٠+</span>
                    <span class="stat-label">عميل راضي</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">٨+</span>
                    <span class="stat-label">حلاق محترف</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">٣</span>
                    <span class="stat-label">فروع</span>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Services Section -->
    <section class="services-section" id="services">
        <h2 class="section-title">خدماتنا <span>وأسعارنا</span></h2>
        
        <div class="services-tabs">
            <button class="tab-btn active" data-tab="hair">الحلاقة والتشذيب</button>
            <button class="tab-btn" data-tab="care">العناية والصبغة</button>
            <button class="tab-btn" data-tab="face">أقنعة البشرة</button>
        </div>
        
        <div class="services-grid" id="servicesGrid">
            <!-- خدمات الحلاقة -->
            <div class="service-card" data-category="hair">
                <div class="service-header">
                    <div class="service-name">حلاقة شعر كاملة</div>
                    <div class="service-price">٣٠ ر.س</div>
                </div>
                <p>تشذيب وتصفيف احترافي باستخدام أحدث التقنيات</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٣٠ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="حلاقة شعر" data-price="30">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="hair">
                <div class="service-header">
                    <div class="service-name">حلاقة ذقن</div>
                    <div class="service-price">٢٥ ر.س</div>
                </div>
                <p>تشذيب الذقن والشارب بدقة عالية باستخدام أدوات معقمة</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٢٠ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="حلاقة ذقن" data-price="25">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="hair">
                <div class="service-header">
                    <div class="service-name">حلاقة شعر وذقن</div>
                    <div class="service-price">٥٥ ر.س</div>
                </div>
                <p>خدمة شاملة للحصول على مظهر متكامل وأنيق</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٥٠ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="حلاقة شعر وذقن" data-price="55">حجز هذه الخدمة</button>
            </div>
            
            <!-- خدمات العناية -->
            <div class="service-card" data-category="care">
                <div class="service-header">
                    <div class="service-name">صبغة ذقن</div>
                    <div class="service-price">٣٠ ر.س</div>
                </div>
                <p>صبغة طبيعية للذقن لإخفاء الشيب وإضفاء مظهر شبابي</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٢٥ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="صبغة ذقن" data-price="30">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="care">
                <div class="service-header">
                    <div class="service-name">تنظيف وجه عميق</div>
                    <div class="service-price">٤٠ ر.س</div>
                </div>
                <p>تنظيف عميق للبشرة لإزالة الشوائب والرؤوس السوداء</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٣٥ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="تنظيف وجه" data-price="40">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="care">
                <div class="service-header">
                    <div class="service-name">شمع الوجه</div>
                    <div class="service-price">٣٠ ر.س</div>
                </div>
                <p>إزالة شعر الوجه الزائد بطريقة الشمع للحصول على بشرة ناعمة</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٢٠ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="شمع وجه" data-price="30">حجز هذه الخدمة</button>
            </div>
            
            <!-- خدمات الأقنعة -->
            <div class="service-card" data-category="face">
                <div class="service-header">
                    <div class="service-name">قناع البخار</div>
                    <div class="service-price">٤٠ ر.س</div>
                </div>
                <p>بخار دافئ لفتح المسام وتنقية البشرة بعمق</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>٢٥ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="قناع بخار" data-price="40">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="face">
                <div class="service-header">
                    <div class="service-name">قناع الفحم</div>
                    <div class="service-price">٢٠ ر.س</div>
                </div>
                <p>قناع الفحم النشط لامتصاص السموم وتنقية البشرة</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>١٥ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="قناع الفحم" data-price="20">حجز هذه الخدمة</button>
            </div>
            
            <div class="service-card" data-category="face">
                <div class="service-header">
                    <div class="service-name">صنفرة الوجه</div>
                    <div class="service-price">٢٠ ر.س</div>
                </div>
                <p>تقشير لطيف لإزالة الخلايا الميتة وإنعاش البشرة</p>
                <div class="service-duration">
                    <i class="far fa-clock"></i>
                    <span>١٥ دقيقة</span>
                </div>
                <button class="book-service-btn" data-service="صنفرة وجه" data-price="20">حجز هذه الخدمة</button>
            </div>
        </div>
    </section>
    
    <!-- Booking Section -->
    <section class="booking-section" id="booking">
        <h2 class="section-title">احجز <span>موعدك الآن</span></h2>
        <p style="text-align: center; color: rgba(255,255,255,0.7); margin-bottom: 30px;">اختر حلاقك المفضل وموعدك المناسب</p>
        
        <!-- Barbers Slider -->
        <div class="barbers-slider">
            <div class="swipe-hint">
                <i class="fas fa-chevron-left"></i>
                اسحب لرؤية المزيد من الحلاقين
                <i class="fas fa-chevron-right"></i>
            </div>
            
            <div class="swiper">
                <div class="swiper-wrapper">
                    <!-- Barber 1 -->
                    <div class="swiper-slide">
                        <div class="barber-card" data-barber="أحمد">
                            <div class="barber-img">
                                <img src="https://images.unsplash.com/photo-1599566150163-29194dcaad36?auto=format&fit=crop&q=80&w=400" alt="الحلاق أحمد">
                            </div>
                            <h3 class="barber-name">المعلم أحمد</h3>
                            <div class="barber-title">خبير حلاقة ذقن</div>
                            <div class="barber-rating">
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star-half-alt star"></i>
                            </div>
                            <p>١٥ سنة خبرة في حلاقة الذقن والتشكيلات الدقيقة</p>
                        </div>
                    </div>
                    
                    <!-- Barber 2 -->
                    <div class="swiper-slide">
                        <div class="barber-card" data-barber="ياسر">
                            <div class="barber-img">
                                <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w-400" alt="الحلاق ياسر">
                            </div>
                            <h3 class="barber-name">المعلم ياسر</h3>
                            <div class="barber-title">مختص قصات شعر</div>
                            <div class="barber-rating">
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                            </div>
                            <p>محترف في أحدث صيحات قصات الشعر العالمية</p>
                        </div>
                    </div>
                    
                    <!-- Barber 3 -->
                    <div class="swiper-slide">
                        <div class="barber-card" data-barber="فهد">
                            <div class="barber-img">
                                <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?auto=format&fit=crop&q=80&w=400" alt="الحلاق فهد">
                            </div>
                            <h3 class="barber-name">المعلم فهد</h3>
                            <div class="barber-title">خبير عناية البشرة</div>
                            <div class="barber-rating">
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="fas fa-star star"></i>
                                <i class="far fa-star star"></i>
                            </div>
                            <p>متخصص في خدمات العناية بالبشرة والأقنعة العلاجية</p>
                        </div>
                    </div>
                </div>
                
                <div class="swiper-pagination"></div>
            </div>
        </div>
        
        <!-- Time Slots -->
        <h3 style="margin-top: 40px; margin-bottom: 20px; font-weight: 800;">اختر وقت الزيارة</h3>
        <div class="time-slots">
            <div class="time-slot" data-time="09:00">٩ صباحاً</div>
            <div class="time-slot" data-time="11:00">١١ صباحاً</div>
            <div class="time-slot" data-time="13:00">١ ظهراً</div>
            <div class="time-slot" data-time="15:00">٣ عصراً</div>
            <div class="time-slot" data-time="17:00">٥ مساءً</div>
            <div class="time-slot" data-time="19:00">٧ مساءً</div>
            <div class="time-slot" data-time="21:00">٩ مساءً</div>
        </div>
        
        <!-- Branch Selection -->
        <h3 style="margin-top: 40px; margin-bottom: 20px; font-weight: 800;">اختر الفرع</h3>
        <div class="time-slots">
            <div class="time-slot" data-branch="حي بدر">حي بدر</div>
            <div class="time-slot" data-branch="حي الشعلة">حي الشعلة</div>
            <div class="time-slot" data-branch="حي الفرسان">حي الفرسان</div>
        </div>
    </section>
    
    <!-- Booking Bar (Fixed at bottom) -->
    <div class="booking-bar" id="bookingBar">
        <div class="booking-details">
            <div class="booking-summary" id="bookingSummary">اختر خدمة للحجز</div>
            <div class="booking-price" id="bookingPrice">٠ ر.س</div>
        </div>
        <button class="confirm-booking" id="confirmBooking" onclick="showBookingModal()">تأكيد الحجز</button>
    </div>
    
    <!-- Footer -->
    <footer class="mobile-footer" id="branches">
        <div class="footer-section">
            <h3 class="footer-title">فروعنا</h3>
            
            <div class="branch-card">
                <div class="branch-name">فرع حي بدر</div>
                <p>شارع الخوارزمي، بجانب البنك الأهلي</p>
                <div class="branch-hours">
                    <i class="far fa-clock"></i>
                    <span>٩ صباحاً - ١١ مساءً</span>
                </div>
            </div>
            
            <div class="branch-card">
                <div class="branch-name">فرع حي الشعلة</div>
                <p>شارع عبدالرحمن بن عوف، مقابل سوق التميمي</p>
                <div class="branch-hours">
                    <i class="far fa-clock"></i>
                    <span>٩ صباحاً - ١١ مساءً</span>
                </div>
            </div>
            
            <div class="branch-card">
                <div class="branch-name">فرع حي الفرسان</div>
                <p>شارع ربيعة بنت خويلد، بجوار مركز الراية</p>
                <div class="branch-hours">
                    <i class="far fa-clock"></i>
                    <span>٩ صباحاً - ١١ مساءً</span>
                </div>
            </div>
        </div>
        
        <div class="footer-section" id="contact">
            <h3 class="footer-title">تواصل معنا</h3>
            <p style="margin-bottom: 20px; line-height: 1.6;">نحن هنا لخدمتك في أي وقت. لا تتردد في الاتصال بنا لمعرفة المزيد عن خدماتنا أو لحجز موعدك.</p>
            
            <a href="tel:0596160783" style="display: block; font-size: 1.5rem; font-weight: 900; color: var(--gold); margin-bottom: 25px; text-decoration: none;">
                <i class="fas fa-phone" style="margin-left: 10px;"></i>
                ٠٥٩٦١٦٠٧٨٣
            </a>
            
            <div class="social-icons">
                <a href="#" class="social-icon">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="#" class="social-icon">
                    <i class="fab fa-snapchat-ghost"></i>
                </a>
                <a href="#" class="social-icon">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="#" class="social-icon">
                    <i class="fab fa-tiktok"></i>
                </a>
            </div>
        </div>
        
        <div class="copyright">
            &copy; ٢٠٢٤ ركن الرجل للحلاقة والعناية. جميع الحقوق محفوظة.
        </div>
    </footer>
    
    <!-- Add to Home Screen Prompt -->
    <div class="add-to-home" id="addToHome">
        <div class="add-to-home-content">
            <div class="add-to-home-icon">
                <i class="fas fa-plus"></i>
            </div>
            <div class="add-to-home-text">
                <div class="add-to-home-title">أضف ركن الرجل إلى شاشتك الرئيسية</div>
                <div class="add-to-home-desc">احصل على تجربة تطبيق سريع ووصل مباشرة من شاشة هاتفك</div>
            </div>
            <button class="add-to-home-close" onclick="closeAddToHome()">✕</button>
        </div>
        <button class="add-to-home-btn" onclick="addToHomeScreen()">إضافة إلى الشاشة الرئيسية</button>
    </div>
    
    <!-- Booking Modal -->
    <div class="modal" id="bookingModal">
        <div class="modal-content">
            <div class="modal-icon">
                <i class="fas fa-check"></i>
            </div>
            <h3 class="modal-title">تم الحجز بنجاح!</h3>
            <p class="modal-message" id="modalMessage">شكراً لاختيارك ركن الرجل. سنتصل بك لتأكيد الموعد.</p>
            <button class="modal-btn" onclick="closeModal()">حسناً، أراك قريباً</button>
        </div>
    </div>
    
    <!-- JavaScript Libraries -->
    <script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
    
    <script>
        // Initialize Swiper for barbers slider
        const swiper = new Swiper('.swiper', {
            slidesPerView: 1.1,
            spaceBetween: 20,
            centeredSlides: false,
            loop: false,
            pagination: {
                el: '.swiper-pagination',
                clickable: true,
            },
            breakpoints: {
                640: {
                    slidesPerView: 2,
                },
                1024: {
                    slidesPerView: 3,
                },
            }
        });
        
        // DOM Elements
        const hamburger = document.getElementById('hamburger');
        const mobileMenu = document.getElementById('mobileMenu');
        const bookingBar = document.getElementById('bookingBar');
        const bookingSummary = document.getElementById('bookingSummary');
        const bookingPrice = document.getElementById('bookingPrice');
        const loader = document.getElementById('loader');
        
        // Booking state
        let bookingState = {
            service: null,
            price: 0,
            barber: null,
            time: null,
            branch: null
        };
        
        // Show loader on page load
        window.addEventListener('load', function() {
            setTimeout(() => {
                loader.classList.remove('active');
                // Show add to home prompt after 10 seconds
                setTimeout(showAddToHomePrompt, 10000);
            }, 1500);
        });
        
        // Mobile menu toggle
        hamburger.addEventListener('click', function() {
            this.classList.toggle('active');
            mobileMenu.classList.toggle('active');
        });
        
        // Close menu when clicking outside
        document.addEventListener('click', function(event) {
            if (!hamburger.contains(event.target) && !mobileMenu.contains(event.target)) {
                hamburger.classList.remove('active');
                mobileMenu.classList.remove('active');
            }
        });
        
        // Service tabs functionality
        const tabBtns = document.querySelectorAll('.tab-btn');
        const serviceCards = document.querySelectorAll('.service-card');
        
        tabBtns.forEach(btn => {
            btn.addEventListener('click', function() {
                // Update active tab
                tabBtns.forEach(b => b.classList.remove('active'));
                this.classList.add('active');
                
                // Filter services
                const category = this.getAttribute('data-tab');
                
                serviceCards.forEach(card => {
                    if (category === 'all' || card.getAttribute('data-category') === category) {
                        card.style.display = 'block';
                        setTimeout(() => {
                            card.style.opacity = '1';
                            card.style.transform = 'translateY(0)';
                        }, 10);
                    } else {
                        card.style.opacity = '0';
                        card.style.transform = 'translateY(20px)';
                        setTimeout(() => {
                            card.style.display = 'none';
                        }, 300);
                    }
                });
            });
        });
        
        // Book service button
        const bookServiceBtns = document.querySelectorAll('.book-service-btn');
        
        bookServiceBtns.forEach(btn => {
            btn.addEventListener('click', function() {
                const service = this.getAttribute('data-service');
                const price = this.getAttribute('data-price');
                
                bookingState.service = service;
                bookingState.price = price;
                
                // Update booking bar
                bookingSummary.textContent = service;
                bookingPrice.textContent = `${price} ر.س`;
                
                // Show booking bar
                bookingBar.classList.add('active');
                
                // Scroll to booking section
                scrollToSection('booking');
                
                // Highlight selected service card
                bookServiceBtns.forEach(b => {
                    b.parentElement.classList.remove('selected');
                });
                this.parentElement.classList.add('selected');
            });
        });
        
        // Select barber
        const barberCards = document.querySelectorAll('.barber-card');
        
        barberCards.forEach(card => {
            card.addEventListener('click', function() {
                barberCards.forEach(c => c.classList.remove('selected'));
                this.classList.add('selected');
                
                bookingState.barber = this.getAttribute('data-barber');
                updateBookingSummary();
            });
        });
        
        // Select time slot
        const timeSlots = document.querySelectorAll('.time-slot');
        
        timeSlots.forEach(slot => {
            slot.addEventListener('click', function() {
                // Check if it's a branch or time slot
                const time = this.getAttribute('data-time');
                const branch = this.getAttribute('data-branch');
                
                // Remove selection from all time slots
                timeSlots.forEach(s => s.classList.remove('selected'));
                
                // Add selection to clicked slot
                this.classList.add('selected');
                
                if (time) {
                    bookingState.time = time;
                }
                
                if (branch) {
                    bookingState.branch = branch;
                }
                
                updateBookingSummary();
            });
        });
        
        // Update booking summary
        function updateBookingSummary() {
            let summary = '';
            
            if (bookingState.service) {
                summary += bookingState.service;
            }
            
            if (bookingState.barber) {
                summary += ` مع ${bookingState.barber}`;
            }
            
            if (bookingState.time) {
                summary += ` الساعة ${bookingState.time}`;
            }
            
            if (bookingState.branch) {
                summary += ` في ${bookingState.branch}`;
            }
            
            if (summary) {
                bookingSummary.textContent = summary;
                bookingBar.classList.add('active');
            }
        }
        
        // Show booking modal
        function showBookingModal() {
            if (!bookingState.service) {
                alert('يرجى اختيار خدمة أولاً');
                return;
            }
            
            if (!bookingState.barber) {
                alert('يرجى اختيار حلاقك المفضل');
                return;
            }
            
            if (!bookingState.time) {
                alert('يرجى اختيار وقت الزيارة');
                return;
            }
            
            if (!bookingState.branch) {
                alert('يرجى اختيار الفرع');
                return;
            }
            
            const modalMessage = `شكراً لحجزك في ركن الرجل!<br><br>
            <strong>الخدمة:</strong> ${bookingState.service}<br>
            <strong>الحلاق:</strong> ${bookingState.barber}<br>
            <strong>الوقت:</strong> ${bookingState.time}<br>
            <strong>الفرع:</strong> ${bookingState.branch}<br>
            <strong>السعر:</strong> ${bookingState.price} ريال<br><br>
            سنتصل بك على الرقم <strong>٠٥٩٦١٦٠٧٨٣</strong> لتأكيد الموعد.`;
            
            document.getElementById('modalMessage').innerHTML = modalMessage;
            document.getElementById('bookingModal').classList.add('active');
            
            // In a real app, you would send this data to a server
            console.log('Booking details:', bookingState);
        }
        
        // Close modal
        function closeModal() {
            document.getElementById('bookingModal').classList.remove('active');
            
            // Reset booking state
            bookingState = {
                service: null,
                price: 0,
                barber: null,
                time: null,
                branch: null
            };
            
            // Reset UI
            bookingSummary.textContent = 'اختر خدمة للحجز';
            bookingPrice.textContent = '٠ ر.س';
            bookingBar.classList.remove('active');
            
            // Remove selections
            bookServiceBtns.forEach(b => b.parentElement.classList.remove('selected'));
            barberCards.forEach(c => c.classList.remove('selected'));
            timeSlots.forEach(s => s.classList.remove('selected'));
        }
        
        // Scroll to section
        function scrollToSection(sectionId) {
            const section = document.getElementById(sectionId);
            if (section) {
                section.scrollIntoView({ behavior: 'smooth' });
                
                // Close mobile menu if open
                hamburger.classList.remove('active');
                mobileMenu.classList.remove('active');
            }
        }
        
        // Add to home screen functionality
        let deferredPrompt;
        
        window.addEventListener('beforeinstallprompt', (e) => {
            // Prevent the mini-infobar from appearing on mobile
            e.preventDefault();
            // Stash the event so it can be triggered later
            deferredPrompt = e;
        });
        
        function showAddToHomePrompt() {
            if (deferredPrompt) {
                document.getElementById('addToHome').style.display = 'block';
            }
        }
        
        function closeAddToHome() {
            document.getElementById('addToHome').style.display = 'none';
        }
        
        function addToHomeScreen() {
            if (!deferredPrompt) return;
            
            // Show the install prompt
            deferredPrompt.prompt();
            
            // Wait for the user to respond to the prompt
            deferredPrompt.userChoice.then((choiceResult) => {
                if (choiceResult.outcome === 'accepted') {
                    console.log('User accepted the install prompt');
                } else {
                    console.log('User dismissed the install prompt');
                }
                deferredPrompt = null;
                closeAddToHome();
            });
        }
        
        // Touch-friendly enhancements
        document.addEventListener('touchstart', function() {}, {passive: true});
        
        // Prevent context menu on long press for buttons
        document.addEventListener('contextmenu', function(e) {
            if (e.target.tagName === 'BUTTON' || e.target.classList.contains('service-card')) {
                e.preventDefault();
            }
        }, false);
        
        // Handle back button on Android
        if (window.history && window.history.pushState) {
            window.history.pushState('forward', null, './');
            window.addEventListener('popstate', function() {
                // Close menus on back button press
                hamburger.classList.remove('active');
                mobileMenu.classList.remove('active');
                document.getElementById('bookingModal').classList.remove('active');
                document.getElementById('addToHome').style.display = 'none';
            });
        }
        
        // Service Worker Registration for PWA
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', function() {
                navigator.serviceWorker.register('/sw.js').then(function(registration) {
                    console.log('ServiceWorker registration successful with scope: ', registration.scope);
                }, function(err) {
                    console.log('ServiceWorker registration failed: ', err);
                });
            });
        }
        
        // Detect device type for optimizations
        const isMobile = /iPhone|iPad|iPod|Android/i.test(navigator.userAgent);
        if (isMobile) {
            document.body.classList.add('mobile-device');
        }
        
        // Initialize tooltips for better UX
        function initTooltips() {
            const elementsWithTooltip = document.querySelectorAll('[data-tooltip]');
            elementsWithTooltip.forEach(el => {
                el.addEventListener('touchstart', function() {
                    // Show custom tooltip on touch
                    const tooltipText = this.getAttribute('data-tooltip');
                    if (tooltipText) {
                        showTouchTooltip(this, tooltipText);
                    }
                }, {passive: true});
                
                el.addEventListener('touchend', function() {
                    // Hide tooltip
                    hideTouchTooltip();
                }, {passive: true});
            });
        }
        
        // Simple touch tooltip implementation
        function showTouchTooltip(element, text) {
            // Implementation for touch tooltips
        }
        
        function hideTouchTooltip() {
            // Hide tooltip
        }
        
        // Initialize when DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            initTooltips();
        });
    </script>
    
    <!-- Service Worker File (sw.js) would be a separate file -->
    <script>
        // Inline service worker registration code
        // In production, this should be in a separate sw.js file
    </script>
</body>
</html>
