# customs-portal-ad
Customs Calc for Enturpenurs 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Customs Intelligence Portal — Ad</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --green:   #1a7a4a;
    --green-mid: #22a05c;
    --green-light: #4cca83;
    --gold:    #d4a843;
    --dark:    #0d1a12;
    --card-bg: rgba(255,255,255,0.04);
    --border:  rgba(255,255,255,0.08);
  }

  body {
    background: var(--dark);
    color: #e8f0eb;
    font-family: 'DM Sans', sans-serif;
    overflow-x: hidden;
  }

  /* ── HERO ────────────────────────────────────────────────── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 80px 24px 60px;
    overflow: hidden;
  }

  /* animated mesh background */
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 70% 60% at 20% 30%, rgba(26,122,74,.35) 0%, transparent 60%),
      radial-gradient(ellipse 50% 50% at 80% 70%, rgba(34,160,92,.20) 0%, transparent 55%),
      radial-gradient(ellipse 40% 40% at 50% 10%, rgba(212,168,67,.12) 0%, transparent 50%);
    animation: meshPulse 8s ease-in-out infinite alternate;
  }

  @keyframes meshPulse {
    0%   { opacity: .7; transform: scale(1); }
    100% { opacity: 1;  transform: scale(1.05); }
  }

  /* port grid overlay */
  .hero::after {
    content: '';
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(76,202,131,.06) 1px, transparent 1px),
      linear-gradient(90deg, rgba(76,202,131,.06) 1px, transparent 1px);
    background-size: 48px 48px;
    mask-image: radial-gradient(ellipse at center, black 30%, transparent 75%);
  }

  .hero-badge {
    position: relative; z-index: 2;
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(26,122,74,.25);
    border: 1px solid rgba(76,202,131,.3);
    border-radius: 50px;
    padding: 6px 18px;
    font-size: .78rem;
    font-weight: 600;
    letter-spacing: .12em;
    text-transform: uppercase;
    color: var(--green-light);
    margin-bottom: 28px;
    animation: fadeDown .8s ease both;
  }

  .hero-badge::before {
    content: '';
    width: 7px; height: 7px;
    background: var(--green-light);
    border-radius: 50%;
    animation: blink 1.4s ease-in-out infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:.3} }

  .hero-title {
    position: relative; z-index: 2;
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.6rem, 7vw, 5.5rem);
    font-weight: 900;
    line-height: 1.08;
    letter-spacing: -.02em;
    max-width: 820px;
    animation: fadeDown .9s .15s ease both;
  }

  .hero-title .accent { color: var(--green-light); }
  .hero-title .gold   { color: var(--gold); }

  .hero-sub {
    position: relative; z-index: 2;
    font-size: clamp(1rem, 2vw, 1.2rem);
    font-weight: 300;
    color: rgba(232,240,235,.65);
    max-width: 560px;
    line-height: 1.7;
    margin: 24px auto 40px;
    animation: fadeDown 1s .3s ease both;
  }

  .hero-cta-row {
    position: relative; z-index: 2;
    display: flex; flex-wrap: wrap; gap: 14px; justify-content: center;
    animation: fadeDown 1s .45s ease both;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--green), var(--green-mid));
    color: #fff;
    font-family: 'DM Sans', sans-serif;
    font-size: .95rem;
    font-weight: 600;
    padding: 14px 36px;
    border-radius: 50px;
    border: none;
    cursor: pointer;
    text-decoration: none;
    box-shadow: 0 0 30px rgba(34,160,92,.35);
    transition: transform .2s, box-shadow .2s;
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 0 45px rgba(34,160,92,.5); }

  .btn-ghost {
    background: transparent;
    color: rgba(232,240,235,.8);
    font-family: 'DM Sans', sans-serif;
    font-size: .95rem;
    font-weight: 500;
    padding: 13px 32px;
    border-radius: 50px;
    border: 1px solid rgba(255,255,255,.18);
    cursor: pointer;
    text-decoration: none;
    transition: border-color .2s, color .2s;
  }
  .btn-ghost:hover { border-color: var(--green-light); color: var(--green-light); }

  @keyframes fadeDown {
    from { opacity:0; transform: translateY(-20px); }
    to   { opacity:1; transform: translateY(0); }
  }

  /* ── STATS BAR ───────────────────────────────────────────── */
  .stats-bar {
    position: relative; z-index: 2;
    margin-top: 64px;
    display: flex; flex-wrap: wrap; gap: 0;
    justify-content: center;
    border: 1px solid var(--border);
    border-radius: 18px;
    overflow: hidden;
    backdrop-filter: blur(12px);
    background: rgba(255,255,255,.03);
    max-width: 740px;
    animation: fadeDown 1s .6s ease both;
  }

  .stat-item {
    flex: 1 1 150px;
    padding: 22px 28px;
    text-align: center;
    border-right: 1px solid var(--border);
  }
  .stat-item:last-child { border-right: none; }

  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    font-weight: 700;
    color: var(--green-light);
    line-height: 1;
  }
  .stat-label {
    font-size: .78rem;
    font-weight: 500;
    color: rgba(232,240,235,.5);
    margin-top: 5px;
    letter-spacing: .06em;
    text-transform: uppercase;
  }

  /* ── SECTION COMMON ──────────────────────────────────────── */
  section { padding: 96px 24px; max-width: 1100px; margin: 0 auto; }

  .section-label {
    font-size: .72rem;
    font-weight: 700;
    letter-spacing: .2em;
    text-transform: uppercase;
    color: var(--green-light);
    margin-bottom: 16px;
  }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.9rem, 4vw, 3rem);
    font-weight: 700;
    line-height: 1.18;
    max-width: 640px;
  }

  .section-body {
    font-size: 1.05rem;
    font-weight: 300;
    color: rgba(232,240,235,.65);
    max-width: 560px;
    line-height: 1.8;
    margin-top: 18px;
  }

  /* ── FEATURE CARDS ───────────────────────────────────────── */
  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
    margin-top: 56px;
  }

  .feat-card {
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 32px 28px;
    position: relative;
    overflow: hidden;
    transition: transform .25s, border-color .25s;
  }
  .feat-card:hover {
    transform: translateY(-5px);
    border-color: rgba(76,202,131,.3);
  }

  .feat-card::before {
    content: '';
    position: absolute;
    top: -40px; right: -40px;
    width: 140px; height: 140px;
    background: radial-gradient(circle, rgba(26,122,74,.22) 0%, transparent 70%);
    border-radius: 50%;
    pointer-events: none;
  }

  .feat-icon {
    width: 48px; height: 48px;
    background: linear-gradient(135deg, rgba(26,122,74,.4), rgba(76,202,131,.15));
    border: 1px solid rgba(76,202,131,.25);
    border-radius: 14px;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.4rem;
    margin-bottom: 20px;
  }

  .feat-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem;
    font-weight: 700;
    margin-bottom: 10px;
  }

  .feat-desc {
    font-size: .92rem;
    font-weight: 300;
    color: rgba(232,240,235,.6);
    line-height: 1.7;
  }

  /* ── HOW IT WORKS ────────────────────────────────────────── */
  .how-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 64px;
    align-items: center;
    margin-top: 0;
  }

  @media (max-width: 700px) { .how-wrapper { grid-template-columns: 1fr; gap: 40px; } }

  .steps-list { list-style: none; }

  .step-item {
    display: flex; gap: 20px;
    padding: 22px 0;
    border-bottom: 1px solid var(--border);
  }
  .step-item:last-child { border-bottom: none; }

  .step-num {
    flex-shrink: 0;
    width: 36px; height: 36px;
    background: linear-gradient(135deg, var(--green), var(--green-mid));
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: .85rem;
    font-weight: 700;
    color: #fff;
    box-shadow: 0 0 14px rgba(34,160,92,.3);
  }

  .step-body h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1.05rem;
    margin-bottom: 5px;
  }
  .step-body p {
    font-size: .88rem;
    color: rgba(232,240,235,.55);
    line-height: 1.7;
  }

  /* mock phone */
  .phone-mockup {
    background: linear-gradient(160deg, rgba(26,122,74,.12), rgba(13,26,18,.5));
    border: 1px solid rgba(76,202,131,.2);
    border-radius: 32px;
    padding: 28px 20px;
    box-shadow:
      0 40px 80px rgba(0,0,0,.5),
      inset 0 1px 0 rgba(255,255,255,.08);
    position: relative;
    overflow: hidden;
  }

  .phone-mockup::before {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(180deg, rgba(76,202,131,.05) 0%, transparent 40%);
    border-radius: 32px;
    pointer-events: none;
  }

  .mock-row {
    display: flex; align-items: center; justify-content: space-between;
    margin-bottom: 14px;
  }

  .mock-label {
    font-size: .72rem;
    font-weight: 600;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: rgba(232,240,235,.45);
  }

  .mock-value {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--green-light);
  }

  .mock-bar {
    height: 6px;
    background: rgba(255,255,255,.07);
    border-radius: 6px;
    margin-bottom: 18px;
    overflow: hidden;
  }
  .mock-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--green), var(--green-light));
    border-radius: 6px;
    animation: barLoad 2.5s ease infinite;
  }

  @keyframes barLoad {
    0%   { width: 20%; }
    60%  { width: 82%; }
    100% { width: 82%; }
  }

  .mock-result {
    background: rgba(26,122,74,.2);
    border: 1px solid rgba(76,202,131,.2);
    border-radius: 14px;
    padding: 16px;
    margin-top: 10px;
  }

  .mock-result-title {
    font-size: .7rem;
    font-weight: 600;
    letter-spacing: .12em;
    text-transform: uppercase;
    color: var(--green-light);
    margin-bottom: 10px;
  }

  .mock-result-line {
    display: flex; justify-content: space-between;
    font-size: .82rem;
    color: rgba(232,240,235,.7);
    padding: 5px 0;
    border-bottom: 1px solid rgba(255,255,255,.05);
  }
  .mock-result-line:last-child { border-bottom: none; font-weight: 700; color: #fff; }

  /* ── ENTREPRENEUR HOOK ───────────────────────────────────── */
  .hook-section {
    background: linear-gradient(135deg, rgba(26,122,74,.15), rgba(13,26,18,.8));
    border: 1px solid rgba(76,202,131,.15);
    border-radius: 28px;
    padding: 72px 48px;
    text-align: center;
    position: relative;
    overflow: hidden;
    max-width: 1100px;
    margin: 0 auto 96px;
  }

  .hook-section::before {
    content: '';
    position: absolute;
    top: -60px; left: 50%; transform: translateX(-50%);
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(76,202,131,.12) 0%, transparent 65%);
    border-radius: 50%;
    pointer-events: none;
  }

  .hook-eyebrow {
    font-size: .75rem;
    font-weight: 700;
    letter-spacing: .22em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
    position: relative; z-index: 1;
  }

  .hook-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 5vw, 3.8rem);
    font-weight: 900;
    line-height: 1.1;
    max-width: 780px;
    margin: 0 auto 24px;
    position: relative; z-index: 1;
  }

  .hook-title .hl {
    background: linear-gradient(90deg, var(--green-light), var(--gold));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hook-sub {
    font-size: 1.05rem;
    font-weight: 300;
    color: rgba(232,240,235,.6);
    max-width: 540px;
    margin: 0 auto 40px;
    line-height: 1.75;
    position: relative; z-index: 1;
  }

  .hook-pills {
    display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;
    margin-bottom: 44px;
    position: relative; z-index: 1;
  }

  .pill {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 8px 18px;
    border-radius: 50px;
    font-size: .82rem;
    font-weight: 500;
  }

  .pill-green {
    background: rgba(26,122,74,.3);
    border: 1px solid rgba(76,202,131,.25);
    color: var(--green-light);
  }

  .pill-gold {
    background: rgba(212,168,67,.12);
    border: 1px solid rgba(212,168,67,.25);
    color: var(--gold);
  }

  /* ── AUTHORITY BAR ───────────────────────────────────────── */
  .authority-bar {
    display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;
    padding: 36px 24px;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    background: rgba(255,255,255,.02);
    margin: 0 0 96px;
  }

  .auth-item {
    display: flex; align-items: center; gap: 10px;
    font-size: .88rem;
    color: rgba(232,240,235,.5);
    font-weight: 500;
  }

  .auth-dot {
    width: 8px; height: 8px;
    background: var(--green-mid);
    border-radius: 50%;
    box-shadow: 0 0 8px var(--green-mid);
  }

  /* ── FOOTER ──────────────────────────────────────────────── */
  footer {
    text-align: center;
    padding: 40px 24px;
    font-size: .8rem;
    color: rgba(232,240,235,.3);
    border-top: 1px solid var(--border);
  }

  /* ── UTILITIES ───────────────────────────────────────────── */
  .mt-0 { margin-top: 0 !important; }
  .center { text-align: center; }
  .mx-auto { margin-left: auto; margin-right: auto; }

  @media (max-width: 600px) {
    .hook-section { padding: 48px 24px; }
    .stat-item { flex: 1 1 120px; }
  }
</style>
</head>
<body>

<!-- ═══ HERO ═══════════════════════════════════════════════ -->
<div class="hero">
  <div class="hero-badge">Now Live · Egyptian Customs Simulation</div>

  <h1 class="hero-title">
    Stop Guessing<br>
    Your <span class="accent">Import Duties</span><br>
    <span class="gold">Before You Pay Them.</span>
  </h1>

  <p class="hero-sub">
    The Customs Intelligence Portal gives Egyptian importers and entrepreneurs
    instant, AI-powered duty estimates — before a single shipment clears port.
  </p>

  <div class="hero-cta-row">
    <a href="#" class="btn-primary">Try the Calculator →</a>
    <a href="#features" class="btn-ghost">See How It Works</a>
  </div>

  <div class="stats-bar">
    <div class="stat-item">
      <div class="stat-num">3s</div>
      <div class="stat-label">Duty Estimate</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">100%</div>
      <div class="stat-label">Nafeza Aligned</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">EGP</div>
      <div class="stat-label">Live FX Rates</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">0 EGP</div>
      <div class="stat-label">To Get Started</div>
    </div>
  </div>
</div>

<!-- ═══ AUTHORITY ═══════════════════════════════════════════ -->
<div class="authority-bar">
  <div class="auth-item"><span class="auth-dot"></span>Synced with Nafeza Smart Gateway</div>
  <div class="auth-item"><span class="auth-dot"></span>Egyptian Customs Authority Standards</div>
  <div class="auth-item"><span class="auth-dot"></span>CIF-Based Tariff Calculation</div>
  <div class="auth-item"><span class="auth-dot"></span>Multi-Currency with Live EGP Rates</div>
</div>

<!-- ═══ FEATURES ════════════════════════════════════════════ -->
<section id="features">
  <div class="section-label">Core Features</div>
  <h2 class="section-title">Everything a serious importer needs — in one place.</h2>
  <p class="section-body">
    Designed for Egypt's Nafeza ecosystem, the portal handles every variable
    that affects what you actually owe at customs clearance.
  </p>

  <div class="features-grid">
    <div class="feat-card">
      <div class="feat-icon">🧮</div>
      <div class="feat-title">Instant Duty Calculator</div>
      <div class="feat-desc">Enter FOB value, freight, and insurance — get your full CIF-based customs duty in seconds, not days.</div>
    </div>
    <div class="feat-card">
      <div class="feat-icon">💱</div>
      <div class="feat-title">Live EGP Exchange Rates</div>
      <div class="feat-desc">Supports USD, EUR, CNY and more. Real-time EGP conversion baked directly into every calculation.</div>
    </div>
    <div class="feat-card">
      <div class="feat-icon">📦</div>
      <div class="feat-title">Smart Tariff Classification</div>
      <div class="feat-desc">Select your tariff group — from standard goods to specialized medical equipment — for accurate rate application.</div>
    </div>
    <div class="feat-card">
      <div class="feat-icon">🔗</div>
      <div class="feat-title">Nafeza-Aligned Logic</div>
      <div class="feat-desc">Built on Egypt's official Smart Nafeza gateway rules so simulation results match real-world clearance expectations.</div>
    </div>
    <div class="feat-card">
      <div class="feat-icon">📝</div>
      <div class="feat-title">Shipment Declaration Form</div>
      <div class="feat-desc">A clean, guided form walks you through cargo description, valuation, and all required customs fields.</div>
    </div>
    <div class="feat-card">
      <div class="feat-icon">🛡️</div>
      <div class="feat-title">Authority-Grade Accuracy</div>
      <div class="feat-desc">Modeled on Egyptian Customs Authority standards — trustworthy enough to inform real procurement decisions.</div>
    </div>
  </div>
</section>

<!-- ═══ HOW IT WORKS ════════════════════════════════════════ -->
<section>
  <div class="how-wrapper">
    <div>
      <div class="section-label">How It Works</div>
      <h2 class="section-title">From cargo description to duty estimate — in 4 steps.</h2>

      <ul class="steps-list" style="margin-top:36px">
        <li class="step-item">
          <div class="step-num">1</div>
          <div class="step-body">
            <h4>Describe Your Cargo</h4>
            <p>Enter a plain-language description of the goods you're importing — the AI handles classification hints.</p>
          </div>
        </li>
        <li class="step-item">
          <div class="step-num">2</div>
          <div class="step-body">
            <h4>Set Your Values</h4>
            <p>Input FOB value in your preferred currency, plus freight and insurance costs for full CIF computation.</p>
          </div>
        </li>
        <li class="step-item">
          <div class="step-num">3</div>
          <div class="step-body">
            <h4>Select Tariff Group</h4>
            <p>Choose the appropriate tariff group — Standard, Medical, Industrial, or more — for your commodity.</p>
          </div>
        </li>
        <li class="step-item">
          <div class="step-num">4</div>
          <div class="step-body">
            <h4>Get Your Duty Report</h4>
            <p>Receive a full breakdown: customs duty, VAT, and any additional levies — in EGP, instantly.</p>
          </div>
        </li>
      </ul>
    </div>

    <!-- phone mockup -->
    <div class="phone-mockup">
      <div class="mock-row">
        <span class="mock-label">Shipment ID #EG-2026</span>
        <span style="font-size:.75rem;color:var(--green-light);font-weight:600;">● Live</span>
      </div>

      <div class="mock-row">
        <span class="mock-label">FOB Value</span>
        <span class="mock-value">$48,000</span>
      </div>
      <div class="mock-bar"><div class="mock-bar-fill" style="width:82%"></div></div>

      <div class="mock-row">
        <span class="mock-label">CIF (EGP)</span>
        <span class="mock-value">2,475,600</span>
      </div>
      <div class="mock-bar"><d
