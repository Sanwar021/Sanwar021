<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sanwar Islam — Identity</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@300;400;500;700&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --orange: #F97316;
    --orange-dim: #c2570e;
    --violet: #8B5CF6;
    --violet-dim: #5b359e;
    --bg: #06060f;
    --surface: #0d0d1c;
    --surface2: #13132a;
    --border: rgba(139,92,246,0.18);
    --border-o: rgba(249,115,22,0.22);
    --text: #e8e4f0;
    --muted: #7a7490;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'Space Grotesk', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    position: relative;
  }

  /* Ambient orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    animation: drift 12s ease-in-out infinite alternate;
  }
  .orb-1 {
    width: 520px; height: 520px;
    background: radial-gradient(circle, rgba(139,92,246,0.14) 0%, transparent 70%);
    top: -160px; left: -120px;
    animation-delay: 0s;
  }
  .orb-2 {
    width: 400px; height: 400px;
    background: radial-gradient(circle, rgba(249,115,22,0.12) 0%, transparent 70%);
    bottom: -100px; right: -80px;
    animation-delay: -6s;
  }
  .orb-3 {
    width: 280px; height: 280px;
    background: radial-gradient(circle, rgba(139,92,246,0.08) 0%, transparent 70%);
    top: 40%; left: 60%;
    animation-delay: -3s;
  }

  @keyframes drift {
    from { transform: translate(0, 0) scale(1); }
    to   { transform: translate(30px, 20px) scale(1.06); }
  }

  /* Grid noise texture */
  body::before {
    content: '';
    position: fixed; inset: 0;
    background-image:
      linear-gradient(rgba(139,92,246,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(139,92,246,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* Card */
  .card {
    position: relative;
    z-index: 10;
    width: min(780px, 96vw);
    background: rgba(13,13,28,0.82);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 48px 52px;
    backdrop-filter: blur(24px);
    -webkit-backdrop-filter: blur(24px);
    box-shadow:
      0 0 0 1px rgba(249,115,22,0.06),
      0 24px 80px rgba(0,0,0,0.6),
      inset 0 1px 0 rgba(255,255,255,0.05);
    opacity: 0;
    transform: translateY(28px);
    animation: fadeUp 0.9s cubic-bezier(0.16,1,0.3,1) 0.2s forwards;
  }

  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }

  /* Top accent line */
  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 12%; right: 12%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--orange), var(--violet), transparent);
    border-radius: 1px;
    opacity: 0.7;
  }

  /* Header */
  .header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 36px;
    opacity: 0;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) 0.5s forwards;
  }

  .name-block {}

  .name-tag {
    font-size: 11px;
    font-family: var(--mono);
    letter-spacing: 0.18em;
    color: var(--orange);
    text-transform: uppercase;
    margin-bottom: 6px;
    opacity: 0.8;
  }

  .name {
    font-size: 32px;
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1;
    background: linear-gradient(135deg, #fff 0%, #c8b8f0 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .alias {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--muted);
    margin-top: 4px;
  }
  .alias span { color: var(--violet); }

  .location-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(139,92,246,0.08);
    border: 1px solid rgba(139,92,246,0.2);
    border-radius: 100px;
    padding: 8px 16px;
    font-size: 13px;
    font-family: var(--mono);
    color: var(--muted);
  }
  .location-badge .flag { font-size: 16px; }
  .location-badge strong { color: var(--text); font-weight: 500; }

  /* Divider */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), var(--border-o), var(--border), transparent);
    margin: 28px 0;
  }

  /* Info grid */
  .info-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px 32px;
    opacity: 0;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) 0.7s forwards;
  }

  .info-row {
    display: flex;
    flex-direction: column;
    gap: 3px;
  }

  .info-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--orange);
    opacity: 0.7;
  }

  .info-value {
    font-size: 14px;
    color: var(--text);
    font-weight: 400;
    line-height: 1.5;
  }

  .info-value .dot {
    color: var(--violet);
    margin: 0 4px;
    opacity: 0.6;
  }

  .info-value a {
    color: var(--violet);
    text-decoration: none;
    font-family: var(--mono);
    font-size: 13px;
  }
  .info-value a:hover { color: var(--orange); }

  /* Stats row */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-top: 28px;
    opacity: 0;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) 0.9s forwards;
  }

  .stat-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px 18px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, background 0.3s;
  }
  .stat-card:hover {
    border-color: rgba(249,115,22,0.3);
    background: rgba(249,115,22,0.04);
  }
  .stat-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.08), transparent);
  }

  .stat-number {
    font-size: 26px;
    font-weight: 700;
    font-family: var(--mono);
    color: var(--orange);
    line-height: 1;
    margin-bottom: 4px;
  }
  .stat-number.violet { color: var(--violet); }

  .stat-label {
    font-size: 11px;
    font-family: var(--mono);
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  /* Award card */
  .award-card {
    margin-top: 28px;
    background: linear-gradient(135deg, rgba(249,115,22,0.07) 0%, rgba(139,92,246,0.07) 100%);
    border: 1px solid rgba(249,115,22,0.25);
    border-radius: 14px;
    padding: 18px 22px;
    display: flex;
    align-items: center;
    gap: 16px;
    opacity: 0;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) 1.0s forwards;
    position: relative;
    overflow: hidden;
  }

  .award-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, rgba(249,115,22,0.04), transparent);
    pointer-events: none;
  }

  .award-icon {
    font-size: 28px;
    flex-shrink: 0;
    filter: drop-shadow(0 0 8px rgba(249,115,22,0.5));
    animation: pulse 2.5s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { filter: drop-shadow(0 0 6px rgba(249,115,22,0.4)); }
    50%       { filter: drop-shadow(0 0 14px rgba(249,115,22,0.8)); }
  }

  .award-text {}
  .award-title {
    font-size: 13px;
    font-weight: 600;
    color: var(--orange);
    letter-spacing: 0.02em;
    margin-bottom: 2px;
  }
  .award-desc {
    font-size: 12px;
    color: var(--muted);
    font-family: var(--mono);
    line-height: 1.5;
  }
  .award-desc strong { color: var(--text); font-weight: 500; }

  .award-badge {
    margin-left: auto;
    background: rgba(249,115,22,0.12);
    border: 1px solid rgba(249,115,22,0.3);
    border-radius: 100px;
    padding: 4px 12px;
    font-size: 10px;
    font-family: var(--mono);
    color: var(--orange);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    white-space: nowrap;
    flex-shrink: 0;
  }

  /* Status footer */
  .status-footer {
    margin-top: 28px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    opacity: 0;
    animation: fadeUp 0.8s cubic-bezier(0.16,1,0.3,1) 1.1s forwards;
  }

  .status-pill {
    display: flex;
    align-items: center;
    gap: 8px;
    background: rgba(22,163,74,0.08);
    border: 1px solid rgba(22,163,74,0.25);
    border-radius: 100px;
    padding: 7px 16px;
    font-size: 12px;
    font-family: var(--mono);
    color: #4ade80;
  }

  .status-dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: #4ade80;
    box-shadow: 0 0 6px #4ade80;
    animation: blink 1.8s ease-in-out infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; box-shadow: 0 0 6px #4ade80; }
    50%       { opacity: 0.4; box-shadow: 0 0 2px #4ade80; }
  }

  .tagline {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--muted);
    font-style: italic;
  }
  .tagline span { color: var(--violet); opacity: 0.7; }

  /* Cursor blink on tagline end */
  .cursor {
    display: inline-block;
    width: 2px; height: 13px;
    background: var(--violet);
    margin-left: 2px;
    vertical-align: middle;
    animation: cursorBlink 1s step-end infinite;
  }
  @keyframes cursorBlink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  /* Scan line animation on hover */
  .card:hover::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 100%;
    background: linear-gradient(180deg, transparent 0%, rgba(139,92,246,0.025) 50%, transparent 100%);
    animation: scan 3s linear infinite;
    pointer-events: none;
    border-radius: 20px;
  }
  @keyframes scan {
    from { transform: translateY(-100%); }
    to   { transform: translateY(100%); }
  }

  @media (max-width: 560px) {
    .card { padding: 32px 24px; }
    .name { font-size: 24px; }
    .info-grid { grid-template-columns: 1fr; }
    .stats-row { grid-template-columns: 1fr 1fr; }
    .header { flex-direction: column; align-items: flex-start; gap: 16px; }
    .tagline { display: none; }
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="card">

  <div class="header">
    <div class="name-block">
      <div class="name-tag">// identity.json</div>
      <div class="name">Sanwar Islam</div>
      <div class="alias"><span>@</span>Sanwar021 &nbsp;·&nbsp; East West University</div>
    </div>
    <div class="location-badge">
      <span class="flag">🇧🇩</span>
      <span><strong>Dhaka</strong>, Bangladesh</span>
    </div>
  </div>

  <div class="divider"></div>

  <div class="info-grid">
    <div class="info-row">
      <div class="info-label">Speciality</div>
      <div class="info-value">ML Engineering<span class="dot">·</span>AI Research</div>
    </div>
    <div class="info-row">
      <div class="info-label">Research Focus</div>
      <div class="info-value">Computer Vision<span class="dot">·</span>Medical AI<span class="dot">·</span>DL</div>
    </div>
    <div class="info-row">
      <div class="info-label">Tech Stack</div>
      <div class="info-value">Python · TF · PyTorch · React · Go · PG</div>
    </div>
    <div class="info-row">
      <div class="info-label">Currently Building</div>
      <div class="info-value">Upasham Prescription <span style="color:var(--violet);opacity:0.7">[ React + Go + PG ]</span></div>
    </div>
    <div class="info-row">
      <div class="info-label">Portfolio</div>
      <div class="info-value"><a href="https://sanwarul-ai-folio.vercel.app/" target="_blank">sanwarul-ai-folio.vercel.app</a></div>
    </div>
    <div class="info-row">
      <div class="info-label">Google Scholar</div>
      <div class="info-value"><a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" target="_blank">eqFfAEMAAAAJ</a></div>
    </div>
  </div>

  <div class="divider"></div>

  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-number">9</div>
      <div class="stat-label">Publications</div>
    </div>
    <div class="stat-card">
      <div class="stat-number violet">3</div>
      <div class="stat-label">Citations & counting</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">2</div>
      <div class="stat-label">Best Paper Awards</div>
    </div>
  </div>

  <div class="award-card">
    <div class="award-icon">🏆</div>
    <div class="award-text">
      <div class="award-title">Springer ICDMIS 2024 — Best Paper Award</div>
      <div class="award-desc">
        <strong>"Prediction of Glioblastoma Using 3D-CNN"</strong> &nbsp;·&nbsp;
        Springer LNNS Series &nbsp;·&nbsp; SCOPUS indexed &nbsp;·&nbsp; EWU, Dept. of CSE
      </div>
    </div>
    <div class="award-badge">Verified ✓</div>
  </div>

  <div class="status-footer">
    <div class="status-pill">
      <div class="status-dot"></div>
      Available · Open to Remote ML / AI Roles
    </div>
    <div class="tagline">
      <span>></span> "Build something impactful — and publish it."<span class="cursor"></span>
    </div>
  </div>

</div>

</body>
</html>
