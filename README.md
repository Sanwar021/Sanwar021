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
  .top-label::before { content: ''; flex: 1; height: 1px; background: linear-gradient(90deg, transparent, var(--border)); }
  .top-label::after  { content: ''; flex: 1; height: 1px; background: linear-gradient(90deg, var(--border), transparent); }

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

  .titlebar {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 14px 20px;
    background: var(--panel);
    border-bottom: 1px solid var(--border);
  }
  .dots { display: flex; gap: 7px; }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ef4444; box-shadow: 0 0 6px #ef444455; }
  .dot-y { background: #f59e0b; box-shadow: 0 0 6px #f59e0b55; }
  .dot-g { background: #22c55e; box-shadow: 0 0 6px #22c55e55; }

  .titlebar-file { font-size: 12px; color: var(--muted); margin-left: 6px; letter-spacing: 0.04em; }
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
  .tab.active { color: var(--accent); border-bottom-color: var(--accent); }

  .code-body { display: flex; padding: 28px 0; }

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

  .ln {
    display: block;
    padding: 0 4px;
    border-radius: 4px;
    transition: background 0.15s;
    white-space: pre;
  }
  .ln:hover { background: rgba(249,115,22,0.05); }
  .ln.highlight {
    background: rgba(168,85,247,0.07);
    border-left: 2px solid var(--accent2);
    padding-left: 2px;
  }

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
  .output-text { font-size: 13px; color: var(--string); }
  .output-text .rocket {
    display: inline-block;
    animation: rocketBounce 2s ease-in-out infinite;
  }
  @keyframes rocketBounce {
    0%,100%{ transform: translateY(0) rotate(-45deg); }
    50%    { transform: translateY(-4px) rotate(-45deg); }
  }

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
  .stat-label { font-size: 11px; color: var(--muted); letter-spacing: 0.08em; text-transform: uppercase; }
  .stat-icon {
    position: absolute;
    right: 16px; top: 50%;
    transform: translateY(-50%);
    font-size: 26px;
    opacity: 0.18;
  }

  .bottom-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 20px;
    padding: 0 4px;
    animation: fadeUp 0.6s 0.25s ease both;
  }
  .bottom-bar .quote { font-size: 11px; color: var(--muted); font-style: italic; letter-spacing: 0.03em; }
  .bottom-bar .quote em { color: var(--accent); font-style: normal; }
  .status-dot { display: flex; align-items: center; gap: 7px; font-size: 11px; color: #22c55e; }
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

    <div class="titlebar">
      <div class="dots">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
      </div>
      <span class="titlebar-file"><span>sanwar</span>.py</span>
      <span class="titlebar-badge">Python 3.12</span>
    </div>

    <div class="tabbar">
      <div class="tab active">sanwar.py</div>
      <div class="tab">research.md</div>
      <div class="tab">stack.json</div>
    </div>

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

    <div class="output-panel">
      <span class="output-label">▶ Output</span>
      <span class="output-text">Let's collaborate and build something impactful! <span class="rocket">🚀</span></span>
    </div>

  </div>

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

  <div class="bottom-bar">
    <div class="quote">"In God we trust. All others must <em>bring data</em>." — Deming</div>
    <div class="status-dot">available</div>
  </div>

</div>
</body>
</html>
