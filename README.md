<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sanwar Islam — ML Engineer & AI Researcher</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
/* ═══════════════════════════════════════════════
   DESIGN TOKENS
═══════════════════════════════════════════════ */
:root {
  --bg-base:       #060a10;
  --bg-surface:    #0a0f18;
  --bg-card:       #0e1520;
  --bg-hover:      #131c2b;
  --bg-glass:      rgba(14,21,32,0.7);
  --border:        rgba(255,255,255,0.055);
  --border-mid:    rgba(255,255,255,0.09);
  --border-hover:  rgba(99,179,237,0.3);
  --border-accent: rgba(99,179,237,0.15);
  --text-primary:  #e8eef4;
  --text-secondary:#7e8a96;
  --text-muted:    #3d4550;
  --accent:        #63b3ed;
  --accent-dim:    rgba(99,179,237,0.08);
  --accent-glow:   rgba(99,179,237,0.18);
  --teal:          #4fd1c5;
  --green:         #3fb950;
  --green-dim:     rgba(63,185,80,0.1);
  --orange:        #e8894a;
  --orange-dim:    rgba(232,137,74,0.1);
  --purple:        #a78bfa;
  --font-sans:     'Sora', sans-serif;
  --font-mono:     'JetBrains Mono', monospace;
  --r-sm: 6px; --r-md: 10px; --r-lg: 16px; --r-xl: 20px;
  --ease: cubic-bezier(0.4,0,0.2,1);
  --transition: all 0.24s var(--ease);
}

/* ═══ RESET ═══ */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
  font-family:var(--font-sans);
  background:var(--bg-base);
  color:var(--text-primary);
  line-height:1.6;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
}

/* ═══ AMBIENT BACKGROUND ═══ */
.bg-orb{
  position:fixed;pointer-events:none;z-index:0;
  border-radius:50%;filter:blur(80px);
}
.bg-orb-1{
  width:600px;height:500px;top:-100px;left:-200px;
  background:radial-gradient(ellipse,rgba(99,179,237,0.04) 0%,transparent 70%);
}
.bg-orb-2{
  width:500px;height:400px;bottom:10%;right:-150px;
  background:radial-gradient(ellipse,rgba(79,209,197,0.03) 0%,transparent 70%);
}
.bg-grid{
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background-image:
    linear-gradient(rgba(99,179,237,0.022) 1px,transparent 1px),
    linear-gradient(90deg,rgba(99,179,237,0.022) 1px,transparent 1px);
  background-size:64px 64px;
}

/* ═══ LAYOUT ═══ */
.wrap{max-width:880px;margin:0 auto;padding:0 28px;position:relative;z-index:1}
section{padding:80px 0}
.divider{border:none;border-top:1px solid var(--border);margin:0;position:relative;z-index:1}

/* ═══ SCROLL REVEAL ═══ */
.reveal{opacity:0;transform:translateY(20px);transition:opacity 0.65s var(--ease),transform 0.65s var(--ease)}
.reveal.in{opacity:1;transform:translateY(0)}

/* ═══════════════════════════════════════════════
   NAV
═══════════════════════════════════════════════ */
nav{
  position:fixed;top:0;left:0;right:0;z-index:200;
  padding:0 28px;
  background:rgba(6,10,16,0.82);
  backdrop-filter:blur(18px) saturate(150%);
  border-bottom:1px solid var(--border);
}
.nav-inner{
  max-width:880px;margin:0 auto;
  display:flex;align-items:center;justify-content:space-between;
  height:56px;
}
.nav-brand{
  font-family:var(--font-mono);font-size:13.5px;font-weight:500;
  color:var(--text-primary);text-decoration:none;
  display:flex;align-items:center;gap:9px;
}
.nav-brand .live-dot{
  width:7px;height:7px;border-radius:50%;
  background:var(--green);
  box-shadow:0 0 0 0 var(--green);
  animation:livePulse 2.2s infinite;
}
@keyframes livePulse{
  0%{box-shadow:0 0 0 0 rgba(63,185,80,0.5)}
  70%{box-shadow:0 0 0 7px rgba(63,185,80,0)}
  100%{box-shadow:0 0 0 0 rgba(63,185,80,0)}
}
.nav-links{display:flex;gap:24px;list-style:none}
.nav-links a{
  font-family:var(--font-mono);font-size:12px;font-weight:400;
  color:var(--text-secondary);text-decoration:none;
  transition:var(--transition);letter-spacing:0.3px;
}
.nav-links a:hover{color:var(--text-primary)}

/* ═══════════════════════════════════════════════
   HERO
═══════════════════════════════════════════════ */
#hero{
  padding-top:136px;
  padding-bottom:96px;
  position:relative;
  overflow:hidden;
}

/* Decorative right column lines */
#hero::after{
  content:'';
  position:absolute;right:0;top:60px;bottom:60px;width:1px;
  background:linear-gradient(to bottom,transparent,var(--border) 30%,var(--border) 70%,transparent);
}

.hero-eyebrow{
  display:flex;align-items:center;gap:12px;
  margin-bottom:22px;
}
.hero-eyebrow-line{width:32px;height:1px;background:var(--accent);opacity:0.55}
.hero-eyebrow-text{
  font-family:var(--font-mono);font-size:11.5px;font-weight:500;
  color:var(--accent);letter-spacing:3px;text-transform:uppercase;
}

.hero-name{
  font-size:clamp(42px,7vw,68px);
  font-weight:800;
  line-height:1.0;
  letter-spacing:-2.5px;
  color:var(--text-primary);
  margin-bottom:10px;
}
.hero-name .gradient-word{
  background:linear-gradient(125deg,var(--accent) 0%,var(--teal) 60%,#a5f3fc 100%);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
  background-clip:text;
}

.hero-role-row{
  display:flex;align-items:center;gap:10px;
  margin-bottom:18px;flex-wrap:wrap;
}
.hero-role{
  font-size:15.5px;font-weight:600;
  color:var(--text-primary);
}
.hero-role-sep{color:var(--text-muted);font-size:13px}
.hero-role-sub{font-size:14px;color:var(--text-secondary);font-weight:400}

/* Status pill */
.status-pill{
  display:inline-flex;align-items:center;gap:8px;
  padding:6px 14px;
  background:var(--green-dim);
  border:1px solid rgba(63,185,80,0.22);
  border-radius:24px;
  margin-bottom:28px;
}
.status-pill .pulse{
  width:6px;height:6px;border-radius:50%;
  background:var(--green);
  animation:livePulse 2.2s infinite;
}
.status-pill span{
  font-family:var(--font-mono);font-size:11.5px;
  color:var(--green);font-weight:500;
}

.hero-bio{
  font-size:14.5px;color:var(--text-secondary);
  max-width:560px;line-height:1.85;
  margin-bottom:32px;
}
.hero-bio strong{color:var(--text-primary);font-weight:500}

/* Tag cluster */
.tag-cluster{
  display:flex;flex-wrap:wrap;gap:8px;
  margin-bottom:36px;
}
.tag{
  display:inline-flex;align-items:center;gap:6px;
  padding:5px 13px;
  background:var(--bg-card);
  border:1px solid var(--border);
  border-radius:24px;
  font-family:var(--font-mono);font-size:11px;font-weight:400;
  color:var(--text-secondary);
  transition:var(--transition);
}
.tag:hover{border-color:var(--border-hover);color:var(--accent);background:var(--bg-hover)}
.tag-dot{width:5px;height:5px;border-radius:50%}
.td-blue{background:var(--accent)}
.td-orange{background:var(--orange)}
.td-teal{background:var(--teal)}
.td-green{background:var(--green);animation:livePulse 2.2s infinite}

/* CTA buttons */
.cta-row{display:flex;gap:10px;flex-wrap:wrap}
.btn-primary{
  display:inline-flex;align-items:center;gap:8px;
  padding:10px 22px;
  background:var(--accent);
  color:#060a10;
  font-family:var(--font-mono);font-size:12.5px;font-weight:600;
  border-radius:var(--r-md);text-decoration:none;
  transition:var(--transition);border:1px solid transparent;
  letter-spacing:0.2px;
}
.btn-primary:hover{background:#90cdf4;transform:translateY(-2px);box-shadow:0 10px 28px rgba(99,179,237,0.28)}
.btn-outline{
  display:inline-flex;align-items:center;gap:8px;
  padding:10px 20px;
  background:transparent;
  color:var(--text-secondary);
  font-family:var(--font-mono);font-size:12.5px;font-weight:400;
  border-radius:var(--r-md);text-decoration:none;
  transition:var(--transition);
  border:1px solid var(--border-mid);
}
.btn-outline:hover{border-color:var(--border-hover);color:var(--text-primary);background:var(--bg-card);transform:translateY(-2px)}

/* ═══════════════════════════════════════════════
   METRIC STRIP
═══════════════════════════════════════════════ */
.metric-strip{
  display:grid;grid-template-columns:repeat(3,1fr);
  border:1px solid var(--border);border-radius:var(--r-xl);
  overflow:hidden;background:var(--border);gap:1px;
  margin-bottom:44px;
}
.metric{
  background:var(--bg-card);
  padding:30px 28px;
  text-align:center;
  transition:var(--transition);
  position:relative;overflow:hidden;
}
.metric::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,transparent 40%,rgba(99,179,237,0.02) 100%);
  transition:var(--transition);
}
.metric:hover{background:var(--bg-hover)}
.metric:hover::before{background:linear-gradient(135deg,transparent 0%,rgba(99,179,237,0.05) 100%)}
.metric-val{
  font-family:var(--font-mono);font-size:42px;font-weight:700;
  letter-spacing:-2px;line-height:1;color:var(--text-primary);
  margin-bottom:6px;
}
.metric-val.c-blue{color:var(--accent)}
.metric-label{font-size:12px;font-weight:600;color:var(--text-secondary);margin-bottom:3px}
.metric-sub{font-family:var(--font-mono);font-size:10.5px;color:var(--text-muted)}

/* ═══════════════════════════════════════════════
   AWARD CARD
═══════════════════════════════════════════════ */
.award-wrap{
  position:relative;
  background:var(--bg-card);
  border:1px solid rgba(232,137,74,0.18);
  border-radius:var(--r-xl);
  padding:28px 32px;
  display:flex;align-items:flex-start;gap:22px;
  overflow:hidden;
  transition:var(--transition);
}
.award-wrap::before{
  content:'';
  position:absolute;left:0;top:0;bottom:0;width:3px;
  background:linear-gradient(to bottom,var(--orange),rgba(232,137,74,0.2));
}
.award-wrap::after{
  content:'';
  position:absolute;top:0;left:3px;right:0;height:1px;
  background:linear-gradient(to right,var(--orange-dim),transparent);
}
.award-wrap:hover{
  border-color:rgba(232,137,74,0.35);
  transform:translateY(-2px);
  box-shadow:0 20px 48px rgba(0,0,0,0.35);
}
.award-emoji{font-size:34px;flex-shrink:0;line-height:1;margin-top:2px}
.award-content{}
.award-eyebrow{
  font-family:var(--font-mono);font-size:10px;font-weight:500;
  letter-spacing:2.5px;text-transform:uppercase;
  color:var(--orange);margin-bottom:8px;
}
.award-title{font-size:16.5px;font-weight:600;color:var(--text-primary);margin-bottom:6px;line-height:1.35}
.award-paper{
  font-family:var(--font-mono);font-size:12.5px;
  color:var(--accent);margin-bottom:10px;
}
.award-meta{font-size:12.5px;color:var(--text-muted);line-height:1.8}
.award-meta b{color:var(--text-secondary);font-weight:500}
.award-chip{
  margin-left:auto;flex-shrink:0;align-self:center;
  background:var(--orange-dim);
  border:1px solid rgba(232,137,74,0.28);
  border-radius:20px;
  padding:5px 14px;
  font-family:var(--font-mono);font-size:10px;font-weight:600;
  color:var(--orange);white-space:nowrap;letter-spacing:0.5px;
}

/* ═══════════════════════════════════════════════
   SECTION HEADER
═══════════════════════════════════════════════ */
.sec-eyebrow{
  font-family:var(--font-mono);font-size:10.5px;font-weight:500;
  letter-spacing:3px;text-transform:uppercase;color:var(--accent);
  display:flex;align-items:center;gap:10px;margin-bottom:8px;
}
.sec-eyebrow::before{content:'';width:22px;height:1px;background:var(--accent);opacity:0.5}
.sec-title{font-size:25px;font-weight:700;letter-spacing:-0.5px;color:var(--text-primary);margin-bottom:5px}
.sec-sub{font-size:13.5px;color:var(--text-secondary);margin-bottom:44px}

/* ═══════════════════════════════════════════════
   ABOUT
═══════════════════════════════════════════════ */
.about-grid{display:grid;grid-template-columns:1.1fr 0.9fr;gap:28px}
.about-prose{font-size:14px;color:var(--text-secondary);line-height:1.85;margin-bottom:16px}
.about-prose b{color:var(--text-primary);font-weight:500}
.meta-list{list-style:none;display:flex;flex-direction:column;gap:9px;margin-top:4px}
.meta-list li{
  display:flex;align-items:center;gap:10px;
  font-family:var(--font-mono);font-size:11.5px;
}
.meta-list .k{color:var(--text-muted);min-width:84px}
.meta-list .v{color:var(--text-primary)}
.info-cards{display:flex;flex-direction:column;gap:10px}
.info-card{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--r-md);padding:16px 18px;
  transition:var(--transition);
}
.info-card:hover{border-color:var(--border-hover);background:var(--bg-hover)}
.ic-label{font-family:var(--font-mono);font-size:9.5px;letter-spacing:2px;text-transform:uppercase;color:var(--text-muted);margin-bottom:6px}
.ic-value{font-size:13px;font-weight:600;color:var(--text-primary);margin-bottom:2px}
.ic-sub{font-size:11.5px;color:var(--text-secondary)}

/* ═══════════════════════════════════════════════
   TECH STACK
═══════════════════════════════════════════════ */
.stack-section{display:flex;flex-direction:column;gap:24px}
.stack-group{}
.sg-label{
  font-family:var(--font-mono);font-size:10px;letter-spacing:2px;
  text-transform:uppercase;color:var(--text-muted);margin-bottom:10px;
  display:flex;align-items:center;gap:8px;
}
.sg-label::after{content:'';flex:1;height:1px;background:var(--border)}
.chips{display:flex;flex-wrap:wrap;gap:7px}
.chip{
  display:inline-flex;align-items:center;gap:6px;
  padding:6px 13px;
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--r-sm);
  font-family:var(--font-mono);font-size:11.5px;font-weight:400;
  color:var(--text-secondary);
  transition:var(--transition);cursor:default;
}
.chip:hover{border-color:var(--border-hover);color:var(--text-primary);background:var(--bg-hover);transform:translateY(-1px)}

/* ═══════════════════════════════════════════════
   PAPERS
═══════════════════════════════════════════════ */
.paper-list{
  display:flex;flex-direction:column;
  border:1px solid var(--border);border-radius:var(--r-xl);
  overflow:hidden;
  background:var(--border);gap:1px;
}
.paper-row{
  display:flex;align-items:center;gap:14px;
  padding:17px 22px;
  background:var(--bg-card);
  text-decoration:none;
  transition:var(--transition);
}
.paper-row:hover{background:var(--bg-hover)}
.p-num{
  font-family:var(--font-mono);font-size:10.5px;
  color:var(--text-muted);min-width:20px;flex-shrink:0;
}
.p-body{flex:1;min-width:0}
.p-title{font-size:13px;font-weight:500;color:var(--text-primary);margin-bottom:5px;line-height:1.4}
.p-meta{display:flex;align-items:center;gap:7px;flex-wrap:wrap}
.p-tag{
  font-family:var(--font-mono);font-size:9.5px;font-weight:600;
  padding:2px 8px;border-radius:4px;letter-spacing:0.3px;
}
.pt-ml  {background:rgba(99,179,237,0.1);color:var(--accent)}
.pt-dl  {background:rgba(167,139,250,0.1);color:var(--purple)}
.pt-cv  {background:rgba(79,209,197,0.1);color:var(--teal)}
.pt-med {background:rgba(232,137,74,0.12);color:var(--orange)}
.pt-ai  {background:rgba(63,185,80,0.1);color:var(--green)}
.pt-ds  {background:rgba(255,255,255,0.04);color:var(--text-muted)}
.p-year {font-family:var(--font-mono);font-size:10.5px;color:var(--text-muted)}
.p-cite {font-family:var(--font-mono);font-size:10px;color:var(--green);font-weight:500}
.p-award{font-size:10.5px;color:var(--orange);font-weight:600;display:flex;align-items:center;gap:3px}
.p-arr  {font-size:13px;color:var(--text-muted);transition:var(--transition);flex-shrink:0}
.paper-row:hover .p-arr{color:var(--accent);transform:translateX(4px)}

/* ═══════════════════════════════════════════════
   GITHUB STATS — fixed
═══════════════════════════════════════════════ */
.gh-stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px}
.gh-card{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--r-lg);overflow:hidden;
  transition:var(--transition);
  display:flex;flex-direction:column;
}
.gh-card:hover{border-color:var(--border-hover);transform:translateY(-2px);box-shadow:0 16px 40px rgba(0,0,0,0.3)}
.gh-card-full{
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--r-lg);overflow:hidden;
  transition:var(--transition);
}
.gh-card-full:hover{border-color:var(--border-hover);transform:translateY(-2px)}
.gh-card img,.gh-card-full img{
  width:100%;display:block;
  /* Force rerender so browsers don't cache broken state */
}

/* fallback shimmer while loading */
.gh-placeholder{
  background:linear-gradient(90deg,var(--bg-card) 25%,var(--bg-hover) 50%,var(--bg-card) 75%);
  background-size:200% 100%;
  animation:shimmer 1.8s infinite;
  height:180px;width:100%;
}
.gh-placeholder-sm{height:130px}
@keyframes shimmer{0%{background-position:200% 0}100%{background-position:-200% 0}}

/* Stat data cards (used as fallback display) */
.stat-data-grid{
  display:grid;grid-template-columns:repeat(4,1fr);gap:1px;
  border:1px solid var(--border);border-radius:var(--r-lg);
  overflow:hidden;background:var(--border);
  margin-bottom:12px;
}
.sd-cell{
  background:var(--bg-card);padding:20px 16px;text-align:center;
  transition:var(--transition);
}
.sd-cell:hover{background:var(--bg-hover)}
.sd-val{font-family:var(--font-mono);font-size:22px;font-weight:700;color:var(--accent);margin-bottom:3px}
.sd-key{font-size:11px;color:var(--text-muted)}

/* ═══════════════════════════════════════════════
   SNAKE ANIMATION
═══════════════════════════════════════════════ */
.snake-wrap{
  background:var(--bg-card);
  border:1px solid var(--border);
  border-radius:var(--r-xl);
  overflow:hidden;
  padding:24px;
  transition:var(--transition);
}
.snake-wrap:hover{border-color:var(--border-hover)}
.snake-header{
  font-family:var(--font-mono);font-size:10px;letter-spacing:2px;
  text-transform:uppercase;color:var(--text-muted);margin-bottom:16px;
  display:flex;align-items:center;gap:8px;
}
.snake-header::after{content:'';flex:1;height:1px;background:var(--border)}
.snake-img{width:100%;display:block;border-radius:var(--r-md)}

/* ═══════════════════════════════════════════════
   CONNECT
═══════════════════════════════════════════════ */
.connect-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.sc{
  display:flex;align-items:center;gap:12px;
  padding:15px 16px;
  background:var(--bg-card);border:1px solid var(--border);
  border-radius:var(--r-md);text-decoration:none;
  transition:var(--transition);
}
.sc:hover{border-color:var(--border-hover);background:var(--bg-hover);transform:translateY(-2px)}
.sc-icon{
  width:36px;height:36px;flex-shrink:0;
  background:var(--bg-hover);border-radius:var(--r-sm);
  display:flex;align-items:center;justify-content:center;
  font-size:16px;transition:var(--transition);
}
.sc:hover .sc-icon{background:var(--accent-dim)}
.sc-name{font-size:12.5px;font-weight:600;color:var(--text-primary);line-height:1.2}
.sc-handle{font-family:var(--font-mono);font-size:10.5px;color:var(--text-muted);margin-top:1px}

/* ═══════════════════════════════════════════════
   FOOTER
═══════════════════════════════════════════════ */
footer{
  border-top:1px solid var(--border);
  padding:36px 28px;text-align:center;
  position:relative;z-index:1;
}
.footer-quote{
  font-family:var(--font-mono);font-size:12px;
  color:var(--text-muted);font-style:italic;margin-bottom:10px;
}
.footer-meta{font-family:var(--font-mono);font-size:10.5px;color:var(--text-muted);opacity:0.45}

/* ═══════════════════════════════════════════════
   HERO ANIM KEYFRAMES (stagger)
═══════════════════════════════════════════════ */
@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}
.a1{animation:fadeUp 0.7s var(--ease) 0.05s both}
.a2{animation:fadeUp 0.7s var(--ease) 0.15s both}
.a3{animation:fadeUp 0.7s var(--ease) 0.25s both}
.a4{animation:fadeUp 0.7s var(--ease) 0.35s both}
.a5{animation:fadeUp 0.7s var(--ease) 0.45s both}
.a6{animation:fadeUp 0.7s var(--ease) 0.55s both}
.a7{animation:fadeUp 0.7s var(--ease) 0.65s both}

/* ═══ RESPONSIVE ═══ */
@media(max-width:660px){
  .metric-strip,.stat-data-grid{grid-template-columns:1fr 1fr}
  .about-grid,.gh-stats-grid,.connect-grid{grid-template-columns:1fr}
  .nav-links{display:none}
  .award-wrap{flex-direction:column}
  .award-chip{margin-left:0;align-self:flex-start}
}
</style>
</head>
<body>

<!-- Ambient bg -->
<div class="bg-orb bg-orb-1"></div>
<div class="bg-orb bg-orb-2"></div>
<div class="bg-grid"></div>

<!-- ═══════════════════ NAV ═══════════════════ -->
<nav>
  <div class="nav-inner">
    <a href="#" class="nav-brand">
      <span class="live-dot"></span>
      sanwar.islam
    </a>
    <ul class="nav-links">
      <li><a href="#about">about</a></li>
      <li><a href="#stack">stack</a></li>
      <li><a href="#research">research</a></li>
      <li><a href="#stats">github</a></li>
      <li><a href="#connect">contact</a></li>
    </ul>
  </div>
</nav>

<!-- ═══════════════════ HERO ═══════════════════ -->
<section id="hero">
  <div class="wrap">

    <div class="hero-eyebrow a1">
      <span class="hero-eyebrow-line"></span>
      <span class="hero-eyebrow-text">ML Engineer &amp; AI Researcher</span>
    </div>

    <h1 class="hero-name a2">
      Sanwar <span class="gradient-word">Islam</span>
    </h1>

    <div class="hero-role-row a3">
      <span class="hero-role">Full-Stack Developer</span>
      <span class="hero-role-sep">·</span>
      <span class="hero-role-sub">Computer Vision</span>
      <span class="hero-role-sep">·</span>
      <span class="hero-role-sub">Medical AI</span>
      <span class="hero-role-sep">·</span>
      <span class="hero-role-sub">Deep Learning</span>
    </div>

    <div class="status-pill a4">
      <span class="pulse"></span>
      <span>Available — Open to Remote ML / AI Roles</span>
    </div>

    <p class="hero-bio a5">
      Published researcher with <b>9 papers</b> across IEEE, Springer &amp; SCOPUS.
      Building the intersection of deep learning and real-world medical applications at
      <b>East West University</b>, Dhaka.
      Springer ICDMIS 2024 Best Paper Award recipient.
    </p>

    <div class="tag-cluster a6">
      <span class="tag"><span class="tag-dot td-blue"></span>9 Publications</span>
      <span class="tag"><span class="tag-dot td-orange"></span>Best Paper Award</span>
      <span class="tag"><span class="tag-dot td-teal"></span>3 Citations</span>
      <span class="tag"><span class="tag-dot td-green"></span>East West University</span>
      <span class="tag"><span class="tag-dot td-blue"></span>Dhaka, BD 🇧🇩</span>
    </div>

    <div class="cta-row a7">
      <a href="https://sanwarul-ai-folio.vercel.app/" class="btn-primary" target="_blank">
        <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 2a15.5 15.5 0 010 20M2 12h20"/></svg>
        View Portfolio
      </a>
      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ&hl=en&oi=ao" class="btn-outline" target="_blank">
        <svg width="13" height="13" fill="none" stroke="currentColor" stroke-width="2.2" viewBox="0 0 24 24"><path d="M12 2L3 7l9 5 9-5-9-5zM3 17l9 5 9-5M3 12l9 5 9-5"/></svg>
        Google Scholar
      </a>
      <a href="https://github.com/Sanwar021" class="btn-outline" target="_blank">
        <svg width="13" height="13" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.58 2 12.26c0 4.54 2.87 8.39 6.84 9.75.5.09.68-.22.68-.49v-1.71C6.73 20.4 6.14 18.5 6.14 18.5c-.46-1.18-1.11-1.5-1.11-1.5-.91-.63.07-.62.07-.62 1 .07 1.53 1.05 1.53 1.05.9 1.56 2.35 1.11 2.93.85.09-.66.35-1.11.63-1.37-2.24-.26-4.59-1.14-4.59-5.07 0-1.12.39-2.03 1.03-2.75-.1-.26-.45-1.3.1-2.71 0 0 .84-.27 2.75 1.05a9.4 9.4 0 012.5-.34c.85 0 1.7.11 2.5.34 1.91-1.32 2.75-1.05 2.75-1.05.55 1.41.2 2.45.1 2.71.64.72 1.03 1.63 1.03 2.75 0 3.94-2.36 4.81-4.6 5.06.36.32.68.94.68 1.9v2.82c0 .27.18.59.69.49A10.27 10.27 0 0022 12.26C22 6.58 17.52 2 12 2z"/></svg>
        GitHub
      </a>
      <a href="https://www.linkedin.com/in/sanwarislam17/" class="btn-outline" target="_blank">
        <svg width="13" height="13" fill="currentColor" viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
    </div>

  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ METRICS + AWARD ═══════════════════ -->
<section>
  <div class="wrap">
    <div class="metric-strip reveal">
      <div class="metric">
        <div class="metric-val c-blue">9</div>
        <div class="metric-label">Publications</div>
        <div class="metric-sub">IEEE · Springer · SCOPUS</div>
      </div>
      <div class="metric">
        <div class="metric-val c-blue">3</div>
        <div class="metric-label">Citations</div>
        <div class="metric-sub">Google Scholar · Verified</div>
      </div>
      <div class="metric">
        <div class="metric-val c-blue">2</div>
        <div class="metric-label">Best Paper Awards</div>
        <div class="metric-sub">ICDMIS 2024 · Springer</div>
      </div>
    </div>

    <div class="award-wrap reveal">
      <div class="award-emoji">🏆</div>
      <div class="award-content">
        <div class="award-eyebrow">Springer ICDMIS 2024 — Best Paper Award</div>
        <div class="award-title">Prediction of Glioblastoma Using 3D-CNN</div>
        <div class="award-paper">ICDMIS 2024 · ECMT India × Universitas Al Asyariah Mandar, Indonesia · Oct 7–8, 2024</div>
        <div class="award-meta">
          Published in <b>Springer LNNS Series</b> · <b>SCOPUS Indexed</b> ·
          East West University, Dept. of CSE ·
          Supervised by <b>Prof. Dr. Ahmed Wasif Reza</b>
        </div>
      </div>
      <div class="award-chip">VERIFIED ✓</div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ ABOUT ═══════════════════ -->
<section id="about">
  <div class="wrap">
    <div class="sec-eyebrow reveal">About</div>
    <h2 class="sec-title reveal">Who I am</h2>
    <p class="sec-sub reveal">Builder, researcher, and published author from Dhaka.</p>
    <div class="about-grid reveal">
      <div>
        <p class="about-prose">
          I'm a <b>Machine Learning Engineer and AI Researcher</b> at East West University,
          specializing in computer vision, medical imaging, and deep learning systems. With
          <b>9 peer-reviewed publications</b> across Springer, IEEE, and SCOPUS-indexed venues,
          my work bridges AI and healthcare.
        </p>
        <p class="about-prose">
          On the engineering side, I build full-stack products with <b>React, Go, and PostgreSQL</b> —
          currently developing <em>Upasham Prescription</em>, a medical platform combining modern web
          tech with AI-assisted diagnostics.
        </p>
        <ul class="meta-list">
          <li><span class="k">location</span><span class="v">Dhaka, Bangladesh 🇧🇩</span></li>
          <li><span class="k">institute</span><span class="v">East West University</span></li>
          <li><span class="k">dept.</span><span class="v">Computer Science &amp; Engineering</span></li>
          <li><span class="k">portfolio</span><span class="v">sanwarul-ai-folio.vercel.app</span></li>
          <li><span class="k">scholar</span><span class="v">eqFfAEMAAAAJ</span></li>
        </ul>
      </div>
      <div class="info-cards">
        <div class="info-card">
          <div class="ic-label">Currently Building</div>
          <div class="ic-value">Upasham Prescription</div>
          <div class="ic-sub">Medical platform · React + Go + PostgreSQL</div>
        </div>
        <div class="info-card">
          <div class="ic-label">Research Focus</div>
          <div class="ic-value">Computer Vision · Medical AI</div>
          <div class="ic-sub">3D-CNN · Tumor detection · Disease classification</div>
        </div>
        <div class="info-card" style="border-color:rgba(63,185,80,0.18)">
          <div class="ic-label">Status</div>
          <div class="ic-value" style="color:var(--green)">🟢 Open to Opportunities</div>
          <div class="ic-sub">Remote ML / AI Roles — Full-time or Research</div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ TECH STACK ═══════════════════ -->
<section id="stack">
  <div class="wrap">
    <div class="sec-eyebrow reveal">Technology</div>
    <h2 class="sec-title reveal">Tech Stack</h2>
    <p class="sec-sub reveal">ML engineering, full-stack web, and research tooling.</p>
    <div class="stack-section reveal">
      <div class="stack-group">
        <div class="sg-label">Machine Learning &amp; AI</div>
        <div class="chips">
          <span class="chip">🐍 Python</span>
          <span class="chip">🔥 PyTorch</span>
          <span class="chip">🧠 TensorFlow</span>
          <span class="chip">📊 scikit-learn</span>
          <span class="chip">🐼 Pandas</span>
          <span class="chip">🔢 NumPy</span>
          <span class="chip">📓 Jupyter</span>
          <span class="chip">🏆 Kaggle</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="sg-label">Web Development</div>
        <div class="chips">
          <span class="chip">⚛️ React</span>
          <span class="chip">⚡ Vite</span>
          <span class="chip">📘 TypeScript</span>
          <span class="chip">🟨 JavaScript</span>
          <span class="chip">🌊 Tailwind CSS</span>
          <span class="chip">🐹 Go</span>
          <span class="chip">🐘 PostgreSQL</span>
        </div>
      </div>
      <div class="stack-group">
        <div class="sg-label">Tools &amp; Platforms</div>
        <div class="chips">
          <span class="chip">🔀 Git</span>
          <span class="chip">🐙 GitHub</span>
          <span class="chip">💻 VS Code</span>
          <span class="chip">🐧 Linux</span>
          <span class="chip">☁️ Google Colab</span>
          <span class="chip">▲ Vercel</span>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ RESEARCH ═══════════════════ -->
<section id="research">
  <div class="wrap">
    <div class="sec-eyebrow reveal">Publications</div>
    <h2 class="sec-title reveal">Research Papers</h2>
    <p class="sec-sub reveal">9 publications · Springer · IEEE · SCOPUS · Google Scholar verified</p>

    <div class="paper-list reveal">

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">01</span>
        <div class="p-body">
          <div class="p-title">Measuring Accuracy of Different ML Algorithms on Expectations and Experiences of University Students</div>
          <div class="p-meta"><span class="p-tag pt-ml">Machine Learning</span><span class="p-year">2025</span><span class="p-cite">1 citation</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">02</span>
        <div class="p-body">
          <div class="p-title">Earthquake Magnitude Prediction: A Survey on ML Models, Datasets, Techniques, Challenges, and Future Directions</div>
          <div class="p-meta"><span class="p-tag pt-dl">Deep Learning</span><span class="p-year">2024</span><span class="p-cite">1 citation</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">03</span>
        <div class="p-body">
          <div class="p-title">Detection of Sugarcane Leaf Diseases Using Custom CNN and ResNet50</div>
          <div class="p-meta"><span class="p-tag pt-cv">Computer Vision</span><span class="p-year">2024</span><span class="p-cite">1 citation</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">04</span>
        <div class="p-body">
          <div class="p-title">Prediction of Glioblastoma Using (Data Mining &amp; AI)</div>
          <div class="p-meta"><span class="p-tag pt-med">Medical AI</span><span class="p-year">2025</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">05</span>
        <div class="p-body">
          <div class="p-title">Deep Learning-Based Classification of Coconut Leaf Diseases Using Optimized CNN Models</div>
          <div class="p-meta"><span class="p-tag pt-dl">Deep Learning</span><span class="p-year">2025</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">06</span>
        <div class="p-body">
          <div class="p-title">Green Machine Learning (GML): Energy-Aware Approaches for Sustainable Computing</div>
          <div class="p-meta"><span class="p-tag pt-ai">Sustainable AI</span><span class="p-year">2025</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">07</span>
        <div class="p-body">
          <div class="p-title">Detection of Lemon Leaf Diseases Using Inception V3-Based Machine Learning Model</div>
          <div class="p-meta"><span class="p-tag pt-cv">Computer Vision</span><span class="p-year">2025</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ" class="paper-row" target="_blank">
        <span class="p-num">08</span>
        <div class="p-body">
          <div class="p-title">Forecasting Air Quality: A Comprehensive Survey of Air Pollution Prediction Methods and Applications</div>
          <div class="p-meta"><span class="p-tag pt-ds">Data Science</span><span class="p-year">2025</span></div>
        </div>
        <span class="p-arr">→</span>
      </a>

      <a href="https://ewubd.edu/achievement-details/cse-students-won-two-springer-icdmis-2024-best-paper-awards"
         class="paper-row" target="_blank"
         style="border-top:1px solid rgba(232,137,74,0.18)">
        <span class="p-num" style="color:var(--orange)">09</span>
        <div class="p-body">
          <div class="p-title">Prediction of Glioblastoma Using 3D-CNN</div>
          <div class="p-meta">
            <span class="p-tag pt-med">Medical AI</span>
            <span class="p-year">2024</span>
            <span class="p-award">🏆 Best Paper Award</span>
          </div>
        </div>
        <span class="p-arr" style="color:var(--orange)">→</span>
      </a>

    </div>
    <p style="margin-top:14px;font-family:var(--font-mono);font-size:10.5px;color:var(--text-muted)">
      Published in: Springer (LNNS) · International Conference on Quantum Photonics &amp; AI · ICIDA · ICDMIS · ICCIIT
    </p>
  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ GITHUB STATS ═══════════════════ -->
<section id="stats">
  <div class="wrap">
    <div class="sec-eyebrow reveal">GitHub</div>
    <h2 class="sec-title reveal">Contribution Stats</h2>
    <p class="sec-sub reveal">Open source activity and contribution history.</p>

    <!-- Stats + Streak side by side -->
    <div class="gh-stats-grid reveal">
      <div class="gh-card">
        <img
          id="gh-stats-img"
          src="https://github-readme-stats.vercel.app/api?username=Sanwar021&show_icons=true&count_private=true&theme=transparent&hide_border=true&bg_color=0e1520&title_color=e8eef4&icon_color=63b3ed&text_color=7e8a96&ring_color=63b3ed&border_radius=0"
          alt="GitHub Stats"
          loading="lazy"
          onerror="this.style.display='none';this.nextElementSibling.style.display='block'"
        />
        <div class="gh-placeholder gh-placeholder-sm" style="display:none"></div>
      </div>
      <div class="gh-card">
        <img
          src="https://streak-stats.demolab.com/?user=Sanwar021&theme=transparent&hide_border=true&background=0e1520&stroke=1e2a3a&ring=63b3ed&fire=e8894a&currStreakLabel=e8eef4&sideLabels=7e8a96&dates=3d4550&sideNums=e8eef4&border_radius=0"
          alt="GitHub Streak"
          loading="lazy"
          onerror="this.style.display='none';this.nextElementSibling.style.display='block'"
        />
        <div class="gh-placeholder gh-placeholder-sm" style="display:none"></div>
      </div>
    </div>

    <!-- Activity graph full width -->
    <div class="gh-card-full reveal">
      <img
        src="https://github-readme-activity-graph.vercel.app/graph?username=Sanwar021&bg_color=0e1520&color=63b3ed&line=1e2a3a&point=63b3ed&area=true&area_color=132030&hide_border=true&custom_title=Contribution%20Graph%20%E2%80%94%20Sanwar021&radius=0"
        alt="Contribution Graph"
        loading="lazy"
        onerror="this.style.display='none'"
      />
    </div>

    <!-- GitHub Trophies -->
    <div class="gh-card-full reveal" style="margin-top:12px">
      <img
        src="https://github-profile-trophy.vercel.app/?username=Sanwar021&theme=darkhub&no-frame=true&no-bg=true&margin-w=6&column=7&rank=SECRET,SSS,SS,S,AAA,AA,A,B,C"
        alt="GitHub Trophies"
        loading="lazy"
        onerror="this.style.display='none'"
        style="padding:16px;background:var(--bg-card)"
      />
    </div>

  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ SNAKE ANIMATION ═══════════════════ -->
<section id="snake">
  <div class="wrap">
    <div class="sec-eyebrow reveal">Contributions</div>
    <h2 class="sec-title reveal">Contribution Snake</h2>
    <p class="sec-sub reveal">A visual journey through every commit and contribution.</p>

    <div class="snake-wrap reveal">
      <div class="snake-header">
        contribution-grid-snake — dark mode
      </div>
      <!-- Primary: prefers-color-scheme aware SVG from GitHub Actions output -->
      <picture>
        <source
          media="(prefers-color-scheme: dark)"
          srcset="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake-dark.svg"
        />
        <source
          media="(prefers-color-scheme: light)"
          srcset="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake.svg"
        />
        <img
          class="snake-img"
          src="https://github.com/Sanwar021/Sanwar021/raw/output/github-contribution-grid-snake-dark.svg"
          alt="Contribution Snake Animation"
          loading="lazy"
          onerror="handleSnakeError(this)"
        />
      </picture>

      <!-- Fallback: animated SVG snake built inline -->
      <div id="snake-fallback" style="display:none">
        <svg viewBox="0 0 840 120" xmlns="http://www.w3.org/2000/svg" style="width:100%;display:block;border-radius:8px">
          <rect width="840" height="120" fill="#0e1520" rx="8"/>
          <!-- Grid cells -->
          <g opacity="0.5">
            <script type="text/javascript">
              // Rendered statically below
            </script>
          </g>
          <!-- Static contribution-style grid -->
          <g fill="#1e2a3a">
            <!-- Row of contribution squares -->
            <rect x="10" y="10" width="10" height="10" rx="2"/><rect x="22" y="10" width="10" height="10" rx="2"/><rect x="34" y="10" width="10" height="10" rx="2"/><rect x="46" y="10" width="10" height="10" rx="2"/><rect x="58" y="10" width="10" height="10" rx="2"/><rect x="70" y="10" width="10" height="10" rx="2"/><rect x="82" y="10" width="10" height="10" rx="2"/><rect x="94" y="10" width="10" height="10" rx="2"/><rect x="106" y="10" width="10" height="10" rx="2"/><rect x="118" y="10" width="10" height="10" rx="2"/>
            <rect x="10" y="22" width="10" height="10" rx="2"/><rect x="22" y="22" width="10" height="10" rx="2"/><rect x="34" y="22" width="10" height="10" rx="2"/><rect x="46" y="22" width="10" height="10" rx="2"/><rect x="58" y="22" width="10" height="10" rx="2"/>
            <!-- Snake path highlight -->
          </g>
          <!-- Animated snake -->
          <g>
            <!-- Snake body segments -->
            <rect x="130" y="55" width="12" height="12" rx="3" fill="#63b3ed" opacity="0.9"/>
            <rect x="144" y="55" width="12" height="12" rx="3" fill="#4fd1c5" opacity="0.85"/>
            <rect x="158" y="55" width="12" height="12" rx="3" fill="#4fd1c5" opacity="0.8"/>
            <rect x="172" y="55" width="12" height="12" rx="3" fill="#4fd1c5" opacity="0.75"/>
            <rect x="186" y="55" width="12" height="12" rx="3" fill="#3fb950" opacity="0.7"/>
            <!-- Snake head -->
            <rect x="116" y="55" width="12" height="12" rx="3" fill="#63b3ed">
              <animateTransform attributeName="transform" type="translate"
                values="0,0;700,0;700,14;0,14;0,0"
                keyTimes="0;0.25;0.5;0.75;1"
                dur="8s" repeatCount="indefinite"/>
            </rect>
            <!-- Eyes on snake head -->
            <circle cx="122" cy="59" r="1.5" fill="#060a10">
              <animateTransform attributeName="transform" type="translate"
                values="0,0;700,0;700,14;0,14;0,0"
                keyTimes="0;0.25;0.5;0.75;1"
                dur="8s" repeatCount="indefinite"/>
            </circle>
          </g>
          <text x="420" y="106" text-anchor="middle" font-family="JetBrains Mono,monospace" font-size="10" fill="#3d4550">
            🐍 Live snake loads from GitHub Actions — set up output branch to enable
          </text>
        </svg>
      </div>
    </div>
  </div>
</section>

<hr class="divider"/>

<!-- ═══════════════════ CONNECT ═══════════════════ -->
<section id="connect">
  <div class="wrap">
    <div class="sec-eyebrow reveal">Contact</div>
    <h2 class="sec-title reveal">Let's Connect</h2>
    <p class="sec-sub reveal">Open to research collaborations, remote roles, and interesting projects.</p>
    <div class="connect-grid reveal">
      <a href="https://sanwarul-ai-folio.vercel.app/" class="sc" target="_blank">
        <div class="sc-icon">🌐</div>
        <div><div class="sc-name">Portfolio</div><div class="sc-handle">sanwarul-ai-folio.vercel.app</div></div>
      </a>
      <a href="https://www.linkedin.com/in/sanwarislam17/" class="sc" target="_blank">
        <div class="sc-icon">💼</div>
        <div><div class="sc-name">LinkedIn</div><div class="sc-handle">sanwarislam17</div></div>
      </a>
      <a href="https://scholar.google.com/citations?user=eqFfAEMAAAAJ&hl=en&oi=ao" class="sc" target="_blank">
        <div class="sc-icon">📚</div>
        <div><div class="sc-name">Google Scholar</div><div class="sc-handle">eqFfAEMAAAAJ</div></div>
      </a>
      <a href="https://github.com/Sanwar021" class="sc" target="_blank">
        <div class="sc-icon">🐙</div>
        <div><div class="sc-name">GitHub</div><div class="sc-handle">@Sanwar021</div></div>
      </a>
      <a href="https://www.facebook.com/sanwar.islam.2024/" class="sc" target="_blank">
        <div class="sc-icon">📘</div>
        <div><div class="sc-name">Facebook</div><div class="sc-handle">sanwar.islam.2024</div></div>
      </a>
      <a href="https://www.instagram.com/mr.raw420_/" class="sc" target="_blank">
        <div class="sc-icon">📸</div>
        <div><div class="sc-name">Instagram</div><div class="sc-handle">@mr.raw420_</div></div>
      </a>
    </div>
  </div>
</section>

<!-- ═══════════════════ FOOTER ═══════════════════ -->
<footer>
  <div class="footer-quote">"In God we trust. All others must bring data." — W. Edwards Deming</div>
  <div class="footer-meta">Sanwar Islam · @Sanwar021 · East West University · Dhaka, BD</div>
</footer>

<script>
/* ── Scroll reveal ── */
const io = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('in'); io.unobserve(e.target); }
  });
}, { threshold: 0.06, rootMargin: '0px 0px -20px 0px' });

document.querySelectorAll('.reveal').forEach((el, i) => {
  el.style.transitionDelay = (i % 5 * 70) + 'ms';
  io.observe(el);
});

/* ── Snake fallback ── */
function handleSnakeError(img) {
  img.style.display = 'none';
  document.getElementById('snake-fallback').style.display = 'block';
}

/* ── GitHub stats image error handling ── */
document.querySelectorAll('.gh-card img, .gh-card-full img').forEach(img => {
  img.addEventListener('error', function() {
    const placeholder = this.nextElementSibling;
    if (placeholder && placeholder.classList.contains('gh-placeholder')) {
      this.style.display = 'none';
      placeholder.style.display = 'block';
    }
  });
});

/* ── Nav active link highlight ── */
const sections = document.querySelectorAll('section[id]');
const navLinks = document.querySelectorAll('.nav-links a');
window.addEventListener('scroll', () => {
  let current = '';
  sections.forEach(s => {
    if (window.scrollY >= s.offsetTop - 80) current = s.id;
  });
  navLinks.forEach(a => {
    a.style.color = a.getAttribute('href') === '#' + current
      ? 'var(--text-primary)' : '';
  });
}, { passive: true });
</script>
</body>
</html>
