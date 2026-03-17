# Building-website-2
Ascent Consulting
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dr. Monazza Shahab | Pre-Med & PhD Mentoring</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
  :root {
    --ink: #0e1117;
    --ink-light: #3a3f4a;
    --gold: #b8922a;
    --gold-light: #d4a93c;
    --cream: #f8f5ef;
    --cream-deep: #ede9e0;
    --white: #ffffff;
    --rule: rgba(14,17,23,0.12);
    --serif: 'Cormorant Garamond', Georgia, serif;
    --sans: 'DM Sans', sans-serif;
  }
 
  html { scroll-behavior: smooth; }
 
  body {
    font-family: var(--sans);
    background: var(--cream);
    color: var(--ink);
    font-size: 16px;
    line-height: 1.6;
    overflow-x: hidden;
  }
 
  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 22px 5vw;
    background: rgba(248,245,239,0.88);
    backdrop-filter: blur(12px);
    border-bottom: 0.5px solid var(--rule);
    transition: box-shadow .3s;
  }
  nav.scrolled { box-shadow: 0 2px 24px rgba(0,0,0,0.06); }
 
  .nav-logo {
    font-family: var(--serif);
    font-size: 1.15rem;
    font-weight: 500;
    letter-spacing: 0.01em;
    color: var(--ink);
    text-decoration: none;
  }
  .nav-logo span { color: var(--gold); }
 
  .nav-links {
    display: flex;
    gap: 36px;
    list-style: none;
  }
  .nav-links a {
    font-family: var(--sans);
    font-size: 0.82rem;
    font-weight: 400;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--ink-light);
    text-decoration: none;
    transition: color .2s;
  }
  .nav-links a:hover { color: var(--gold); }
 
  .nav-cta {
    font-family: var(--sans);
    font-size: 0.82rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--white);
    background: var(--ink);
    padding: 10px 22px;
    border-radius: 2px;
    text-decoration: none;
    transition: background .2s;
  }
  .nav-cta:hover { background: var(--gold); }
 
  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 80px;
    position: relative;
    overflow: hidden;
  }
 
  .hero::before {
    content: '';
    position: absolute;
    top: -120px; right: -80px;
    width: 600px; height: 600px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(184,146,42,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
 
  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 80px 5vw 80px 8vw;
  }
 
  .hero-eyebrow {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp .7s .1s forwards;
  }
  .hero-eyebrow-line {
    width: 32px; height: 1px;
    background: var(--gold);
  }
  .hero-eyebrow span {
    font-family: var(--sans);
    font-size: 0.75rem;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
  }
 
  .hero h1 {
    font-family: var(--serif);
    font-size: clamp(3rem, 5vw, 4.8rem);
    font-weight: 500;
    line-height: 1.08;
    letter-spacing: -0.01em;
    color: var(--ink);
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp .7s .2s forwards;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--gold);
  }
 
  .hero-sub {
    font-family: var(--sans);
    font-size: 1rem;
    font-weight: 300;
    line-height: 1.8;
    color: var(--ink-light);
    max-width: 440px;
    margin-bottom: 44px;
    opacity: 0;
    animation: fadeUp .7s .3s forwards;
  }
 
  .hero-actions {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    opacity: 0;
    animation: fadeUp .7s .4s forwards;
  }
 
  .btn-primary {
    font-family: var(--sans);
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--white);
    background: var(--ink);
    padding: 16px 32px;
    border-radius: 2px;
    text-decoration: none;
    transition: background .2s, transform .15s;
    display: inline-block;
  }
  .btn-primary:hover { background: var(--gold); transform: translateY(-1px); }
 
  .btn-ghost {
    font-family: var(--sans);
    font-size: 0.85rem;
    font-weight: 400;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink);
    background: transparent;
    padding: 16px 32px;
    border-radius: 2px;
    border: 1px solid var(--rule);
    text-decoration: none;
    transition: border-color .2s, color .2s, transform .15s;
    display: inline-block;
  }
  .btn-ghost:hover { border-color: var(--gold); color: var(--gold); transform: translateY(-1px); }
 
  .hero-right {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 80px 8vw 80px 4vw;
    position: relative;
    opacity: 0;
    animation: fadeIn .9s .5s forwards;
  }
 
  .hero-credentials {
    background: var(--white);
    border: 0.5px solid var(--rule);
    border-radius: 4px;
    padding: 40px 36px;
    width: 100%;
    max-width: 380px;
    position: relative;
  }
  .hero-credentials::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--gold);
    border-radius: 4px 0 0 4px;
  }
 
  .cred-label {
    font-family: var(--sans);
    font-size: 0.7rem;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 24px;
  }
 
  .cred-item {
    display: flex;
    gap: 16px;
    align-items: flex-start;
    padding: 16px 0;
    border-bottom: 0.5px solid var(--rule);
  }
  .cred-item:last-child { border-bottom: none; padding-bottom: 0; }
 
  .cred-icon {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: var(--cream);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 14px;
  }
 
  .cred-text strong {
    display: block;
    font-family: var(--serif);
    font-size: 1.05rem;
    font-weight: 600;
    line-height: 1.3;
    color: var(--ink);
  }
  .cred-text span {
    font-size: 0.78rem;
    color: var(--ink-light);
    font-weight: 300;
  }
 
  /* ── TRUST BAR ── */
  .trust-bar {
    background: var(--ink);
    padding: 28px 8vw;
    display: flex;
    align-items: center;
    gap: 48px;
    overflow-x: auto;
    flex-wrap: wrap;
    justify-content: center;
  }
  .trust-item {
    display: flex;
    align-items: center;
    gap: 10px;
    flex-shrink: 0;
  }
  .trust-dot {
    width: 5px; height: 5px;
    border-radius: 50%;
    background: var(--gold);
  }
  .trust-item span {
    font-family: var(--sans);
    font-size: 0.78rem;
    font-weight: 300;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.7);
    white-space: nowrap;
  }
 
  /* ── SECTIONS ── */
  section { padding: 100px 8vw; }
 
  .section-eyebrow {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 20px;
  }
  .section-eyebrow-line { width: 24px; height: 1px; background: var(--gold); }
  .section-eyebrow span {
    font-size: 0.72rem;
    font-weight: 500;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--gold);
  }
 
  .section-title {
    font-family: var(--serif);
    font-size: clamp(2.2rem, 4vw, 3.4rem);
    font-weight: 500;
    line-height: 1.1;
    color: var(--ink);
    margin-bottom: 16px;
  }
  .section-title em { font-style: italic; color: var(--gold); }
 
  .section-sub {
    font-size: 1rem;
    font-weight: 300;
    line-height: 1.8;
    color: var(--ink-light);
    max-width: 560px;
    margin-bottom: 60px;
  }
 
  /* ── SERVICES ── */
  #services { background: var(--white); }
 
  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: var(--rule);
    border: 0.5px solid var(--rule);
    border-radius: 4px;
    overflow: hidden;
  }
 
  .service-card {
    background: var(--white);
    padding: 44px 36px;
    position: relative;
    transition: background .25s;
    cursor: default;
  }
  .service-card:hover { background: var(--cream); }
 
  .service-num {
    font-family: var(--serif);
    font-size: 3rem;
    font-weight: 400;
    color: rgba(184,146,42,0.18);
    line-height: 1;
    margin-bottom: 20px;
    letter-spacing: -0.02em;
  }
 
  .service-tag {
    display: inline-block;
    font-size: 0.68rem;
    font-weight: 500;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--gold);
    background: rgba(184,146,42,0.1);
    padding: 4px 10px;
    border-radius: 2px;
    margin-bottom: 16px;
  }
 
  .service-card h3 {
    font-family: var(--serif);
    font-size: 1.55rem;
    font-weight: 500;
    line-height: 1.2;
    color: var(--ink);
    margin-bottom: 14px;
  }
 
  .service-card p {
    font-size: 0.88rem;
    font-weight: 300;
    line-height: 1.8;
    color: var(--ink-light);
    margin-bottom: 24px;
  }
 
  .service-details {
    list-style: none;
    margin-bottom: 28px;
  }
  .service-details li {
    font-size: 0.82rem;
    font-weight: 300;
    color: var(--ink-light);
    padding: 5px 0;
    padding-left: 16px;
    position: relative;
    border-bottom: 0.5px solid var(--rule);
  }
  .service-details li:last-child { border-bottom: none; }
  .service-details li::before {
    content: '—';
    position: absolute; left: 0;
    color: var(--gold);
    font-size: 0.75rem;
  }
 
  .service-price {
    font-family: var(--serif);
    font-size: 1.1rem;
    font-weight: 500;
    color: var(--ink);
  }
  .service-price-note {
    font-size: 0.75rem;
    font-weight: 300;
    color: var(--ink-light);
    display: block;
    margin-top: 2px;
  }
 
  /* ── HOW IT WORKS ── */
  #process { background: var(--cream); }
 
  .process-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
  }
 
  .process-steps { display: flex; flex-direction: column; gap: 0; }
 
  .process-step {
    display: flex;
    gap: 24px;
    padding: 28px 0;
    border-bottom: 0.5px solid var(--rule);
    position: relative;
  }
  .process-step:first-child { padding-top: 0; }
  .process-step:last-child { border-bottom: none; }
 
  .step-num {
    font-family: var(--serif);
    font-size: 2.5rem;
    font-weight: 400;
    color: var(--gold);
    line-height: 1;
    flex-shrink: 0;
    width: 48px;
    text-align: right;
  }
  .step-content h4 {
    font-family: var(--serif);
    font-size: 1.25rem;
    font-weight: 500;
    color: var(--ink);
    margin-bottom: 8px;
  }
  .step-content p {
    font-size: 0.88rem;
    font-weight: 300;
    line-height: 1.8;
    color: var(--ink-light);
  }
 
  .process-aside {
    background: var(--ink);
    border-radius: 4px;
    padding: 52px 44px;
    position: relative;
    overflow: hidden;
  }
  .process-aside::before {
    content: '"';
    font-family: var(--serif);
    font-size: 18rem;
    font-weight: 400;
    color: rgba(184,146,42,0.08);
    position: absolute;
    top: -60px; left: 20px;
    line-height: 1;
    pointer-events: none;
  }
  .process-aside blockquote {
    font-family: var(--serif);
    font-size: 1.55rem;
    font-weight: 400;
    font-style: italic;
    line-height: 1.5;
    color: var(--white);
    margin-bottom: 28px;
    position: relative;
  }
  .process-aside cite {
    font-family: var(--sans);
    font-size: 0.78rem;
    font-weight: 300;
    letter-spacing: 0.1em;
    color: rgba(255,255,255,0.5);
    font-style: normal;
    text-transform: uppercase;
  }
  .aside-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: rgba(255,255,255,0.08);
    border-top: 0.5px solid rgba(255,255,255,0.12);
    margin-top: 36px;
    padding-top: 28px;
  }
  .aside-stat { padding: 0 20px 0 0; }
  .aside-stat:last-child { padding-left: 20px; padding-right: 0; border-left: 0.5px solid rgba(255,255,255,0.12); }
  .aside-stat-num {
    font-family: var(--serif);
    font-size: 2.4rem;
    font-weight: 500;
    color: var(--gold-light);
    line-height: 1;
    margin-bottom: 4px;
  }
  .aside-stat-label {
    font-size: 0.75rem;
    font-weight: 300;
    color: rgba(255,255,255,0.5);
    letter-spacing: 0.05em;
  }
 
  /* ── WHO I HELP ── */
  #who { background: var(--white); }
 
  .who-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
  }
  .who-card {
    padding: 32px 24px;
    border: 0.5px solid var(--rule);
    border-radius: 4px;
    transition: border-color .2s, transform .2s;
  }
  .who-card:hover { border-color: var(--gold); transform: translateY(-3px); }
 
  .who-icon {
    width: 44px; height: 44px;
    background: var(--cream);
    border-radius: 2px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    margin-bottom: 20px;
  }
  .who-card h4 {
    font-family: var(--serif);
    font-size: 1.2rem;
    font-weight: 500;
    color: var(--ink);
    margin-bottom: 10px;
  }
  .who-card p {
    font-size: 0.83rem;
    font-weight: 300;
    line-height: 1.7;
    color: var(--ink-light);
  }
 
  /* ── CTA ── */
  .cta-section {
    background: var(--ink);
    padding: 100px 8vw;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .cta-section::before {
    content: '';
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 700px; height: 700px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(184,146,42,0.08) 0%, transparent 65%);
    pointer-events: none;
  }
  .cta-section h2 {
    font-family: var(--serif);
    font-size: clamp(2.5rem, 5vw, 4rem);
    font-weight: 500;
    font-style: italic;
    color: var(--white);
    margin-bottom: 20px;
    line-height: 1.1;
  }
  .cta-section h2 span { color: var(--gold-light); font-style: normal; }
  .cta-section p {
    font-size: 0.95rem;
    font-weight: 300;
    color: rgba(255,255,255,0.6);
    margin-bottom: 44px;
    max-width: 480px;
    margin-left: auto;
    margin-right: auto;
  }
  .cta-btns { display: flex; gap: 16px; justify-content: center; flex-wrap: wrap; }
  .btn-gold {
    font-family: var(--sans);
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--ink);
    background: var(--gold-light);
    padding: 16px 36px;
    border-radius: 2px;
    text-decoration: none;
    transition: background .2s, transform .15s;
    display: inline-block;
  }
  .btn-gold:hover { background: var(--gold); transform: translateY(-2px); }
  .btn-outline-white {
    font-family: var(--sans);
    font-size: 0.85rem;
    font-weight: 400;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.8);
    background: transparent;
    padding: 16px 36px;
    border-radius: 2px;
    border: 1px solid rgba(255,255,255,0.2);
    text-decoration: none;
    transition: border-color .2s, color .2s;
    display: inline-block;
  }
  .btn-outline-white:hover { border-color: var(--gold); color: var(--gold-light); }
 
  /* ── FOOTER ── */
  footer {
    background: var(--cream-deep);
    padding: 40px 8vw;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-top: 0.5px solid var(--rule);
    flex-wrap: wrap;
    gap: 16px;
  }
  .footer-logo {
    font-family: var(--serif);
    font-size: 1rem;
    font-weight: 500;
    color: var(--ink);
    text-decoration: none;
  }
  .footer-logo span { color: var(--gold); }
  footer p {
    font-size: 0.78rem;
    font-weight: 300;
    color: var(--ink-light);
  }
  .footer-links { display: flex; gap: 24px; }
  .footer-links a {
    font-size: 0.78rem;
    font-weight: 300;
    color: var(--ink-light);
    text-decoration: none;
    letter-spacing: 0.05em;
    transition: color .2s;
  }
  .footer-links a:hover { color: var(--gold); }
 
  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }
 
  .reveal {
    opacity: 0;
    transform: translateY(28px);
    transition: opacity .7s, transform .7s;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
 
  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-right { padding: 0 8vw 60px; }
    .services-grid { grid-template-columns: 1fr; }
    .process-grid { grid-template-columns: 1fr; }
    .who-grid { grid-template-columns: 1fr 1fr; }
    .nav-links { display: none; }
  }
  @media (max-width: 600px) {
    .who-grid { grid-template-columns: 1fr; }
    .trust-bar { gap: 24px; padding: 24px 5vw; }
    section { padding: 70px 5vw; }
    .hero-left { padding: 80px 5vw; }
  }
</style>
</head>
<body>
 
<!-- NAV -->
<nav id="navbar">
  <a href="#" class="nav-logo">Dr. Monazza <span>Shahab</span></a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#process">How it works</a></li>
    <li><a href="#who">Who I help</a></li>
  </ul>
  <a href="mailto:monazzashahab@gmail.com" class="nav-cta">Book a consult</a>
</nav>
 
<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">
      <div class="hero-eyebrow-line"></div>
      <span>Pre-Med · PhD · MD-PhD Mentoring</span>
    </div>
 
    <h1>Get into the program<br>you <em>actually</em> deserve.</h1>
 
    <p class="hero-sub">
      Guided by a PhD pharmacologist who trained at Memorial Sloan Kettering Cancer Center — with expertise in every stage of the journey, from your first MCAT practice test to your final research publication.
    </p>
 
    <div class="hero-actions">
      <a href="mailto:monazzashahab@gmail.com" class="btn-primary">Book a free consult</a>
      <a href="#services" class="btn-ghost">See what I offer</a>
    </div>
  </div>
 
  <div class="hero-right">
    <div class="hero-credentials">
      <p class="cred-label">Credentials</p>
 
      <div class="cred-item">
        <div class="cred-icon">🔬</div>
        <div class="cred-text">
          <strong>Memorial Sloan Kettering Cancer Center</strong>
          <span>Research Scholar — ranked #2 globally in cancer research</span>
        </div>
      </div>
 
      <div class="cred-item">
        <div class="cred-icon">🎓</div>
        <div class="cred-text">
          <strong>PhD in Pharmacology</strong>
          <span>Wayne State University · 6 peer-reviewed publications</span>
        </div>
      </div>
 
      <div class="cred-item">
        <div class="cred-icon">📄</div>
        <div class="cred-text">
          <strong>Invited Peer Reviewer</strong>
          <span>Nature Portfolio · Communications Biology</span>
        </div>
      </div>
 
      <div class="cred-item">
        <div class="cred-icon">🧠</div>
        <div class="cred-text">
          <strong>Postdoctoral Scientist</strong>
          <span>University of Michigan · Vision Neuroscience & ML</span>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- TRUST BAR -->
<div class="trust-bar">
  <div class="trust-item"><div class="trust-dot"></div><span>PhD Pharmacology</span></div>
  <div class="trust-item"><div class="trust-dot"></div><span>MSKCC Postdoc</span></div>
  <div class="trust-item"><div class="trust-dot"></div><span>Nature Peer Reviewer</span></div>
  <div class="trust-item"><div class="trust-dot"></div><span>6 Publications</span></div>
  <div class="trust-item"><div class="trust-dot"></div><span>Applied ML · Columbia</span></div>
  <div class="trust-item"><div class="trust-dot"></div><span>Columbus & Online</span></div>
</div>
 
<!-- SERVICES -->
<section id="services">
  <div class="reveal">
    <div class="section-eyebrow"><div class="section-eyebrow-line"></div><span>What I offer</span></div>
    <h2 class="section-title">Three ways I get<br>students <em>across the line.</em></h2>
    <p class="section-sub">Whether you need test scores, a compelling application, or a publication under your belt — I cover the full spectrum of what admissions committees actually look at.</p>
  </div>
 
  <div class="services-grid reveal">
 
    <div class="service-card">
      <div class="service-num">01</div>
      <span class="service-tag">Group · In-person & Online</span>
      <h3>Test Preparation</h3>
      <p>Small-group sessions that go beyond strategy — taught by someone who understands the science behind every question, not just the test format.</p>
      <ul class="service-details">
        <li>MCAT — Biology, Biochem, Chemistry, Psychology</li>
        <li>GRE — Verbal, Quant, Analytical Writing</li>
        <li>SAT / ACT — Science & Math focus</li>
        <li>Groups of 3–5 students maximum</li>
        <li>Custom study plans and weekly progress checks</li>
      </ul>
      <div class="service-price">From $80/student per session
        <span class="service-price-note">2-hour group sessions · packages available</span>
      </div>
    </div>
 
    <div class="service-card">
      <div class="service-num">02</div>
      <span class="service-tag">1-on-1 · Online</span>
      <h3>Application Counseling</h3>
      <p>Full-cycle guidance from someone who has lived both the PhD and the MD-PhD track — built around your actual story, not a template.</p>
      <ul class="service-details">
        <li>School list strategy & program targeting</li>
        <li>Personal statement & secondary essays</li>
        <li>Statement of Purpose for PhD programs</li>
        <li>Interview prep — MMI, traditional, panel</li>
        <li>MD-PhD program specialization</li>
      </ul>
      <div class="service-price">From $2,500 per package
        <span class="service-price-note">Medical school · PhD · MD-PhD · 4–6 months support</span>
      </div>
    </div>
 
    <div class="service-card">
      <div class="service-num">03</div>
      <span class="service-tag">1-on-1 · Online</span>
      <h3>Research Paper Coaching</h3>
      <p>For current PhD students, residents, and pre-meds who need a first-author publication. Peer review expertise that most tutors simply cannot offer.</p>
      <ul class="service-details">
        <li>Manuscript structure, framing & argument</li>
        <li>Methods & results section writing</li>
        <li>Bioinformatics & data interpretation</li>
        <li>Journal selection & submission strategy</li>
        <li>Response-to-reviewers coaching</li>
      </ul>
      <div class="service-price">From $150/hr or project-based
        <span class="service-price-note">Hourly or fixed-scope project pricing</span>
      </div>
    </div>
 
  </div>
</section>
 
<!-- PROCESS -->
<section id="process">
  <div class="process-grid">
    <div class="reveal">
      <div class="section-eyebrow"><div class="section-eyebrow-line"></div><span>How it works</span></div>
      <h2 class="section-title">Simple,<br><em>structured,</em><br>effective.</h2>
      <p class="section-sub" style="margin-bottom: 40px;">No cookie-cutter packages. Every student gets a plan built around where they are and where they need to go.</p>
 
      <div class="process-steps">
        <div class="process-step">
          <div class="step-num">1</div>
          <div class="step-content">
            <h4>Free 30-minute consultation</h4>
            <p>We talk through your goals, timeline, and what's standing between you and your target program. No obligation.</p>
          </div>
        </div>
        <div class="process-step">
          <div class="step-num">2</div>
          <div class="step-content">
            <h4>Custom plan designed for you</h4>
            <p>I put together a specific roadmap — which services, what timeline, how we'll measure progress.</p>
          </div>
        </div>
        <div class="process-step">
          <div class="step-num">3</div>
          <div class="step-content">
            <h4>Weekly sessions, real accountability</h4>
            <p>Structured sessions with between-session support. You always know exactly what to do next.</p>
          </div>
        </div>
        <div class="process-step">
          <div class="step-num">4</div>
          <div class="step-content">
            <h4>Submit with confidence</h4>
            <p>Applications, tests, and papers that reflect the full strength of what you've built.</p>
          </div>
        </div>
      </div>
    </div>
 
    <div class="reveal">
      <div class="process-aside">
        <blockquote>
          "The students who get into top programs aren't smarter than you. They're better prepared — and better guided."
        </blockquote>
        <cite>— Dr. Monazza Shahab</cite>
 
        <div class="aside-stats">
          <div class="aside-stat">
            <div class="aside-stat-num">6</div>
            <div class="aside-stat-label">Peer-reviewed publications</div>
          </div>
          <div class="aside-stat">
            <div class="aside-stat-num">#2</div>
            <div class="aside-stat-label">Cancer center globally (MSKCC)</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- WHO I HELP -->
<section id="who">
  <div class="reveal">
    <div class="section-eyebrow"><div class="section-eyebrow-line"></div><span>Who I work with</span></div>
    <h2 class="section-title">Built for students<br>with <em>serious ambitions.</em></h2>
    <p class="section-sub">I work with a small number of students at a time. If you're in any of these situations, we should talk.</p>
  </div>
 
  <div class="who-grid reveal">
    <div class="who-card">
      <div class="who-icon">⚗️</div>
      <h4>Pre-med undergraduates</h4>
      <p>Targeting MD or MD-PhD programs and need MCAT prep, research experience coaching, and an application that stands out.</p>
    </div>
    <div class="who-card">
      <div class="who-icon">📚</div>
      <h4>Graduating seniors & post-baccs</h4>
      <p>Applying this cycle or planning your gap year strategy. Full-service application support from school list to submit.</p>
    </div>
    <div class="who-card">
      <div class="who-icon">🧬</div>
      <h4>PhD program applicants</h4>
      <p>In biology, neuroscience, pharmacology, or related fields — needing SOPs, school targeting, and interview coaching.</p>
    </div>
    <div class="who-card">
      <div class="who-icon">📝</div>
      <h4>Current PhD students & residents</h4>
      <p>Working on your first or second publication and needing hands-on writing, framing, and submission strategy support.</p>
    </div>
  </div>
</section>
 
<!-- CTA -->
<div class="cta-section">
  <div class="reveal">
    <h2>Ready to start? <span>Let's talk.</span></h2>
    <p>First consultation is free. Serving Columbus, Ohio and students nationwide online.</p>
    <div class="cta-btns">
      <a href="mailto:monazzashahab@gmail.com" class="btn-gold">Book your free consult</a>
      <a href="https://linkedin.com/in/mskwsu-monazza/" target="_blank" class="btn-outline-white">View credentials on LinkedIn</a>
    </div>
  </div>
</div>
 
<!-- FOOTER -->
<footer>
  <a href="#" class="footer-logo">Dr. Monazza <span>Shahab</span></a>
  <p>© 2025 · Columbus, OH & Online Nationwide</p>
  <div class="footer-links">
    <a href="mailto:monazzashahab@gmail.com">Email</a>
    <a href="https://linkedin.com/in/mskwsu-monazza/" target="_blank">LinkedIn</a>
    <a href="https://orcid.org/0000-0002-5134-2233" target="_blank">ORCID</a>
  </div>
</footer>
 
<script>
  // Scroll nav shadow
  const navbar = document.getElementById('navbar');
  window.addEventListener('scroll', () => {
    navbar.classList.toggle('scrolled', window.scrollY > 20);
  });
 
  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));
</script>
</body>
</html>
 
