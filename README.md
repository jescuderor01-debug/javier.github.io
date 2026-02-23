
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TechPlanet — IT Solutions</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #030712;
    --surface: #0d1117;
    --border: rgba(0,255,200,0.12);
    --accent: #00ffc8;
    --accent2: #0099ff;
    --muted: #4a5568;
    --text: #e2e8f0;
    --text-dim: #718096;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── CANVAS STARS ── */
  #starfield {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.2rem 6vw;
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
    background: rgba(3,7,18,0.7);
  }

  .logo {
    font-family: 'Orbitron', monospace;
    font-weight: 900;
    font-size: 1.25rem;
    letter-spacing: 0.05em;
    color: #fff;
  }
  .logo span { color: var(--accent); }

  nav ul {
    list-style: none;
    display: flex;
    gap: 2.5rem;
  }

  nav a {
    text-decoration: none;
    color: var(--text-dim);
    font-size: 0.9rem;
    font-weight: 500;
    letter-spacing: 0.04em;
    transition: color 0.25s;
  }
  nav a:hover { color: var(--accent); }

  .nav-cta {
    background: transparent;
    border: 1px solid var(--accent);
    color: var(--accent) !important;
    padding: 0.5rem 1.25rem;
    border-radius: 4px;
    transition: background 0.25s, color 0.25s !important;
  }
  .nav-cta:hover {
    background: var(--accent) !important;
    color: var(--bg) !important;
  }

  /* ── HERO ── */
  #hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 8rem 2rem 4rem;
    z-index: 1;
  }

  .hero-content { max-width: 800px; }

  .hero-badge {
    display: inline-block;
    font-family: 'Orbitron', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    color: var(--accent);
    border: 1px solid var(--border);
    padding: 0.35rem 1rem;
    border-radius: 100px;
    margin-bottom: 2rem;
    animation: fadeUp 0.8s ease both;
  }

  h1 {
    font-family: 'Orbitron', monospace;
    font-weight: 900;
    font-size: clamp(2.5rem, 8vw, 5rem);
    line-height: 1.05;
    letter-spacing: -0.02em;
    color: #fff;
    animation: fadeUp 0.8s 0.15s ease both;
  }
  h1 em {
    font-style: normal;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    margin-top: 1.5rem;
    font-size: 1.1rem;
    color: var(--text-dim);
    font-weight: 300;
    line-height: 1.7;
    max-width: 560px;
    margin-left: auto;
    margin-right: auto;
    animation: fadeUp 0.8s 0.3s ease both;
  }

  .hero-btns {
    margin-top: 2.5rem;
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
    animation: fadeUp 0.8s 0.45s ease both;
  }

  .btn-primary {
    display: inline-block;
    background: var(--accent);
    color: var(--bg);
    font-family: 'Orbitron', monospace;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    padding: 0.9rem 2rem;
    border-radius: 4px;
    text-decoration: none;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 0 24px rgba(0,255,200,0.3);
  }
  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 0 40px rgba(0,255,200,0.5);
  }

  .btn-ghost {
    display: inline-block;
    border: 1px solid var(--border);
    color: var(--text);
    font-size: 0.9rem;
    padding: 0.9rem 2rem;
    border-radius: 4px;
    text-decoration: none;
    transition: border-color 0.2s, color 0.2s;
  }
  .btn-ghost:hover { border-color: var(--accent2); color: var(--accent2); }

  /* planet */
  .planet-wrap {
    position: absolute;
    bottom: -15vw;
    left: 50%;
    transform: translateX(-50%);
    width: 60vw;
    max-width: 700px;
    aspect-ratio: 1;
    border-radius: 50%;
    background: radial-gradient(circle at 35% 35%, #1a3a5c, #030712 70%);
    border: 1px solid rgba(0,153,255,0.15);
    box-shadow: 0 0 80px rgba(0,153,255,0.1), inset 0 0 60px rgba(0,255,200,0.04);
    overflow: hidden;
    z-index: -1;
    animation: planetSpin 60s linear infinite;
  }
  .planet-ring {
    position: absolute;
    inset: -10%;
    border-radius: 50%;
    border: 2px solid rgba(0,255,200,0.07);
    transform: rotateX(75deg);
  }
  .planet-glow {
    position: absolute;
    top: 10%; left: 15%;
    width: 30%; height: 20%;
    border-radius: 50%;
    background: rgba(0,153,255,0.2);
    filter: blur(30px);
  }

  @keyframes planetSpin {
    from { transform: translateX(-50%) rotate(0deg); }
    to { transform: translateX(-50%) rotate(360deg); }
  }

  /* ── STATS ── */
  #stats {
    position: relative;
    z-index: 1;
    padding: 6rem 6vw;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 2rem;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    background: rgba(13,17,23,0.6);
    backdrop-filter: blur(8px);
  }

  .stat { text-align: center; }
  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 2.5rem;
    font-weight: 900;
    color: var(--accent);
  }
  .stat-label {
    font-size: 0.85rem;
    color: var(--text-dim);
    letter-spacing: 0.06em;
    margin-top: 0.25rem;
    text-transform: uppercase;
  }

  /* ── SECTIONS ── */
  section {
    position: relative;
    z-index: 1;
    padding: 6rem 6vw;
  }

  .section-tag {
    font-family: 'Orbitron', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.25em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 0.75rem;
  }

  .section-title {
    font-family: 'Orbitron', monospace;
    font-size: clamp(1.6rem, 4vw, 2.5rem);
    font-weight: 700;
    color: #fff;
    line-height: 1.2;
    max-width: 600px;
  }

  .section-desc {
    margin-top: 1rem;
    color: var(--text-dim);
    font-weight: 300;
    line-height: 1.8;
    max-width: 520px;
  }

  /* ── SERVICES ── */
  .services-grid {
    margin-top: 3.5rem;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.5px;
    border: 1.5px solid var(--border);
    border-radius: 8px;
    overflow: hidden;
  }

  .service-card {
    padding: 2.5rem;
    background: var(--surface);
    border: none;
    transition: background 0.3s;
    cursor: default;
  }
  .service-card:hover { background: rgba(0,255,200,0.04); }

  .svc-icon {
    width: 48px; height: 48px;
    border-radius: 10px;
    background: linear-gradient(135deg, rgba(0,255,200,0.12), rgba(0,153,255,0.08));
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    margin-bottom: 1.25rem;
    border: 1px solid var(--border);
  }

  .service-card h3 {
    font-family: 'Orbitron', monospace;
    font-size: 0.95rem;
    font-weight: 700;
    color: #fff;
    margin-bottom: 0.75rem;
  }

  .service-card p {
    font-size: 0.88rem;
    color: var(--text-dim);
    line-height: 1.7;
    font-weight: 300;
  }

  /* ── ABOUT ── */
  #about {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
  }

  @media (max-width: 768px) {
    #about { grid-template-columns: 1fr; gap: 3rem; }
    nav ul { display: none; }
  }

  .about-visual {
    position: relative;
    aspect-ratio: 1;
    max-width: 420px;
  }

  .about-orb {
    width: 100%;
    height: 100%;
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
    background: linear-gradient(135deg, rgba(0,255,200,0.08), rgba(0,153,255,0.12));
    border: 1px solid var(--border);
    animation: morphBlob 8s ease-in-out infinite;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 5rem;
  }

  @keyframes morphBlob {
    0%, 100% { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
    33% { border-radius: 70% 30% 50% 50% / 50% 70% 30% 50%; }
    66% { border-radius: 50% 50% 30% 70% / 70% 30% 50% 50%; }
  }

  .feature-list {
    margin-top: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .feature-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
  }

  .feature-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
    margin-top: 0.5rem;
    box-shadow: 0 0 8px var(--accent);
  }

  .feature-item p { font-size: 0.9rem; color: var(--text-dim); line-height: 1.6; }
  .feature-item strong { color: var(--text); font-weight: 500; display: block; margin-bottom: 0.15rem; }

  /* ── PRICING ── */
  .plans-grid {
    margin-top: 3.5rem;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.5rem;
  }

  .plan-card {
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2.5rem;
    background: var(--surface);
    transition: border-color 0.3s, transform 0.3s;
    position: relative;
  }
  .plan-card:hover { border-color: rgba(0,255,200,0.3); transform: translateY(-4px); }

  .plan-card.featured {
    border-color: var(--accent);
    box-shadow: 0 0 40px rgba(0,255,200,0.1);
  }

  .plan-badge {
    position: absolute;
    top: -13px; left: 50%;
    transform: translateX(-50%);
    background: var(--accent);
    color: var(--bg);
    font-family: 'Orbitron', monospace;
    font-size: 0.6rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    padding: 0.25rem 0.75rem;
    border-radius: 100px;
    white-space: nowrap;
  }

  .plan-name {
    font-family: 'Orbitron', monospace;
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    color: var(--text-dim);
    text-transform: uppercase;
    margin-bottom: 1rem;
  }

  .plan-price {
    font-family: 'Orbitron', monospace;
    font-size: 2.5rem;
    font-weight: 900;
    color: #fff;
  }
  .plan-price sup { font-size: 1rem; vertical-align: top; margin-top: 0.5rem; display: inline-block; }
  .plan-price sub { font-size: 0.9rem; color: var(--text-dim); font-weight: 400; }

  .plan-divider {
    height: 1px;
    background: var(--border);
    margin: 1.5rem 0;
  }

  .plan-features { list-style: none; }
  .plan-features li {
    font-size: 0.88rem;
    color: var(--text-dim);
    padding: 0.4rem 0;
    display: flex;
    align-items: center;
    gap: 0.6rem;
  }
  .plan-features li::before { content: '✦'; color: var(--accent); font-size: 0.5rem; }

  .plan-btn {
    margin-top: 2rem;
    display: block;
    text-align: center;
    padding: 0.85rem;
    border-radius: 4px;
    border: 1px solid var(--border);
    color: var(--text);
    text-decoration: none;
    font-size: 0.88rem;
    letter-spacing: 0.05em;
    transition: background 0.25s, border-color 0.25s, color 0.25s;
  }
  .plan-btn:hover { background: var(--accent); border-color: var(--accent); color: var(--bg); }
  .plan-card.featured .plan-btn {
    background: var(--accent);
    border-color: var(--accent);
    color: var(--bg);
    font-weight: 600;
  }
  .plan-card.featured .plan-btn:hover { opacity: 0.85; }

  /* ── TESTIMONIALS ── */
  .testi-grid {
    margin-top: 3.5rem;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }

  .testi-card {
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2rem;
    background: var(--surface);
  }

  .testi-stars { color: var(--accent); font-size: 0.8rem; letter-spacing: 0.1em; margin-bottom: 1rem; }

  .testi-text {
    font-size: 0.92rem;
    color: var(--text-dim);
    line-height: 1.75;
    font-style: italic;
    font-weight: 300;
  }

  .testi-author {
    margin-top: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .testi-avatar {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    display: flex; align-items: center; justify-content: center;
    font-family: 'Orbitron', monospace;
    font-size: 0.7rem;
    font-weight: 700;
    color: var(--bg);
    flex-shrink: 0;
  }

  .testi-author-info strong { display: block; font-size: 0.88rem; color: #fff; font-weight: 500; }
  .testi-author-info span { font-size: 0.78rem; color: var(--text-dim); }

  /* ── CONTACT ── */
  #contact { text-align: center; }
  #contact .section-title, #contact .section-desc { margin-left: auto; margin-right: auto; }

  .contact-form {
    margin-top: 3rem;
    max-width: 560px;
    margin-left: auto;
    margin-right: auto;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  @media (max-width: 480px) { .form-row { grid-template-columns: 1fr; } }

  input, textarea, select {
    width: 100%;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 0.85rem 1rem;
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.25s;
  }
  input:focus, textarea:focus { border-color: var(--accent); }
  input::placeholder, textarea::placeholder { color: var(--muted); }
  textarea { resize: vertical; min-height: 120px; }

  .form-submit {
    background: var(--accent);
    color: var(--bg);
    border: none;
    padding: 1rem;
    border-radius: 4px;
    font-family: 'Orbitron', monospace;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.15em;
    cursor: pointer;
    transition: opacity 0.2s, transform 0.2s;
    box-shadow: 0 0 24px rgba(0,255,200,0.25);
  }
  .form-submit:hover { opacity: 0.9; transform: translateY(-1px); }

  /* ── FOOTER ── */
  footer {
    position: relative;
    z-index: 1;
    border-top: 1px solid var(--border);
    padding: 3rem 6vw;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 1.5rem;
    background: rgba(13,17,23,0.8);
    backdrop-filter: blur(8px);
  }

  .footer-logo {
    font-family: 'Orbitron', monospace;
    font-weight: 900;
    font-size: 1rem;
    color: #fff;
  }
  .footer-logo span { color: var(--accent); }

  .footer-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    flex-wrap: wrap;
  }
  .footer-links a {
    font-size: 0.85rem;
    color: var(--text-dim);
    text-decoration: none;
    transition: color 0.2s;
  }
  .footer-links a:hover { color: var(--accent); }

  .footer-copy {
    font-size: 0.8rem;
    color: var(--text-dim);
    font-weight: 300;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(32px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* Scanline overlay */
  body::after {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      to bottom,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.03) 2px,
      rgba(0,0,0,0.03) 4px
    );
    pointer-events: none;
    z-index: 9999;
  }

  /* Grid decoration */
  .grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,255,200,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,255,200,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    z-index: 0;
    pointer-events: none;
  }
</style>
</head>
<body>

<canvas id="starfield"></canvas>

<!-- NAV -->
<nav>
  <div class="logo">Tech<span>Planet</span></div>
  <ul>
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#contact" class="nav-cta">Get Started</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="grid-bg"></div>
  <div class="hero-content">
    <div class="hero-badge">★ NEXT-GEN IT SOLUTIONS</div>
    <h1>Technology<br>from <em>Another</em><br>Dimension</h1>
    <p class="hero-sub">TechPlanet delivers cutting-edge IT services, cybersecurity, cloud infrastructure, and custom software development that propels your business into the future.</p>
    <div class="hero-btns">
      <a href="#contact" class="btn-primary">Launch Your Project</a>
      <a href="#services" class="btn-ghost">Explore Services</a>
    </div>
  </div>
  <div class="planet-wrap">
    <div class="planet-ring"></div>
    <div class="planet-glow"></div>
  </div>
</section>

<!-- STATS -->
<div id="stats">
  <div class="stat reveal">
    <div class="stat-num" data-target="340">0</div>
    <div class="stat-label">Clients Worldwide</div>
  </div>
  <div class="stat reveal">
    <div class="stat-num" data-target="12">0</div>
    <div class="stat-label">Years of Experience</div>
  </div>
  <div class="stat reveal">
    <div class="stat-num" data-target="99">0</div>
    <div class="stat-label">% Uptime SLA</div>
  </div>
  <div class="stat reveal">
    <div class="stat-num" data-target="48">0</div>
    <div class="stat-label">Hour Response</div>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="section-tag">What We Do</div>
  <h2 class="section-title">Mission-Critical IT Services</h2>
  <p class="section-desc">From managed infrastructure to bespoke software, we handle the tech so you can focus on what matters.</p>

  <div class="services-grid reveal">
    <div class="service-card">
      <div class="svc-icon">🛡️</div>
      <h3>Cybersecurity</h3>
      <p>Advanced threat detection, penetration testing, and zero-trust architecture to keep your systems impenetrable.</p>
    </div>
    <div class="service-card">
      <div class="svc-icon">☁️</div>
      <h3>Cloud Solutions</h3>
      <p>Scalable AWS, Azure, and GCP deployments engineered for performance, resilience, and cost efficiency.</p>
    </div>
    <div class="service-card">
      <div class="svc-icon">💻</div>
      <h3>Custom Software</h3>
      <p>End-to-end development of web apps, APIs, and internal tools built precisely to your requirements.</p>
    </div>
    <div class="service-card">
      <div class="svc-icon">🔧</div>
      <h3>IT Support & Managed</h3>
      <p>24/7 helpdesk, proactive monitoring, and on-site support so your operations never skip a beat.</p>
    </div>
    <div class="service-card">
      <div class="svc-icon">🌐</div>
      <h3>Network Infrastructure</h3>
      <p>Enterprise-grade LAN/WAN design, SD-WAN, and VPN solutions optimized for speed and reliability.</p>
    </div>
    <div class="service-card">
      <div class="svc-icon">🤖</div>
      <h3>AI & Automation</h3>
      <p>Integrate machine learning pipelines and RPA workflows that slash costs and boost productivity.</p>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about" style="background: rgba(13,17,23,0.5);">
  <div class="about-visual reveal">
    <div class="about-orb">🌐</div>
  </div>
  <div class="reveal">
    <div class="section-tag">About TechPlanet</div>
    <h2 class="section-title">We're the IT Partner You've Been Searching For</h2>
    <p class="section-desc">Founded in 2013, TechPlanet has grown from a small IT consultancy into a full-spectrum technology partner serving clients across Europe and North America.</p>
    <div class="feature-list">
      <div class="feature-item">
        <div class="feature-dot"></div>
        <p><strong>Certified Experts</strong> Our team holds 80+ certifications across Microsoft, AWS, Google, and Cisco ecosystems.</p>
      </div>
      <div class="feature-item">
        <div class="feature-dot"></div>
        <p><strong>Agile Delivery</strong> We work in tight sprints with complete transparency so you always know where your project stands.</p>
      </div>
      <div class="feature-item">
        <div class="feature-dot"></div>
        <p><strong>Long-Term Partnership</strong> We measure success by your growth — not just project completion.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section id="pricing">
  <div class="section-tag">Plans & Pricing</div>
  <h2 class="section-title">Simple, Transparent Pricing</h2>
  <p class="section-desc">No hidden fees. No surprises. Choose the plan that fits your orbit.</p>

  <div class="plans-grid">
    <div class="plan-card reveal">
      <div class="plan-name">Starter</div>
      <div class="plan-price"><sup>€</sup>299<sub>/mo</sub></div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Up to 10 workstations</li>
        <li>Business hours support</li>
        <li>Basic cybersecurity monitoring</li>
        <li>Cloud backup (100 GB)</li>
        <li>Monthly system reports</li>
      </ul>
      <a href="#contact" class="plan-btn">Get Started</a>
    </div>

    <div class="plan-card featured reveal">
      <div class="plan-badge">MOST POPULAR</div>
      <div class="plan-name">Professional</div>
      <div class="plan-price"><sup>€</sup>799<sub>/mo</sub></div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Up to 50 workstations</li>
        <li>24/7 helpdesk support</li>
        <li>Advanced threat protection</li>
        <li>Cloud infrastructure management</li>
        <li>Weekly strategy calls</li>
        <li>Priority response (2h SLA)</li>
      </ul>
      <a href="#contact" class="plan-btn">Get Started</a>
    </div>

    <div class="plan-card reveal">
      <div class="plan-name">Enterprise</div>
      <div class="plan-price" style="font-size:1.8rem; line-height:1.4; color: var(--text-dim);">Custom</div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Unlimited workstations</li>
        <li>Dedicated account manager</li>
        <li>Custom security protocols</li>
        <li>Multi-site infrastructure</li>
        <li>AI & automation consulting</li>
        <li>1-hour emergency SLA</li>
      </ul>
      <a href="#contact" class="plan-btn">Talk to Sales</a>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials" style="background: rgba(13,17,23,0.5);">
  <div class="section-tag">Client Stories</div>
  <h2 class="section-title">Trusted by Teams That Can't Afford Downtime</h2>

  <div class="testi-grid">
    <div class="testi-card reveal">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-text">"TechPlanet migrated our entire infrastructure to the cloud with zero downtime. The team's expertise and communication were exceptional throughout."</p>
      <div class="testi-author">
        <div class="testi-avatar">SR</div>
        <div class="testi-author-info">
          <strong>Sarah Reynolds</strong>
          <span>CTO, Novaris Group</span>
        </div>
      </div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-text">"Their cybersecurity team identified vulnerabilities our previous auditor missed entirely. We feel genuinely secure for the first time."</p>
      <div class="testi-author">
        <div class="testi-avatar">MK</div>
        <div class="testi-author-info">
          <strong>Marcus Klein</strong>
          <span>CEO, Fintrade Solutions</span>
        </div>
      </div>
    </div>
    <div class="testi-card reveal">
      <div class="testi-stars">★★★★★</div>
      <p class="testi-text">"Response times are incredible. A critical server issue at 3am was resolved within 90 minutes. The Professional plan pays for itself every month."</p>
      <div class="testi-author">
        <div class="testi-avatar">LP</div>
        <div class="testi-author-info">
          <strong>Laura Pacheco</strong>
          <span>Operations Director, LogiXpress</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-tag">Get In Touch</div>
  <h2 class="section-title">Ready to Elevate Your Technology?</h2>
  <p class="section-desc">Tell us about your project and our team will get back to you within 24 hours.</p>

  <form class="contact-form reveal" onsubmit="handleSubmit(event)">
    <div class="form-row">
      <input type="text" placeholder="Your name" required>
      <input type="email" placeholder="Email address" required>
    </div>
    <input type="text" placeholder="Company name">
    <textarea placeholder="Describe your IT needs or challenges..."></textarea>
    <button type="submit" class="form-submit">SEND MESSAGE ›</button>
  </form>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Tech<span>Planet</span></div>
  <ul class="footer-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#">Privacy Policy</a></li>
    <li><a href="#">Terms</a></li>
  </ul>
  <div class="footer-copy">© 2025 TechPlanet Ltd. All rights reserved.</div>
</footer>

<script>
  // ── STARFIELD ──
  const canvas = document.getElementById('starfield');
  const ctx = canvas.getContext('2d');
  let stars = [];

  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }

  function initStars() {
    stars = Array.from({ length: 160 }, () => ({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      r: Math.random() * 1.2 + 0.2,
      opacity: Math.random() * 0.7 + 0.1,
      speed: Math.random() * 0.3 + 0.05,
      twinkle: Math.random() * Math.PI * 2
    }));
  }

  function drawStars(t) {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    stars.forEach(s => {
      s.twinkle += 0.01;
      const alpha = s.opacity * (0.6 + 0.4 * Math.sin(s.twinkle));
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(200,230,255,${alpha})`;
      ctx.fill();
      s.y -= s.speed;
      if (s.y < 0) { s.y = canvas.height; s.x = Math.random() * canvas.width; }
    });
    requestAnimationFrame(drawStars);
  }

  resize();
  initStars();
  drawStars();
  window.addEventListener('resize', () => { resize(); initStars(); });

  // ── SCROLL REVEAL ──
  const reveals = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.12 });
  reveals.forEach(el => obs.observe(el));

  // ── COUNT UP ──
  const statNums = document.querySelectorAll('.stat-num[data-target]');
  const countObs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const el = e.target;
        const target = +el.dataset.target;
        let current = 0;
        const inc = target / 60;
        const timer = setInterval(() => {
          current = Math.min(current + inc, target);
          el.textContent = Math.round(current) + (target === 99 ? '%' : '+');
          if (current >= target) clearInterval(timer);
        }, 20);
        countObs.unobserve(el);
      }
    });
  }, { threshold: 0.5 });
  statNums.forEach(el => countObs.observe(el));

  // ── FORM ──
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.form-submit');
    btn.textContent = 'MESSAGE SENT ✦';
    btn.style.background = '#00cc99';
    setTimeout(() => {
      btn.textContent = 'SEND MESSAGE ›';
      btn.style.background = '';
      e.target.reset();
    }, 3000);
  }
</script>
</body>
</html>
