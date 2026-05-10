<div align="center">

<!-- HEADER -->
[![header](https://capsule-render.vercel.app/api?type=venom&color=0:0a0a0f,40:0d0d2b,70:1a0533,100:0a0a0f&height=200§ion=header&text=SANWAR%20ISLAM&fontSize=56&fontColor=FF7B00&animation=twinkling&fontAlignY=40&stroke=A855F7&strokeWidth=3&desc=Data%20Scientist%20%E2%80%A2%20Web%20Developer%20%E2%80%A2%20Researcher&descAlignY=62&descSize=18&descColor=C084FC)](https://github.com/Sanwar021)

<!-- SOCIAL BADGES -->
[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-sanwarul--ai--folio-FF7B00?style=for-the-badge&logoColor=white)](https://sanwar-islam.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sanwarislam17/)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-4285F4?style=for-the-badge&logo=google-scholar&logoColor=white)](https://scholar.google.com/citations?user=eqFfAEMAAAAJ&hl=en&oi=ao)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/sanwar.islam.2024/)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/mr.raw420_/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sanwar021)

![Profile views](https://komarev.com/ghpvc/?username=Sanwar021&label=Profile+Views&color=A855F7&style=for-the-badge)

</div>

---

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Sanwar Islam — whoami</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #080b14;
    --surface:   #0d1220;
    --panel:     #111827;
    --border:    #1e2d45;
    --accent:    #f97316;
    --accent2:   #a855f7;
    --accent3:   #22d3ee;
    --text:      #e2e8f0;
    --muted:     #64748b;
    --keyword:   #f97316;
    --string:    #86efac;
    --comment:   #4b5563;
    --attr:      #7dd3fc;
    --value:     #c4b5fd;
    --fn:        #fbbf24;
    --number:    #f472b6;
  }

  body {
    background: var(--bg);
    font-family: 'JetBrains Mono', monospace;
    color: var(--text);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 40px 20px;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(249,115,22,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(249,115,22,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* Glow orbs */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(120px);
    opacity: 0.15;
    pointer-events: none;
    z-index: 0;
    animation: drift 12s ease-in-out infinite alternate;
  }
  .orb-1 { width: 600px; height: 600px; background: var(--accent2); top: -200px; right: -150px; animation-delay: 0s; }
  .orb-2 { width: 500px; height: 500px; background: var(--accent); bottom: -150px; left: -100px; animation-delay: -4s; }
  .orb-3 { width: 300px; height: 300px; background: var(--accent3); top: 40%; left: 40%; animation-delay: -8s; }

  @keyframes drift {
    from { transform: translate(0, 0) scale(1); }
    to   { transform: translate(30px, 20px) scale(1.05); }
  }

  .wrapper {
    position: relative;
    z-index: 1;
    width: 100%;
    max-width: 860px;
  }

  /* ── Top label ── */
  .top-label {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 20px;
    font-family: 'Syne', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
  }
  .top-label::before, .top-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border));
  }
  .top-label::before { background: linear-gradient(90deg, transparent, var(--border)); }
  .top-label::after  { background: linear-gradient(90deg, var(--border), transparent); }

  /* ── Editor card ── */
  .editor {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
    box-shadow:
      0 0 0 1px rgba(168,85,247,0.08),
      0 25px 60px rgba(0,0,0,0.6),
      0 0 80px rgba(249,115,22,0.05);
    animation: fadeUp 0.6s ease both;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ── Title bar ── */
  .titlebar {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 14px 20px;
    background: var(--panel);
    border-bottom: 1px solid var(--border);
  }
  .dots { display: flex; gap: 7px; }
  .dot {
    width: 12px; height: 12px;
    border-radius: 50%;
  }
  .dot-r { background: #ef4444; box-shadow: 0 0 6px #ef444455; }
  .dot-y { background: #f59e0b; box-shadow: 0 0 6px #f59e0b55; }
  .dot-g { background: #22c55e; box-shadow: 0 0 6px #22c55e55; }

  .titlebar-file {
    font-size: 12px;
    color: var(--muted);
    margin-left: 6px;
    letter-spacing: 0.04em;
  }
  .titlebar-file span { color: var(--accent); }

  .titlebar-badge {
    margin-left: auto;
    padding: 3px 10px;
    background: rgba(249,115,22,0.1);
    border: 1px solid rgba(249,115,22,0.25);
    border-radius: 20px;
    font-size: 10px;
    color: var(--accent);
    letter-spacing: 0.08em;
    font-weight: 600;
  }

  /* ── Tab bar ── */
  .tabbar {
    display: flex;
    background: var(--panel);
    border-bottom: 1px solid var(--border);
    padding: 0 20px;
    gap: 2px;
  }
  .tab {
    padding: 8px 18px;
    font-size: 11.5px;
    color: var(--muted);
    border-bottom: 2px solid transparent;
    cursor: default;
    transition: color 0.2s;
    letter-spacing: 0.03em;
  }
  .tab.active {
    color: var(--accent);
    border-bottom-color: var(--accent);
  }

  /* ── Code body ── */
  .code-body {
    display: flex;
    padding: 28px 0;
  }

  .line-nums {
    padding: 0 16px 0 20px;
    color: var(--comment);
    font-size: 13px;
    line-height: 1.95;
    text-align: right;
    user-select: none;
    border-right: 1px solid var(--border);
    min-width: 52px;
  }

  .code-content {
    padding: 0 28px;
    font-size: 13.5px;
    line-height: 1.95;
    overflow-x: auto;
    flex: 1;
  }

  /* Syntax highlighting */
  .kw  { color: var(--keyword); font-weight: 600; }
  .fn  { color: var(--fn); }
  .cls { color: var(--accent3); font-weight: 600; }
  .attr{ color: var(--attr); }
  .str { color: var(--string); }
  .num { color: var(--number); }
  .cmt { color: var(--comment); font-style: italic; }
  .pun { color: var(--muted); }
  .val { color: var(--value); }
  .self{ color: #fb923c; }
  .op  { color: #94a3b8; }

  /* Hover-highlight rows */
  .ln {
    display: block;
    padding: 0 4px;
    border-radius: 4px;
    transition: background 0.15s;
    white-space: pre;
  }
  .ln:hover { background: rgba(249,115,22,0.05); }

  /* Active line glow */
  .ln.highlight {
    background: rgba(168,85,247,0.07);
    border-left: 2px solid var(--accent2);
    padding-left: 2px;
  }

  /* Cursor blink */
  .cursor {
    display: inline-block;
    width: 2px;
    height: 1em;
    background: var(--accent);
    vertical-align: text-bottom;
    animation: blink 1.1s step-end infinite;
    border-radius: 1px;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* ── Output panel ── */
  .output-panel {
    border-top: 1px solid var(--border);
    padding: 16px 24px;
    background: rgba(0,0,0,0.25);
    display: flex;
    align-items: center;
    gap: 14px;
  }
  .output-label {
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    font-family: 'Syne', sans-serif;
  }
  .output-text {
    font-size: 13px;
    color: var(--string);
  }
  .output-text .rocket {
    display: inline-block;
    animation: rocketBounce 2s ease-in-out infinite;
  }
  @keyframes rocketBounce {
    0%,100%{ transform: translateY(0) rotate(-45deg); }
    50%    { transform: translateY(-4px) rotate(-45deg); }
  }

  /* ── Stats row ── */
  .stats-row {
    display: flex;
    gap: 12px;
    margin-top: 20px;
    flex-wrap: wrap;
    animation: fadeUp 0.6s 0.15s ease both;
  }
  .stat-card {
    flex: 1;
    min-width: 160px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    display: flex;
    flex-direction: column;
    gap: 4px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s, transform 0.2s;
  }
  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
  }
  .stat-card:nth-child(1)::before { background: linear-gradient(90deg, var(--accent), transparent); }
  .stat-card:nth-child(2)::before { background: linear-gradient(90deg, var(--accent2), transparent); }
  .stat-card:nth-child(3)::before { background: linear-gradient(90deg, var(--accent3), transparent); }
  .stat-card:hover { border-color: var(--accent); transform: translateY(-2px); }

  .stat-value {
    font-family: 'Syne', sans-serif;
    font-size: 28px;
    font-weight: 800;
    color: var(--text);
    line-height: 1;
  }
  .stat-value span { font-size: 14px; font-weight: 600; color: var(--muted); }
  .stat-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }
  .stat-icon {
    position: absolute;
    right: 16px; top: 50%;
    transform: translateY(-50%);
    font-size: 26px;
    opacity: 0.18;
  }

  /* ── Bottom label ── */
  .bottom-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 20px;
    padding: 0 4px;
    animation: fadeUp 0.6s 0.25s ease both;
  }
  .bottom-bar .quote {
    font-size: 11px;
    color: var(--muted);
    font-style: italic;
    letter-spacing: 0.03em;
  }
  .bottom-bar .quote em { color: var(--accent); font-style: normal; }
  .status-dot {
    display: flex;
    align-items: center;
    gap: 7px;
    font-size: 11px;
    color: #22c55e;
  }
  .status-dot::before {
    content: '';
    display: inline-block;
    width: 8px; height: 8px;
    background: #22c55e;
    border-radius: 50%;
    box-shadow: 0 0 8px #22c55e;
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1;box-shadow:0 0 8px #22c55e} 50%{opacity:0.6;box-shadow:0 0 16px #22c55e} }

  /* ── Scrollbar ── */
  ::-webkit-scrollbar { width: 4px; height: 4px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 4px; }

  @media (max-width: 600px) {
    .code-content { font-size: 11.5px; padding: 0 16px; }
    .stat-value { font-size: 22px; }
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="wrapper">

  <div class="top-label">👋 &nbsp; whoami</div>

  <div class="editor">

    <!-- Title bar -->
    <div class="titlebar">
      <div class="dots">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
      </div>
      <span class="titlebar-file"><span>sanwar</span>.py</span>
      <span class="titlebar-badge">Python 3.12</span>
    </div>

    <!-- Tab bar -->
    <div class="tabbar">
      <div class="tab active">sanwar.py</div>
      <div class="tab">research.md</div>
      <div class="tab">stack.json</div>
    </div>

    <!-- Code -->
    <div class="code-body">
      <div class="line-nums">
1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br>11<br>12<br>13<br>14<br>15<br>16<br>17<br>18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29
      </div>
      <div class="code-content">
<span class="ln"><span class="kw">class</span> <span class="cls">SanwarIslam</span><span class="pun">:</span></span>
<span class="ln">    <span class="kw">def</span> <span class="fn">__init__</span><span class="pun">(</span><span class="self">self</span><span class="pun">):</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">name</span>        <span class="op">=</span> <span class="str">"Sanwar Islam"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">alias</span>       <span class="op">=</span> <span class="str">"Sanwar021"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">location</span>    <span class="op">=</span> <span class="str">"Dhaka, Bangladesh 🇧🇩"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">title</span>       <span class="op">=</span> <span class="str">"Software Engineer | Data Scientist | CSE Graduate"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">university</span>  <span class="op">=</span> <span class="str">"East West University"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">email</span>       <span class="op">=</span> <span class="str">"std.ewubd.edu (verified)"</span></span>
<span class="ln highlight">        <span class="self">self</span><span class="op">.</span><span class="attr">roles</span>       <span class="op">=</span> <span class="pun">[</span><span class="str">"Data Scientist"</span><span class="pun">,</span> <span class="str">"Web Developer"</span><span class="pun">,</span> <span class="str">"Researcher"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">research</span>    <span class="op">=</span> <span class="pun">[</span><span class="str">"ML &amp; DL"</span><span class="pun">,</span> <span class="str">"Data Mining"</span><span class="pun">,</span> <span class="str">"AI"</span><span class="pun">,</span> <span class="str">"Software Development"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">frontend</span>    <span class="op">=</span> <span class="pun">[</span><span class="str">"React"</span><span class="pun">,</span> <span class="str">"Vite"</span><span class="pun">,</span> <span class="str">"JavaScript"</span><span class="pun">,</span> <span class="str">"HTML5"</span><span class="pun">,</span> <span class="str">"CSS3"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">backend</span>     <span class="op">=</span> <span class="pun">[</span><span class="str">"Go (Chi Router)"</span><span class="pun">,</span> <span class="str">"REST APIs"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">database</span>    <span class="op">=</span> <span class="pun">[</span><span class="str">"PostgreSQL"</span><span class="pun">,</span> <span class="str">"MySQL"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">building</span>    <span class="op">=</span> <span class="str">"Upasham Prescription 💊 (React + Go + PostgreSQL)"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">portfolio</span>   <span class="op">=</span> <span class="str">"https://sanwarul-ai-folio.vercel.app/"</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">hobbies</span>     <span class="op">=</span> <span class="pun">[</span><span class="str">"Research 🔬"</span><span class="pun">,</span> <span class="str">"Gaming 🎮"</span><span class="pun">,</span> <span class="str">"Open Source"</span><span class="pun">,</span> <span class="str">"Coffee ☕"</span><span class="pun">]</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">papers</span>      <span class="op">=</span> <span class="num">9</span>    <span class="cmt"># Google Scholar publications</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">citations</span>   <span class="op">=</span> <span class="num">3</span>    <span class="cmt"># and counting...</span></span>
<span class="ln">        <span class="self">self</span><span class="op">.</span><span class="attr">available</span>   <span class="op">=</span> <span class="val">True</span></span>
<span class="ln"> </span>
<span class="ln">    <span class="kw">def</span> <span class="fn">say_hi</span><span class="pun">(</span><span class="self">self</span><span class="pun">):</span></span>
<span class="ln">        <span class="fn">print</span><span class="pun">(</span><span class="str">"Let's collaborate and build something impactful! 🚀"</span><span class="pun">)</span></span>
<span class="ln"> </span>
<span class="ln"> </span>
<span class="ln"><span class="attr">me</span> <span class="op">=</span> <span class="cls">SanwarIslam</span><span class="pun">()</span></span>
<span class="ln"><span class="attr">me</span><span class="op">.</span><span class="fn">say_hi</span><span class="pun">()</span><span class="cursor"></span></span>
      </div>
    </div>

    <!-- Output -->
    <div class="output-panel">
      <span class="output-label">▶ Output</span>
      <span class="output-text">Let's collaborate and build something impactful! <span class="rocket">🚀</span></span>
    </div>

  </div><!-- /editor -->

  <!-- Stats row -->
  <div class="stats-row">
    <div class="stat-card">
      <div class="stat-value">9 <span>papers</span></div>
      <div class="stat-label">Google Scholar Publications</div>
      <div class="stat-icon">📄</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">3 <span>cites</span></div>
      <div class="stat-label">Citations &amp; counting</div>
      <div class="stat-icon">🔗</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">✓ <span>open</span></div>
      <div class="stat-label">Available for Collaboration</div>
      <div class="stat-icon">🤝</div>
    </div>
  </div>

  <!-- Bottom bar -->
  <div class="bottom-bar">
    <div class="quote">"In God we trust. All others must <em>bring data</em>." — Deming</div>
    <div class="status-dot">available</div>
  </div>

</div><!-- /wrapper -->
</body>
</html>

<!-- GITHUB STATS -->
## 📊 `git log --stats`

<div align="center">

<img height="175" src="https://github-readme-stats.vercel.app/api?username=Sanwar021&show_icons=true&count_private=true&theme=midnight-purple&hide_border=true&bg_color=0D0D18&title_color=FF7B00&icon_color=A855F7&text_color=C084FC&ring_color=A855F7" />

<br/><br/>

<img width="500" src="https://github-readme-streak-stats.herokuapp.com/?user=Sanwar021&theme=midnight-purple&hide_border=true&background=0D0D18&stroke=A855F7&ring=FF7B00&fire=EC4899&currStreakLabel=FF7B00&sideLabels=C084FC&dates=6B6B8A&sideNums=FF7B00" />

</div>

---

<!-- TECH STACK -->
## ⚡ `tech_stack --list`

**🧠 Data Science & AI**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)

**🖥️ Web Development**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)

**🛠️ Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Google Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)

---

<!-- RESEARCH PAPERS -->
## 🔬 `research --papers --all`

> 📚 **9 Publications** on [Google Scholar](https://scholar.google.com/citations?user=eqFfAEMAAAAJ&hl=en&oi=ao) · East West University · Verified researcher

| # | 📄 Title | 🏷️ Area | 📅 Year | 🔢 Cited |
|---|---------|---------|---------|---------|
| 1 | [Measuring Accuracy of Different ML Algorithms on Expectations and Experiences of University Students](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Machine Learning | 2025 | 1 |
| 2 | [Earthquake Magnitude Prediction: A Survey on ML Models, Datasets, Techniques, Challenges, and Future Directions](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Deep Learning | 2024 | 1 |
| 3 | [Detection of Sugarcane Leaf Diseases Using Custom CNN and ResNet50](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Computer Vision | 2024 | 1 |
| 4 | [Prediction of Glioblastoma Using (Data Mining & AI)](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Medical AI | 2025 | — |
| 5 | [Deep Learning-Based Classification of Coconut Leaf Diseases Using Optimized CNN Models](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Deep Learning | 2025 | — |
| 6 | [Green Machine Learning (GML): Energy-Aware Approaches for Sustainable Computing](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Sustainable AI | 2025 | — |
| 7 | [Detection of Lemon Leaf Diseases Using Inception V3-Based Machine Learning Model](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Computer Vision | 2025 | — |
| 8 | [Forecasting Air Quality: A Comprehensive Survey of Air Pollution Prediction Methods and Applications](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Data Science | 2025 | — |
| 9 | [Prediction of Glioblastoma Using 3D-CNN](https://scholar.google.com/citations?user=eqFfAEMAAAAJ) | Medical AI | 2024 | — |

> 🏛️ Published in: *International Conference on Quantum Photonics & AI*, *ICIDA*, *ICDMIS*, *ICCIIT*

---

<!-- ACTIVITY GRAPH -->
## 📈 `git log --graph --all`

<div align="center">

[![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=Sanwar021&bg_color=0D0D18&color=FF7B00&line=A855F7&point=EC4899&area=true&area_color=1a0533&hide_border=true&custom_title=Sanwar's%20Contribution%20Graph)](https://github.com/ashutosh00710/github-readme-activity-graph)

</div>

---

<!-- TROPHIES -->
## 🏆 `achievements --unlock`

<div align="center">

[![Trophies](https://github-profile-trophy.vercel.app/?username=Sanwar021&theme=darkhub&no-frame=true&no-bg=true&margin-w=8&column=7)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

<!-- SNAKE -->
## 🐍 `contribution_snake --dark`

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)"  srcset="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake-dark.svg"/>
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake.svg"/>
  <img alt="snake animation" src="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake.svg"/>
</picture>

</div>

---

<!-- CONNECT -->
## 📡 `connect --all`

<div align="center">

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-sanwarul--ai--folio-FF7B00?style=for-the-badge&logoColor=white)](https://sanwar-islam.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sanwarislam17/)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-4285F4?style=for-the-badge&logo=google-scholar&logoColor=white)](https://scholar.google.com/citations?user=eqFfAEMAAAAJ&hl=en&oi=ao)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/sanwar.islam.2024/)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/mr.raw420_/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sanwar021)

<br/>

![Profile views](https://komarev.com/ghpvc/?username=Sanwar021&label=Profile+Views&color=A855F7&style=for-the-badge)

<br/>

> *"In God we trust. All others must bring data."* — W. Edwards Deming

</div>

<br/>

[![footer](https://capsule-render.vercel.app/api?type=venom&color=0:0a0a0f,40:0d0d2b,70:1a0533,100:0a0a0f&height=130§ion=footer&animation=twinkling&stroke=A855F7&strokeWidth=1)](https://github.com/Sanwar021)
