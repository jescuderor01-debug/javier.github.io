<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechPlanet - Your Universe of Technological Solutions | IT Services & Cloud Solutions</title>
  <meta name="description" content="TechPlanet delivers cutting-edge IT solutions including cloud services, cybersecurity, AI automation, and custom development.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/remixicon@3.5.0/fonts/remixicon.css" rel="stylesheet">
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --orange: #f97316;
      --orange-dark: #ea580c;
      --orange-light: #fb923c;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Space Grotesk', sans-serif;
      background: #000;
      color: #fff;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 50;
      background: rgba(0,0,0,0.7);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(255,255,255,0.05);
      transition: all 0.3s;
    }
    .nav-inner {
      max-width: 1280px; margin: 0 auto;
      padding: 16px 24px;
      display: flex; align-items: center; justify-content: space-between;
    }
    .nav-logo {
      display: flex; align-items: center; gap: 12px;
      text-decoration: none; color: #fff;
    }
    .nav-logo-icon {
      width: 44px; height: 44px;
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      font-size: 22px;
    }
    .nav-logo span { font-size: 20px; font-weight: 700; letter-spacing: 0.1em; }
    .nav-links { display: flex; align-items: center; gap: 32px; }
    .nav-links a {
      color: #fff; text-decoration: none;
      font-size: 14px; font-weight: 500;
      position: relative; padding-bottom: 2px;
      transition: color 0.3s;
    }
    .nav-links a::after {
      content: ''; position: absolute; bottom: 0; left: 50%;
      width: 0; height: 2px; background: var(--orange);
      transition: all 0.3s;
    }
    .nav-links a:hover { color: var(--orange); }
    .nav-links a:hover::after { width: 100%; left: 0; }

    /* HERO */
    #home {
      min-height: 100vh;
      display: flex; align-items: center; justify-content: center;
      position: relative; overflow: hidden;
      background: #000;
    }
    .stars {
      position: absolute; inset: 0; pointer-events: none;
    }
    .star {
      position: absolute;
      width: 2px; height: 2px;
      background: #fff; border-radius: 50%;
      animation: pulse 3s ease infinite;
    }
    @keyframes pulse { 0%,100%{opacity:0.3} 50%{opacity:1} }

    .hero-content {
      position: relative; z-index: 10;
      text-align: center; padding: 24px;
      max-width: 900px;
    }
    .hero-content h1 {
      font-size: clamp(3rem, 8vw, 6rem);
      font-weight: 800; line-height: 1.05; margin-bottom: 24px;
    }
    .hero-content h1 .line1 {
      background: linear-gradient(135deg, #fff, #fde8d4, #fff);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
      display: block;
      filter: drop-shadow(0 0 30px rgba(249,115,22,0.4));
    }
    .hero-content h1 .line2 {
      background: linear-gradient(135deg, var(--orange-dark), var(--orange-light), var(--orange));
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      background-clip: text;
      display: block;
      filter: drop-shadow(0 0 40px rgba(249,115,22,0.7));
    }
    .hero-content p {
      font-size: 18px; color: #9ca3af; margin-bottom: 48px;
      max-width: 640px; margin-left: auto; margin-right: auto;
      line-height: 1.7;
    }
    .btn-primary {
      display: inline-flex; align-items: center; gap: 10px;
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      color: #fff; padding: 18px 40px; border-radius: 9999px;
      font-size: 16px; font-weight: 600; border: none; cursor: pointer;
      transition: all 0.3s; text-decoration: none;
    }
    .btn-primary:hover {
      transform: scale(1.05);
      box-shadow: 0 0 40px rgba(249,115,22,0.5);
    }
    .btn-primary i { font-size: 20px; transition: transform 0.3s; }
    .btn-primary:hover i { transform: translateX(4px); }

    .scroll-indicator {
      position: absolute; bottom: 40px; left: 50%;
      transform: translateX(-50%);
      animation: bounce 1.5s ease infinite;
      color: var(--orange); font-size: 28px;
    }
    @keyframes bounce { 0%,100%{transform:translateX(-50%) translateY(0)} 50%{transform:translateX(-50%) translateY(-8px)} }

    /* SECTIONS COMMON */
    section { padding: 80px 24px; }
    .section-label {
      display: inline-flex; align-items: center; gap: 8px;
      color: var(--orange); font-size: 12px; font-weight: 600;
      text-transform: uppercase; letter-spacing: 0.15em;
      margin-bottom: 16px;
    }
    .section-title {
      font-size: clamp(2.5rem, 5vw, 3.5rem);
      font-weight: 700; margin-bottom: 24px; line-height: 1.1;
    }
    .section-title .accent { color: var(--orange); }
    .container { max-width: 1280px; margin: 0 auto; }
    .text-center { text-align: center; }
    .section-subtitle {
      font-size: 18px; color: #6b7280;
      max-width: 640px; margin: 0 auto;
    }

    /* ABOUT */
    #about {
      background: #000;
      position: relative;
    }
    #about::before {
      content: ''; position: absolute; top: 80px; left: 40px;
      width: 256px; height: 256px; background: rgba(249,115,22,0.08);
      border-radius: 50%; filter: blur(100px);
    }
    #about::after {
      content: ''; position: absolute; bottom: 80px; right: 40px;
      width: 384px; height: 384px; background: rgba(234,88,12,0.06);
      border-radius: 50%; filter: blur(130px);
    }
    .about-grid {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 64px; align-items: center;
      position: relative; z-index: 1;
    }
    .about-img-wrap {
      position: relative; border-radius: 24px; overflow: hidden;
    }
    .about-img-wrap::before {
      content: ''; position: absolute; inset: -20px;
      background: linear-gradient(135deg, rgba(249,115,22,0.15), transparent);
      border-radius: 32px; filter: blur(20px); z-index: -1;
    }
    .about-img-wrap img {
      width: 100%; height: 480px; object-fit: cover;
      border-radius: 24px;
      box-shadow: 0 25px 60px rgba(249,115,22,0.15);
    }
    .about-text p {
      font-size: 17px; color: #9ca3af; line-height: 1.8; margin-bottom: 24px;
    }
    .stats-grid {
      display: grid; grid-template-columns: repeat(3,1fr);
      gap: 24px; padding: 32px 0; border-top: 1px solid #1f2937;
      margin-top: 8px;
    }
    .stat { text-align: center; }
    .stat-value { font-size: 40px; font-weight: 700; color: var(--orange); }
    .stat-label { font-size: 13px; color: #6b7280; margin-top: 4px; }
    .about-badges {
      display: flex; gap: 24px; flex-wrap: wrap; padding-top: 16px;
    }
    .badge {
      display: flex; align-items: center; gap: 8px;
      color: #d1d5db; font-size: 14px;
    }
    .badge i { color: var(--orange); font-size: 18px; }

    /* SERVICES */
    #services {
      background: #000;
    }
    .services-grid {
      display: grid; grid-template-columns: repeat(4,1fr);
      gap: 24px; margin-top: 64px;
    }
    .service-card {
      background: #000;
      border: 1px solid #1f2937; border-radius: 24px;
      padding: 32px; cursor: pointer;
      transition: all 0.3s; position: relative; overflow: hidden;
    }
    .service-card.featured {
      border-color: var(--orange);
      box-shadow: 0 0 40px rgba(249,115,22,0.15);
    }
    .featured-badge {
      position: absolute; top: 16px; right: 16px;
      background: var(--orange); color: #000;
      font-size: 11px; font-weight: 700;
      padding: 4px 12px; border-radius: 9999px;
    }
    .service-card:hover {
      transform: translateY(-6px) scale(1.01);
      border-color: rgba(249,115,22,0.4);
      box-shadow: 0 20px 60px rgba(249,115,22,0.1);
    }
    .service-icon {
      width: 60px; height: 60px;
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      border-radius: 16px; display: flex; align-items: center; justify-content: center;
      font-size: 26px; color: #fff; margin-bottom: 24px;
      box-shadow: 0 8px 24px rgba(249,115,22,0.3);
      transition: transform 0.3s;
    }
    .service-card:hover .service-icon { transform: scale(1.1); }
    .service-card h3 { font-size: 22px; font-weight: 700; margin-bottom: 12px; }
    .service-card p { color: #6b7280; font-size: 15px; line-height: 1.7; margin-bottom: 24px; }
    .service-features { list-style: none; margin-bottom: 24px; }
    .service-features li {
      display: flex; align-items: center; gap: 8px;
      font-size: 13px; color: #4b5563; margin-bottom: 8px;
    }
    .service-features li i { color: var(--orange); font-size: 16px; }
    .service-link {
      display: flex; align-items: center; gap: 6px;
      color: var(--orange); font-size: 14px; font-weight: 600;
      padding-top: 20px; border-top: 1px solid #1f2937;
      transition: gap 0.3s;
    }
    .service-card:hover .service-link { gap: 10px; }

    /* PRICING */
    #prices { background: #000; position: relative; overflow: hidden; }
    #prices::before {
      content: ''; position: absolute; top: 0; left: 25%;
      width: 384px; height: 384px; background: rgba(249,115,22,0.06);
      border-radius: 50%; filter: blur(120px);
    }
    .pricing-grid {
      display: grid; grid-template-columns: repeat(2,1fr);
      gap: 20px; max-width: 720px; margin: 48px auto 0;
      position: relative; z-index: 1;
    }
    .pricing-card {
      background: #000;
      border: 1px solid #1f2937; border-radius: 20px;
      padding: 24px; cursor: pointer; transition: all 0.3s; position: relative;
    }
    .pricing-card.popular {
      border: 2px solid var(--orange);
      box-shadow: 0 0 60px rgba(249,115,22,0.2);
    }
    .pricing-card:hover { transform: scale(1.02); }
    .popular-badge {
      position: absolute; top: -14px; left: 50%; transform: translateX(-50%);
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      color: #fff; font-size: 12px; font-weight: 700;
      padding: 5px 20px; border-radius: 9999px; white-space: nowrap;
    }
    .pricing-card h3 { font-size: 20px; font-weight: 700; margin-bottom: 6px; }
    .pricing-card .plan-desc {
      font-size: 12px; color: #6b7280; margin-bottom: 16px; min-height: 40px;
    }
    .price {
      font-size: 40px; font-weight: 700; margin-bottom: 20px;
      display: flex; align-items: flex-start; gap: 4px;
    }
    .price .currency { font-size: 18px; color: #6b7280; margin-top: 6px; }
    .price .period { font-size: 14px; color: #6b7280; align-self: flex-end; margin-bottom: 4px; }
    .price.custom-price { color: var(--orange); align-items: center; }
    .pricing-features { list-style: none; margin-bottom: 24px; }
    .pricing-features li {
      display: flex; align-items: flex-start; gap: 10px;
      font-size: 13px; color: #d1d5db; margin-bottom: 10px;
    }
    .pricing-features li i { color: var(--orange); font-size: 17px; flex-shrink: 0; margin-top: 1px; }
    .btn-plan {
      width: 100%; padding: 13px; border-radius: 9999px;
      font-size: 14px; font-weight: 600; border: none; cursor: pointer;
      transition: all 0.3s;
    }
    .btn-plan.secondary {
      background: #1f2937; color: #fff;
    }
    .btn-plan.secondary:hover { background: #374151; }
    .btn-plan.primary-btn {
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      color: #fff;
    }
    .btn-plan.primary-btn:hover {
      box-shadow: 0 0 30px rgba(249,115,22,0.5);
      transform: scale(1.03);
    }
    .pricing-footer {
      margin-top: 40px; text-align: center;
    }
    .pricing-footer p { color: #6b7280; margin-bottom: 12px; font-size: 14px; }
    .pricing-perks {
      display: flex; justify-content: center; gap: 32px; flex-wrap: wrap;
    }
    .pricing-perks span {
      display: flex; align-items: center; gap: 8px;
      font-size: 13px; color: #4b5563;
    }
    .pricing-perks span i { color: var(--orange); }

    /* FAQ */
    #faq { background: #000; }
    .faq-list { max-width: 800px; margin: 64px auto 0; }
    .faq-item {
      background: #000;
      border: 1px solid #1f2937; border-radius: 16px;
      overflow: hidden; margin-bottom: 12px;
      transition: border-color 0.3s;
    }
    .faq-item:hover { border-color: rgba(249,115,22,0.4); }
    .faq-btn {
      width: 100%; padding: 24px 32px;
      display: flex; align-items: center; justify-content: space-between;
      background: none; border: none; color: #fff; cursor: pointer;
      text-align: left; gap: 16px;
    }
    .faq-btn span {
      font-size: 16px; font-weight: 600; transition: color 0.3s;
    }
    .faq-btn:hover span { color: var(--orange); }
    .faq-btn i {
      font-size: 22px; color: var(--orange); flex-shrink: 0;
      transition: transform 0.3s;
    }
    .faq-btn.open i { transform: rotate(180deg); }
    .faq-answer {
      max-height: 0; overflow: hidden; transition: max-height 0.4s ease;
    }
    .faq-answer.open { max-height: 200px; }
    .faq-answer p {
      padding: 0 32px 24px; color: #6b7280; line-height: 1.8; font-size: 15px;
    }
    .faq-cta {
      max-width: 800px; margin: 64px auto 0;
      background: #000;
      border: 1px solid rgba(249,115,22,0.25);
      border-radius: 20px; padding: 40px; text-align: center;
    }
    .faq-cta h3 { font-size: 24px; font-weight: 700; margin-bottom: 12px; }
    .faq-cta p { color: #6b7280; margin-bottom: 24px; }

    /* CONTACT */
    #contact { background: #000; position: relative; overflow: hidden; }
    #contact::before {
      content: ''; position: absolute; top: 0; right: 0;
      width: 500px; height: 500px; background: rgba(249,115,22,0.06);
      border-radius: 50%; filter: blur(120px);
    }
    .contact-grid {
      display: flex; justify-content: center;
      max-width: 640px; margin: 48px auto 0;
      position: relative; z-index: 1;
    }
    .contact-info h3 { font-size: 24px; font-weight: 700; margin-bottom: 12px; }
    .contact-info > p { color: #6b7280; line-height: 1.7; margin-bottom: 24px; font-size: 14px; }
    .contact-items { display: flex; flex-direction: column; gap: 16px; }
    .contact-item {
      display: flex; align-items: flex-start; gap: 14px;
    }
    .contact-item-icon {
      width: 42px; height: 42px; flex-shrink: 0;
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      border-radius: 12px; display: flex; align-items: center; justify-content: center;
      font-size: 19px; color: #fff;
    }
    .contact-item h4 { font-size: 13px; font-weight: 600; margin-bottom: 3px; }
    .contact-item p { font-size: 12px; color: #6b7280; line-height: 1.5; }
    .social-row {
      margin-top: 20px; padding-top: 20px;
      border-top: 1px solid #1f2937;
    }
    .social-row h4 { font-size: 13px; font-weight: 600; margin-bottom: 12px; }
    .socials { display: flex; gap: 10px; }
    .social-link {
      width: 42px; height: 42px;
      background: #111; border-radius: 12px;
      display: flex; align-items: center; justify-content: center;
      font-size: 16px; color: #fff; text-decoration: none;
      transition: all 0.3s;
    }
    .social-link:hover {
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      transform: scale(1.1);
    }
    .contact-form-wrap {
      background: #000;
      border: 1px solid #1f2937; border-radius: 20px; padding: 24px;
    }
    .form-group { margin-bottom: 14px; }
    .form-group label {
      display: block; font-size: 12px; font-weight: 600; margin-bottom: 6px;
    }
    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%; background: #000;
      border: 1px solid #1f2937; border-radius: 10px;
      padding: 10px 14px; color: #fff; font-family: inherit;
      font-size: 13px; transition: border-color 0.3s; outline: none;
    }
    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      border-color: var(--orange);
    }
    .form-group textarea { resize: none; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
    .char-count { font-size: 11px; color: #4b5563; text-align: right; margin-top: 3px; }
    .btn-submit {
      width: 100%; padding: 13px;
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      color: #fff; border: none; border-radius: 12px;
      font-family: inherit; font-size: 14px; font-weight: 600;
      cursor: pointer; transition: all 0.3s;
    }
    .btn-submit:hover {
      box-shadow: 0 0 30px rgba(249,115,22,0.4);
      transform: scale(1.02);
    }

    /* FOOTER */
    footer {
      background: #000;
      padding: 80px 24px 32px;
    }
    .footer-grid {
      display: grid; grid-template-columns: 2fr 1fr 1fr 2fr;
      gap: 48px; margin-bottom: 64px;
    }
    .footer-brand .logo-row {
      display: flex; align-items: center; gap: 12px; margin-bottom: 16px;
    }
    .footer-brand .logo-row span { font-size: 18px; font-weight: 700; }
    .footer-brand p { font-size: 13px; color: #6b7280; line-height: 1.7; }
    .footer-col h4 {
      font-size: 11px; font-weight: 700; text-transform: uppercase;
      letter-spacing: 0.12em; color: #9ca3af; margin-bottom: 16px;
    }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 8px; }
    .footer-col ul li a {
      color: #6b7280; text-decoration: none; font-size: 13px;
      transition: color 0.3s;
    }
    .footer-col ul li a:hover { color: var(--orange); }
    .newsletter-form {
      display: flex; gap: 8px; margin-bottom: 8px;
    }
    .newsletter-form input {
      flex: 1; background: rgba(0,0,0,0.5);
      border: 1px solid #1f2937; border-radius: 10px;
      padding: 10px 14px; color: #fff; font-family: inherit;
      font-size: 13px; outline: none; transition: border-color 0.3s;
    }
    .newsletter-form input:focus { border-color: var(--orange); }
    .newsletter-form button {
      background: linear-gradient(135deg, var(--orange-dark), var(--orange));
      border: none; border-radius: 10px; padding: 10px 16px;
      color: #fff; cursor: pointer; font-size: 16px; transition: all 0.3s;
    }
    .newsletter-form button:hover {
      box-shadow: 0 0 20px rgba(249,115,22,0.4);
    }
    .newsletter-hint { font-size: 11px; color: #4b5563; }
    .footer-bottom {
      border-top: 1px solid #1f2937; padding-top: 32px;
      display: flex; justify-content: space-between; align-items: center;
      flex-wrap: wrap; gap: 16px;
    }
    .footer-bottom p { font-size: 13px; color: #4b5563; }
    .footer-bottom-links { display: flex; align-items: center; gap: 24px; flex-wrap: wrap; }
    .footer-bottom-links a {
      color: #4b5563; text-decoration: none; font-size: 13px; transition: color 0.3s;
    }
    .footer-bottom-links a:hover { color: var(--orange); }
    .footer-socials { display: flex; gap: 8px; }
    .footer-social {
      width: 32px; height: 32px; background: #111;
      border-radius: 8px; display: flex; align-items: center;
      justify-content: center; font-size: 14px; color: #fff;
      text-decoration: none; transition: background 0.3s;
    }
    .footer-social:hover { background: var(--orange); }

    /* RESPONSIVE */
    @media (max-width: 900px) {
      .about-grid, .contact-grid { grid-template-columns: 1fr; }
      .services-grid { grid-template-columns: 1fr 1fr; }
      .pricing-grid { grid-template-columns: 1fr; max-width: 420px; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
      .nav-links { display: none; }
    }
    @media (max-width: 600px) {
      .services-grid { grid-template-columns: 1fr; }
      .footer-grid { grid-template-columns: 1fr; }
      .form-row { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-inner">
    <a href="#home" class="nav-logo">
      <div class="nav-logo-icon"><i class="ri-planet-line"></i></div>
      <span>TECHPLANET</span>
    </a>
    <div class="nav-links">
      <a href="#home">Home</a>
      <a href="#about">About Us</a>
      <a href="#services">Services</a>
      <a href="#prices">Prices</a>
      <a href="#faq">FAQ</a>
      <a href="#contact">Contact</a>
    </div>
  </div>
</nav>

<!-- HERO -->
<section id="home">
  <div class="stars" id="stars"></div>
  <div class="hero-content">
    <h1>
      <span class="line1">Your universe of</span>
      <span class="line2">technological solutions</span>
    </h1>
    <p>Navigate through the cosmos of innovation with TechPlanet. We deliver cutting-edge IT solutions that propel your business into the future.</p>
    <a href="#services" class="btn-primary">
      Explore Our Universe <i class="ri-rocket-2-line"></i>
    </a>
  </div>
  <div class="scroll-indicator"><i class="ri-arrow-down-line"></i></div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="text-center">
      <div class="section-label"><i class="ri-planet-line"></i> About TechPlanet</div>
      <h2 class="section-title">Navigating the <span class="accent">Digital Galaxy</span></h2>
    </div>
    <div class="about-grid" style="margin-top:64px">
      <div class="about-img-wrap">
        <img src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?w=800&q=80" alt="TechPlanet Team">
      </div>
      <div class="about-text">
        <p>At TechPlanet, we are pioneers in the digital universe, charting new territories in technology and innovation. Since our inception, we have been dedicated to transforming businesses through cutting-edge IT solutions that transcend conventional boundaries.</p>
        <p>Our constellation of experts brings together decades of experience in cloud computing, artificial intelligence, cybersecurity, and digital transformation. We believe that every business deserves to orbit at the forefront of technological advancement.</p>
        <div class="stats-grid">
          <div class="stat"><div class="stat-value">500+</div><div class="stat-label">Projects Launched</div></div>
          <div class="stat"><div class="stat-value">98%</div><div class="stat-label">Client Satisfaction</div></div>
          <div class="stat"><div class="stat-value">15+</div><div class="stat-label">Years Experience</div></div>
        </div>
        <div class="about-badges">
          <div class="badge"><i class="ri-check-line"></i> Innovation-Driven</div>
          <div class="badge"><i class="ri-check-line"></i> Client-Focused</div>
          <div class="badge"><i class="ri-check-line"></i> Results-Oriented</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="container">
    <div class="text-center">
      <div class="section-label"><i class="ri-star-line"></i> Our Services</div>
      <h2 class="section-title">Our Technological <span class="accent">Constellation</span></h2>
      <p class="section-subtitle">Comprehensive IT solutions designed to propel your business into the future</p>
    </div>
    <div class="services-grid">

      <div class="service-card featured">
        <div class="featured-badge">Featured</div>
        <div class="service-icon"><i class="ri-shield-check-line"></i></div>
        <h3>Cybersecurity</h3>
        <p>Protect your digital assets with enterprise-grade security solutions. Our comprehensive approach ensures your data remains safe in the vast digital cosmos.</p>
        <ul class="service-features">
          <li><i class="ri-checkbox-circle-line"></i> Threat Detection</li>
          <li><i class="ri-checkbox-circle-line"></i> Security Audits</li>
          <li><i class="ri-checkbox-circle-line"></i> Compliance</li>
          <li><i class="ri-checkbox-circle-line"></i> Incident Response</li>
        </ul>
        <div class="service-link">Learn More <i class="ri-arrow-right-line"></i></div>
      </div>

      <div class="service-card">
        <div class="service-icon"><i class="ri-robot-2-line"></i></div>
        <h3>AI & Automation</h3>
        <p>Harness the power of artificial intelligence to automate processes and gain insights. Transform data into actionable intelligence.</p>
        <ul class="service-features">
          <li><i class="ri-checkbox-circle-line"></i> Machine Learning</li>
          <li><i class="ri-checkbox-circle-line"></i> Process Automation</li>
          <li><i class="ri-checkbox-circle-line"></i> Predictive Analytics</li>
          <li><i class="ri-checkbox-circle-line"></i> AI Integration</li>
        </ul>
        <div class="service-link">Learn More <i class="ri-arrow-right-line"></i></div>
      </div>

      <div class="service-card">
        <div class="service-icon"><i class="ri-code-s-slash-line"></i></div>
        <h3>Custom Development</h3>
        <p>Build bespoke software solutions tailored to your unique business needs. From web applications to enterprise systems.</p>
        <ul class="service-features">
          <li><i class="ri-checkbox-circle-line"></i> Web Development</li>
          <li><i class="ri-checkbox-circle-line"></i> Mobile Apps</li>
          <li><i class="ri-checkbox-circle-line"></i> API Integration</li>
          <li><i class="ri-checkbox-circle-line"></i> Legacy Modernization</li>
        </ul>
        <div class="service-link">Learn More <i class="ri-arrow-right-line"></i></div>
      </div>

      <div class="service-card">
        <div class="service-icon"><i class="ri-customer-service-2-line"></i></div>
        <h3>IT Consulting</h3>
        <p>Navigate your digital transformation journey with expert guidance. Strategic planning and implementation for sustainable growth.</p>
        <ul class="service-features">
          <li><i class="ri-checkbox-circle-line"></i> Digital Strategy</li>
          <li><i class="ri-checkbox-circle-line"></i> Tech Assessment</li>
          <li><i class="ri-checkbox-circle-line"></i> Roadmap Planning</li>
          <li><i class="ri-checkbox-circle-line"></i> 24/7 Support</li>
        </ul>
        <div class="service-link">Learn More <i class="ri-arrow-right-line"></i></div>
      </div>

    </div>
  </div>
</section>

<!-- PRICING -->
<section id="prices">
  <div class="container">
    <div class="text-center">
      <div class="section-label"><i class="ri-price-tag-3-line"></i> Pricing Plans</div>
      <h2 class="section-title">Choose Your <span class="accent">Orbit</span></h2>
      <p class="section-subtitle">Flexible pricing plans designed to fit businesses of all sizes</p>
    </div>
    <div class="pricing-grid">

      <div class="pricing-card">
        <h3>Starter</h3>
        <p class="plan-desc">Perfect for small businesses taking their first steps into the digital universe</p>
        <div class="price"><span class="currency">$</span>999<span class="period">/month</span></div>
        <ul class="pricing-features">
          <li><i class="ri-checkbox-circle-fill"></i> Cloud Infrastructure Setup</li>
          <li><i class="ri-checkbox-circle-fill"></i> Basic Security Package</li>
          <li><i class="ri-checkbox-circle-fill"></i> Email Support</li>
          <li><i class="ri-checkbox-circle-fill"></i> 10 Hours Consultation</li>
          <li><i class="ri-checkbox-circle-fill"></i> Monthly Reports</li>
          <li><i class="ri-checkbox-circle-fill"></i> Standard SLA</li>
        </ul>
        <button class="btn-plan secondary">Get Started</button>
      </div>

      <div class="pricing-card popular">
        <div class="popular-badge">Most Popular</div>
        <h3>Professional</h3>
        <p class="plan-desc">Ideal for growing companies ready to scale their technological capabilities</p>
        <div class="price"><span class="currency">$</span>2,499<span class="period">/month</span></div>
        <ul class="pricing-features">
          <li><i class="ri-checkbox-circle-fill"></i> Advanced Cloud Solutions</li>
          <li><i class="ri-checkbox-circle-fill"></i> Enhanced Cybersecurity</li>
          <li><i class="ri-checkbox-circle-fill"></i> Priority Support 24/7</li>
          <li><i class="ri-checkbox-circle-fill"></i> 40 Hours Consultation</li>
          <li><i class="ri-checkbox-circle-fill"></i> Custom Development</li>
          <li><i class="ri-checkbox-circle-fill"></i> AI Integration</li>
          <li><i class="ri-checkbox-circle-fill"></i> Weekly Reports</li>
          <li><i class="ri-checkbox-circle-fill"></i> Premium SLA</li>
        </ul>
        <button class="btn-plan primary-btn">Get Started</button>
      </div>



    </div>
    <div class="pricing-footer">
      <p>All plans include a 30-day money-back guarantee</p>
      <div class="pricing-perks">
        <span><i class="ri-shield-check-line"></i> Secure Payment</span>
        <span><i class="ri-customer-service-2-line"></i> 24/7 Support</span>
        <span><i class="ri-refresh-line"></i> Cancel Anytime</span>
      </div>
    </div>
  </div>
</section>

<!-- FAQ -->
<section id="faq">
  <div class="container">
    <div class="text-center">
      <div class="section-label"><i class="ri-question-line"></i> FAQ</div>
      <h2 class="section-title">Frequently Asked <span class="accent">Questions</span></h2>
      <p class="section-subtitle">Everything you need to know about our services</p>
    </div>
    <div class="faq-list">

      <div class="faq-item">
        <button class="faq-btn open" onclick="toggleFaq(this)">
          <span>What services does TechPlanet offer?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer open">
          <p>TechPlanet offers a comprehensive range of IT services including cloud solutions, cybersecurity, AI and automation, custom software development, data analytics, and IT consulting. We tailor our services to meet the unique needs of each client, ensuring optimal results for businesses of all sizes.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>How long does a typical project take?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>Project timelines vary depending on scope and complexity. A basic cloud migration might take 2-4 weeks, while custom software development can range from 2-6 months. During our initial consultation, we provide detailed timelines and milestones specific to your project requirements.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>Do you provide ongoing support after project completion?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>Absolutely! We offer comprehensive post-launch support and maintenance packages. Our team provides 24/7 monitoring, regular updates, security patches, and technical assistance to ensure your systems run smoothly. Support levels vary by plan, from basic email support to dedicated account management.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>What industries do you specialize in?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>We have extensive experience across multiple industries including finance, healthcare, e-commerce, manufacturing, and professional services. Our diverse team brings specialized knowledge to each sector, ensuring compliance with industry standards and best practices.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>How do you ensure data security and compliance?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>Security is our top priority. We implement enterprise-grade encryption, multi-factor authentication, regular security audits, and compliance with standards like GDPR, HIPAA, and SOC 2. Our cybersecurity team continuously monitors for threats and maintains the highest security protocols.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>Can you work with our existing technology stack?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>Yes! We specialize in integrating with existing systems and technologies. Whether you use AWS, Azure, legacy systems, or custom solutions, our team has the expertise to seamlessly integrate new technologies while maintaining your current infrastructure.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>What is your pricing model?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>We offer flexible pricing models including monthly subscriptions, project-based pricing, and custom enterprise agreements. Our transparent pricing ensures no hidden costs, and we work with you to find a solution that fits your budget while delivering maximum value.</p>
        </div>
      </div>

      <div class="faq-item">
        <button class="faq-btn" onclick="toggleFaq(this)">
          <span>How do I get started with TechPlanet?</span>
          <i class="ri-arrow-down-s-line"></i>
        </button>
        <div class="faq-answer">
          <p>Getting started is easy! Simply contact us through our website, schedule a free consultation, and our team will assess your needs. We'll provide a detailed proposal with timelines, costs, and expected outcomes. From there, we can begin your digital transformation journey.</p>
        </div>
      </div>

      <div class="faq-cta">
        <h3>Still have questions?</h3>
        <p>Our team is here to help. Reach out and we'll get back to you as soon as possible.</p>
        <a href="#contact" class="btn-primary" style="display:inline-flex">Contact Us</a>
      </div>

    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="text-center">
      <div class="section-label"><i class="ri-mail-line"></i> Get In Touch</div>
      <h2 class="section-title">Start Your <span class="accent">Journey</span></h2>
      <p class="section-subtitle">Ready to transform your business? Let's discuss how we can help you reach new heights</p>
    </div>
    <div class="contact-grid">
      <div class="contact-form-wrap" style="width:100%">
        <form id="contact-form">
          <div class="form-group">
            <label>Full Name *</label>
            <input type="text" name="name" placeholder="John Doe" required>
          </div>
          <div class="form-group">
            <label>Email Address *</label>
            <input type="email" name="email" placeholder="john@company.com" required>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Company</label>
              <input type="text" name="company" placeholder="Company Inc.">
            </div>
            <div class="form-group">
              <label>Phone</label>
              <input type="tel" name="phone" placeholder="+1 (555) 000-0000">
            </div>
          </div>
          <div class="form-group">
            <label>Service Interested In</label>
            <select name="service">
              <option value="">Select a service</option>
              <option value="cloud">Cloud Solutions</option>
              <option value="security">Cybersecurity</option>
              <option value="ai">AI & Automation</option>
              <option value="development">Custom Development</option>
              <option value="analytics">Data Analytics</option>
              <option value="consulting">IT Consulting</option>
            </select>
          </div>
          <div class="form-group">
            <label>Message *</label>
            <textarea name="message" rows="4" maxlength="500" placeholder="Tell us about your project..." id="msg" oninput="document.getElementById('charCount').textContent=this.value.length" required></textarea>
            <div class="char-count"><span id="charCount">0</span>/500</div>
          </div>
          <button type="submit" class="btn-submit">Send Message</button>
        </form>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <div class="logo-row">
          <div class="nav-logo-icon" style="width:36px;height:36px;font-size:18px;border-radius:10px"><i class="ri-planet-line"></i></div>
          <span>TECHPLANET</span>
        </div>
        <p>Your universe of technological solutions. Pioneering innovation in the digital cosmos since 2009.<br><br>Transforming businesses through cutting-edge technology and strategic IT solutions.</p>
      </div>
      <div class="footer-col">
        <h4>Solutions</h4>
        <ul>
          <li><a href="#services">Cloud Services</a></li>
          <li><a href="#services">Cybersecurity</a></li>
          <li><a href="#services">AI Integration</a></li>
          <li><a href="#services">Custom Development</a></li>
          <li><a href="#services">Data Analytics</a></li>
          <li><a href="#services">IT Consulting</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Company</h4>
        <ul>
          <li><a href="#about">About Us</a></li>
          <li><a href="#services">Our Services</a></li>
          <li><a href="#prices">Pricing</a></li>
          <li><a href="#faq">FAQ</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Newsletter</h4>
        <p style="font-size:13px;color:#6b7280;margin-bottom:12px">Subscribe to our cosmic updates and stay ahead in the tech universe</p>
        <div class="newsletter-form">
          <input type="email" placeholder="Enter your email">
          <button type="button"><i class="ri-arrow-right-line"></i></button>
        </div>
        <p class="newsletter-hint">Join 5,000+ subscribers</p>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2026 TechPlanet. All rights reserved.</p>
      <div class="footer-bottom-links">
        <a href="#">Privacy Policy</a>
        <a href="#">Terms of Service</a>
      </div>
      <div class="footer-socials">
        <a href="#" class="footer-social"><i class="ri-linkedin-fill"></i></a>
        <a href="#" class="footer-social"><i class="ri-twitter-x-fill"></i></a>
        <a href="#" class="footer-social"><i class="ri-github-fill"></i></a>
        <a href="#" class="footer-social"><i class="ri-facebook-fill"></i></a>
      </div>
    </div>
  </div>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
  // Stars
  const starsContainer = document.getElementById('stars');
  for (let i = 0; i < 80; i++) {
    const star = document.createElement('div');
    star.className = 'star';
    star.style.cssText = `
      top: ${Math.random() * 100}%;
      left: ${Math.random() * 100}%;
      animation-delay: ${Math.random() * 3}s;
      opacity: ${0.3 + Math.random() * 0.7};
    `;
    starsContainer.appendChild(star);
  }

  // FAQ
  function toggleFaq(btn) {
    const answer = btn.nextElementSibling;
    const isOpen = btn.classList.contains('open');
    // Close all
    document.querySelectorAll('.faq-btn.open').forEach(b => {
      b.classList.remove('open');
      b.nextElementSibling.classList.remove('open');
    });
    if (!isOpen) {
      btn.classList.add('open');
      answer.classList.add('open');
    }
  }

  // Nav scroll effect
  window.addEventListener('scroll', () => {
    const nav = document.querySelector('nav');
    nav.style.background = window.scrollY > 50
      ? 'rgba(0,0,0,0.95)'
      : 'rgba(0,0,0,0.7)';
  });

  // Form submit
  document.getElementById('contact-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const btn = this.querySele
