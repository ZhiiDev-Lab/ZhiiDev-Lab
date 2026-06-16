<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub — Aryan Prasetyo</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --obsidian: #0A0A0F;
    --slate: #13131A;
    --slate-2: #1C1C27;
    --violet: #7C3AED;
    --violet-soft: #9D5FF5;
    --violet-dim: rgba(124,58,237,0.15);
    --violet-glow: rgba(124,58,237,0.35);
    --ghost: #F8F8FF;
    --silver: #8B8BA7;
    --silver-dim: #3D3D52;
    --green: #22D3A5;
    --amber: #F59E0B;
    --blue: #38BDF8;
    --rose: #FB7185;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--obsidian);
    color: var(--ghost);
    font-family: 'Inter', sans-serif;
    font-size: 15px;
    line-height: 1.6;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── AURORA BACKGROUND ── */
  .aurora {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
    overflow: hidden;
  }
  .aurora::before, .aurora::after {
    content: '';
    position: absolute;
    border-radius: 50%;
    filter: blur(120px);
    opacity: 0.12;
    animation: drift 18s ease-in-out infinite alternate;
  }
  .aurora::before {
    width: 700px; height: 500px;
    background: radial-gradient(circle, #7C3AED, transparent 70%);
    top: -200px; left: -150px;
    animation-delay: 0s;
  }
  .aurora::after {
    width: 600px; height: 400px;
    background: radial-gradient(circle, #38BDF8, transparent 70%);
    top: 10%; right: -200px;
    animation-delay: -8s;
    opacity: 0.08;
  }
  @keyframes drift {
    0%   { transform: translate(0, 0) scale(1); }
    50%  { transform: translate(60px, 40px) scale(1.08); }
    100% { transform: translate(-40px, 80px) scale(0.95); }
  }

  /* ── LAYOUT ── */
  .page { position: relative; z-index: 1; max-width: 1100px; margin: 0 auto; padding: 0 28px 80px; }

  /* ── NAV ── */
  nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 22px 0 16px;
    border-bottom: 1px solid var(--silver-dim);
    margin-bottom: 52px;
  }
  .nav-logo {
    display: flex; align-items: center; gap: 10px;
    font-family: 'Syne', sans-serif; font-size: 17px; font-weight: 700; color: var(--ghost);
    text-decoration: none; letter-spacing: -0.3px;
  }
  .nav-logo svg { opacity: 0.9; }
  .nav-links { display: flex; gap: 8px; }
  .nav-links a {
    font-size: 13px; font-weight: 500; color: var(--silver);
    text-decoration: none; padding: 6px 14px; border-radius: 6px;
    transition: all 0.2s;
  }
  .nav-links a:hover { color: var(--ghost); background: var(--slate-2); }
  .nav-links a.active { color: var(--ghost); background: var(--slate-2); }

  /* ── HERO ── */
  .hero {
    display: grid;
    grid-template-columns: 260px 1fr;
    gap: 52px;
    align-items: start;
    margin-bottom: 64px;
  }
  .avatar-col { display: flex; flex-direction: column; gap: 20px; }
  .avatar-wrap {
    position: relative;
    width: 220px; height: 220px;
  }
  .avatar-wrap::before {
    content: '';
    position: absolute;
    inset: -3px;
    border-radius: 50%;
    background: conic-gradient(from 0deg, var(--violet), var(--blue), var(--violet-soft), var(--violet));
    animation: spin 8s linear infinite;
  }
  .avatar-wrap::after {
    content: '';
    position: absolute;
    inset: -10px;
    border-radius: 50%;
    background: radial-gradient(circle, var(--violet-glow), transparent 70%);
    opacity: 0.6;
    animation: pulse 3s ease-in-out infinite;
  }
  @keyframes spin  { to { transform: rotate(360deg); } }
  @keyframes pulse { 0%,100%{opacity:0.4;} 50%{opacity:0.9;} }
  .avatar-img {
    position: relative; z-index: 1;
    width: 220px; height: 220px;
    border-radius: 50%;
    border: 4px solid var(--obsidian);
    object-fit: cover;
    display: flex; align-items: center; justify-content: center;
    background: var(--slate-2);
    font-size: 72px;
  }
  .avatar-initial {
    position: relative; z-index: 1;
    width: 220px; height: 220px;
    border-radius: 50%;
    border: 4px solid var(--obsidian);
    background: linear-gradient(135deg, #1e1e2e 0%, #2d1b5e 100%);
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif;
    font-size: 72px; font-weight: 800; color: var(--violet-soft);
  }
  .status-badge {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 7px 14px; border-radius: 8px;
    background: var(--slate-2); border: 1px solid var(--silver-dim);
    font-size: 12.5px; color: var(--silver); width: fit-content;
  }
  .status-dot {
    width: 8px; height: 8px; border-radius: 50%;
    background: var(--green);
    box-shadow: 0 0 0 2px rgba(34,211,165,0.25);
    animation: blink 2.5s ease-in-out infinite;
  }
  @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0.4;} }
  .follow-btn {
    width: 100%;
    padding: 10px;
    border-radius: 8px;
    border: 1px solid var(--silver-dim);
    background: var(--slate-2);
    color: var(--ghost);
    font-family: 'Inter', sans-serif;
    font-size: 13.5px; font-weight: 500;
    cursor: pointer;
    transition: all 0.2s;
  }
  .follow-btn:hover { background: var(--slate); border-color: var(--violet); color: var(--violet-soft); }
  .follow-btn.primary {
    background: var(--violet);
    border-color: transparent;
    color: #fff;
    margin-bottom: 0;
  }
  .follow-btn.primary:hover { background: var(--violet-soft); }
  .btn-row { display: flex; gap: 8px; }
  .btn-row .follow-btn { flex: 1; }

  /* ── BIO ── */
  .bio-col {}
  .eyebrow {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--violet-soft); margin-bottom: 12px;
    display: flex; align-items: center; gap: 10px;
  }
  .eyebrow::after { content:''; flex:1; height:1px; background:var(--silver-dim); }
  .display-name {
    font-family: 'Syne', sans-serif;
    font-size: 42px; font-weight: 800; line-height: 1.08;
    letter-spacing: -1.5px; color: var(--ghost);
    margin-bottom: 6px;
  }
  .handle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 16px; color: var(--silver); margin-bottom: 20px;
  }
  .bio-text {
    font-size: 15.5px; color: #BBBBD4; line-height: 1.75;
    max-width: 540px; margin-bottom: 28px;
  }
  .meta-list { display: flex; flex-wrap: wrap; gap: 14px 24px; margin-bottom: 28px; }
  .meta-item {
    display: flex; align-items: center; gap: 7px;
    font-size: 13.5px; color: var(--silver);
  }
  .meta-item svg { flex-shrink: 0; opacity: 0.7; }
  .meta-item a { color: var(--violet-soft); text-decoration: none; }
  .meta-item a:hover { text-decoration: underline; }

  /* ── STATS ── */
  .stats-row { display: flex; gap: 28px; margin-bottom: 32px; }
  .stat { cursor: default; }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 22px; font-weight: 700; color: var(--ghost);
  }
  .stat-label { font-size: 12.5px; color: var(--silver); }

  /* ── TOPICS ── */
  .topics { display: flex; flex-wrap: wrap; gap: 8px; }
  .topic {
    padding: 5px 13px; border-radius: 20px;
    font-size: 12px; font-weight: 500;
    border: 1px solid;
  }
  .topic.v { background: rgba(124,58,237,0.12); border-color: rgba(124,58,237,0.3); color: #C4B5FD; }
  .topic.b { background: rgba(56,189,248,0.10); border-color: rgba(56,189,248,0.25); color: #7DD3FC; }
  .topic.g { background: rgba(34,211,165,0.10); border-color: rgba(34,211,165,0.25); color: #6EE7B7; }
  .topic.a { background: rgba(245,158,11,0.10); border-color: rgba(245,158,11,0.25); color: #FCD34D; }

  /* ── SECTION HEADER ── */
  .section-head {
    display: flex; align-items: center; justify-content: space-between;
    margin-bottom: 20px;
  }
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 13px; font-weight: 600; letter-spacing: 1.5px;
    text-transform: uppercase; color: var(--silver);
  }
  .section-link {
    font-size: 12.5px; color: var(--violet-soft); text-decoration: none;
  }
  .section-link:hover { text-decoration: underline; }

  /* ── PINNED REPOS ── */
  .pinned-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 16px;
    margin-bottom: 52px;
  }
  .repo-card {
    background: var(--slate);
    border: 1px solid var(--silver-dim);
    border-radius: 12px;
    padding: 22px 24px;
    transition: all 0.25s;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    transform-style: preserve-3d;
  }
  .repo-card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--violet-dim) 0%, transparent 60%);
    opacity: 0;
    transition: opacity 0.3s;
    border-radius: 12px;
  }
  .repo-card:hover { border-color: rgba(124,58,237,0.5); transform: translateY(-3px); box-shadow: 0 12px 40px rgba(0,0,0,0.5), 0 0 0 1px rgba(124,58,237,0.2); }
  .repo-card:hover::before { opacity: 1; }
  .repo-top { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 10px; }
  .repo-icon { font-size: 18px; margin-bottom: 8px; }
  .repo-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13.5px; font-weight: 500; color: var(--violet-soft);
  }
  .repo-desc { font-size: 13px; color: var(--silver); line-height: 1.65; margin-bottom: 16px; }
  .repo-footer { display: flex; align-items: center; gap: 16px; }
  .repo-lang { display: flex; align-items: center; gap: 5px; font-size: 12px; color: var(--silver); }
  .lang-dot { width: 10px; height: 10px; border-radius: 50%; }
  .repo-stars { display: flex; align-items: center; gap: 4px; font-size: 12px; color: var(--silver); }
  .star-fork { opacity: 0.8; }
  .repo-badge {
    font-size: 10px; font-weight: 600; letter-spacing: 0.5px;
    text-transform: uppercase;
    padding: 3px 9px; border-radius: 4px;
    background: var(--violet-dim); color: #C4B5FD;
    border: 1px solid rgba(124,58,237,0.3);
    margin-left: auto;
  }

  /* ── CONTRIBUTION GRAPH ── */
  .contrib-section { margin-bottom: 52px; }
  .contrib-grid {
    background: var(--slate);
    border: 1px solid var(--silver-dim);
    border-radius: 12px;
    padding: 24px;
  }
  .contrib-months { display: flex; gap: 0; margin-bottom: 8px; }
  .contrib-month { font-size: 10px; color: var(--silver); flex: 1; font-family: 'Inter', sans-serif; }
  .cells { display: flex; gap: 4px; }
  .cell-col { display: flex; flex-direction: column; gap: 4px; }
  .cell {
    width: 13px; height: 13px; border-radius: 3px;
    background: var(--slate-2);
    transition: transform 0.15s;
    cursor: default;
  }
  .cell:hover { transform: scale(1.3); }
  .cell.l1 { background: rgba(124,58,237,0.2); }
  .cell.l2 { background: rgba(124,58,237,0.4); }
  .cell.l3 { background: rgba(124,58,237,0.65); }
  .cell.l4 { background: var(--violet); box-shadow: 0 0 6px rgba(124,58,237,0.5); }
  .contrib-legend { display: flex; align-items: center; justify-content: flex-end; gap: 6px; margin-top: 12px; }
  .contrib-legend span { font-size: 11px; color: var(--silver); }
  .legend-cells { display: flex; gap: 3px; }
  .legend-cells .cell { width: 11px; height: 11px; }
  .contrib-stats { display: flex; gap: 24px; margin-top: 16px; padding-top: 16px; border-top: 1px solid var(--silver-dim); }
  .contrib-stat { font-size: 12.5px; color: var(--silver); }
  .contrib-stat strong { color: var(--ghost); font-weight: 600; }

  /* ── LANG BAR ── */
  .lang-section { margin-bottom: 52px; }
  .lang-bar-wrap {
    background: var(--slate);
    border: 1px solid var(--silver-dim);
    border-radius: 12px;
    padding: 24px;
  }
  .lang-bar { display: flex; border-radius: 6px; overflow: hidden; height: 8px; margin-bottom: 18px; gap: 2px; }
  .lang-seg { height: 100%; border-radius: 4px; }
  .lang-list { display: flex; flex-wrap: wrap; gap: 14px 28px; }
  .lang-item { display: flex; align-items: center; gap: 8px; font-size: 13px; }
  .lang-item .lang-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }
  .lang-name { color: var(--ghost); font-weight: 500; }
  .lang-pct { color: var(--silver); font-size: 12px; margin-left: 2px; }

  /* ── RECENT ACTIVITY ── */
  .activity-section { margin-bottom: 52px; }
  .activity-list { display: flex; flex-direction: column; gap: 0; }
  .activity-item {
    display: flex; gap: 16px; align-items: flex-start;
    padding: 16px 0;
    border-bottom: 1px solid rgba(61,61,82,0.5);
    transition: padding-left 0.2s;
  }
  .activity-item:last-child { border-bottom: none; }
  .activity-item:hover { padding-left: 6px; }
  .activity-icon {
    width: 32px; height: 32px; border-radius: 8px;
    background: var(--slate-2); border: 1px solid var(--silver-dim);
    display: flex; align-items: center; justify-content: center;
    font-size: 14px; flex-shrink: 0;
  }
  .activity-body { flex: 1; }
  .activity-title { font-size: 13.5px; color: var(--ghost); margin-bottom: 2px; }
  .activity-title a { color: var(--violet-soft); text-decoration: none; }
  .activity-title a:hover { text-decoration: underline; }
  .activity-meta { font-size: 12px; color: var(--silver); }
  .activity-time { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: var(--silver); flex-shrink: 0; margin-top: 2px; }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--silver-dim);
    padding-top: 28px;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 12px;
  }
  footer a { font-size: 12px; color: var(--silver); text-decoration: none; transition: color 0.2s; }
  footer a:hover { color: var(--ghost); }
  .footer-links { display: flex; gap: 18px; flex-wrap: wrap; }
  .footer-brand {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px; color: var(--silver-dim);
  }

  /* ── ANIMATED COUNTER ── */
  @keyframes countUp { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: none; } }
  .stat-num { animation: countUp 0.6s ease both; }

  /* ── RESPONSIVE ── */
  @media (max-width: 720px) {
    .hero { grid-template-columns: 1fr; gap: 28px; }
    .avatar-wrap { width: 120px; height: 120px; }
    .avatar-initial { width: 120px; height: 120px; font-size: 40px; }
    .display-name { font-size: 30px; }
    .pinned-grid { grid-template-columns: 1fr; }
    .stats-row { gap: 16px; }
  }

  @media (prefers-reduced-motion: reduce) {
    .aurora::before, .aurora::after, .avatar-wrap::before, .avatar-wrap::after,
    .status-dot, .repo-card { animation: none !important; transition: none !important; }
  }
</style>
</head>
<body>

<div class="aurora"></div>

<div class="page">

  <!-- NAV -->
  <nav>
    <a href="#" class="nav-logo">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z"/>
      </svg>
      GitHub
    </a>
    <div class="nav-links">
      <a href="#" class="active">Overview</a>
      <a href="#">Repositories <span style="font-size:11px;background:var(--slate-2);padding:1px 7px;border-radius:10px;margin-left:4px;">42</span></a>
      <a href="#">Projects</a>
      <a href="#">Packages</a>
      <a href="#">Stars</a>
    </div>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-col">
      <div class="avatar-wrap">
        <div class="avatar-initial">A</div>
      </div>
      <div class="status-badge">
        <span class="status-dot"></span>
        Open to work
      </div>
      <div class="btn-row">
        <button class="follow-btn primary">Follow</button>
        <button class="follow-btn">Sponsor ♥</button>
      </div>
      <button class="follow-btn">More ▾</button>
    </div>

    <div class="bio-col">
      <div class="eyebrow">Engineer & Creator</div>
      <h1 class="display-name">Aryan<br>Prasetyo</h1>
      <div class="handle">@aryan-dev</div>
      <p class="bio-text">
        Building infrastructure for the next generation of software. Obsessed with systems design, distributed computing, and developer experience. I ship things that last.
      </p>

      <div class="meta-list">
        <div class="meta-item">
          <svg width="15" height="15" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/><path stroke-linecap="round" stroke-linejoin="round" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/></svg>
          Jakarta, Indonesia
        </div>
        <div class="meta-item">
          <svg width="15" height="15" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9"/></svg>
          <a href="#">aryan.dev</a>
        </div>
        <div class="meta-item">
          <svg width="15" height="15" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/></svg>
          aryan@dev.io
        </div>
        <div class="meta-item">
          <svg width="15" height="15" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"/></svg>
          Joined March 2019
        </div>
      </div>

      <div class="stats-row">
        <div class="stat">
          <div class="stat-num">847</div>
          <div class="stat-label">followers</div>
        </div>
        <div class="stat">
          <div class="stat-num">312</div>
          <div class="stat-label">following</div>
        </div>
        <div class="stat">
          <div class="stat-num">2.4k</div>
          <div class="stat-label">stars earned</div>
        </div>
      </div>

      <div class="topics">
        <span class="topic v">TypeScript</span>
        <span class="topic b">Rust</span>
        <span class="topic g">Go</span>
        <span class="topic a">Kubernetes</span>
        <span class="topic v">React</span>
        <span class="topic b">PostgreSQL</span>
        <span class="topic g">GraphQL</span>
        <span class="topic a">Docker</span>
      </div>
    </div>
  </div>

  <!-- PINNED REPOS -->
  <div class="pinned-section">
    <div class="section-head">
      <span class="section-title">Pinned Repositories</span>
      <a href="#" class="section-link">Customize pins →</a>
    </div>
    <div class="pinned-grid">

      <div class="repo-card">
        <div class="repo-top">
          <div class="repo-icon">⚡</div>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-name">⌥ flux-engine</div>
        <p class="repo-desc">A high-performance event streaming engine built in Rust. Handles 1M+ events/sec with sub-ms latency.</p>
        <div class="repo-footer">
          <div class="repo-lang"><span class="lang-dot" style="background:#DEA584;"></span>Rust</div>
          <div class="repo-stars">⭐ 892</div>
          <div class="repo-stars star-fork">⑂ 124</div>
        </div>
      </div>

      <div class="repo-card">
        <div class="repo-top">
          <div class="repo-icon">🧬</div>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-name">⌥ nebula-ui</div>
        <p class="repo-desc">Design system built for scale. 80+ components, dark-first, fully accessible, zero-dependency.</p>
        <div class="repo-footer">
          <div class="repo-lang"><span class="lang-dot" style="background:#3178C6;"></span>TypeScript</div>
          <div class="repo-stars">⭐ 647</div>
          <div class="repo-stars star-fork">⑂ 89</div>
        </div>
      </div>

      <div class="repo-card">
        <div class="repo-top">
          <div class="repo-icon">🔭</div>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-name">⌥ k8s-autopilot</div>
        <p class="repo-desc">Kubernetes operator for auto-scaling ML workloads. Plugs into Prometheus metrics natively.</p>
        <div class="repo-footer">
          <div class="repo-lang"><span class="lang-dot" style="background:#00ADD8;"></span>Go</div>
          <div class="repo-stars">⭐ 415</div>
          <div class="repo-stars star-fork">⑂ 67</div>
        </div>
      </div>

      <div class="repo-card">
        <div class="repo-top">
          <div class="repo-icon">🌐</div>
          <span class="repo-badge">Public</span>
        </div>
        <div class="repo-name">⌥ graphsync</div>
        <p class="repo-desc">Real-time GraphQL subscriptions over WebSocket with automatic reconnect and offline queueing.</p>
        <div class="repo-footer">
          <div class="repo-lang"><span class="lang-dot" style="background:#3178C6;"></span>TypeScript</div>
          <div class="repo-stars">⭐ 238</div>
          <div class="repo-stars star-fork">⑂ 41</div>
        </div>
      </div>

    </div>
  </div>

  <!-- CONTRIBUTION GRAPH -->
  <div class="contrib-section">
    <div class="section-head">
      <span class="section-title">Contribution Activity</span>
      <a href="#" class="section-link">2026 ▾</a>
    </div>
    <div class="contrib-grid">
      <div class="contrib-months">
        <span class="contrib-month">Jan</span>
        <span class="contrib-month">Feb</span>
        <span class="contrib-month">Mar</span>
        <span class="contrib-month">Apr</span>
        <span class="contrib-month">May</span>
        <span class="contrib-month">Jun</span>
      </div>
      <div class="cells" id="cells"></div>
      <div class="contrib-legend">
        <span>Less</span>
        <div class="legend-cells">
          <div class="cell"></div>
          <div class="cell l1"></div>
          <div class="cell l2"></div>
          <div class="cell l3"></div>
          <div class="cell l4"></div>
        </div>
        <span>More</span>
      </div>
      <div class="contrib-stats">
        <div class="contrib-stat"><strong>1,842</strong> contributions in 2026</div>
        <div class="contrib-stat"><strong>47</strong> day streak</div>
        <div class="contrib-stat">Longest streak: <strong>89</strong> days</div>
      </div>
    </div>
  </div>

  <!-- LANG BAR -->
  <div class="lang-section">
    <div class="section-head">
      <span class="section-title">Most Used Languages</span>
    </div>
    <div class="lang-bar-wrap">
      <div class="lang-bar">
        <div class="lang-seg" style="width:38%;background:#3178C6;"></div>
        <div class="lang-seg" style="width:26%;background:#DEA584;"></div>
        <div class="lang-seg" style="width:18%;background:#00ADD8;"></div>
        <div class="lang-seg" style="width:10%;background:#89e051;"></div>
        <div class="lang-seg" style="width:8%;background:#f1e05a;"></div>
      </div>
      <div class="lang-list">
        <div class="lang-item"><span class="lang-dot" style="background:#3178C6;"></span><span class="lang-name">TypeScript</span><span class="lang-pct">38.2%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#DEA584;"></span><span class="lang-name">Rust</span><span class="lang-pct">25.6%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#00ADD8;"></span><span class="lang-name">Go</span><span class="lang-pct">18.1%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#89e051;"></span><span class="lang-name">Shell</span><span class="lang-pct">10.4%</span></div>
        <div class="lang-item"><span class="lang-dot" style="background:#f1e05a;"></span><span class="lang-name">JavaScript</span><span class="lang-pct">7.7%</span></div>
      </div>
    </div>
  </div>

  <!-- RECENT ACTIVITY -->
  <div class="activity-section">
    <div class="section-head">
      <span class="section-title">Recent Activity</span>
    </div>
    <div class="activity-list">

      <div class="activity-item">
        <div class="activity-icon">⭐</div>
        <div class="activity-body">
          <div class="activity-title">Starred <a href="#">vercel/turborepo</a> — Monorepo build system for JS & TS</div>
          <div class="activity-meta">Public repository · 24k stars</div>
        </div>
        <div class="activity-time">2h ago</div>
      </div>

      <div class="activity-item">
        <div class="activity-icon">🔀</div>
        <div class="activity-body">
          <div class="activity-title">Merged PR <a href="#">#284 — feat: add connection pooling</a> in <a href="#">flux-engine</a></div>
          <div class="activity-meta">3 files changed · +142 −28</div>
        </div>
        <div class="activity-time">5h ago</div>
      </div>

      <div class="activity-item">
        <div class="activity-icon">💬</div>
        <div class="activity-body">
          <div class="activity-title">Commented on <a href="#">#401 — Support for custom serializers</a> in <a href="#">graphsync</a></div>
          <div class="activity-meta">"This is the right approach — using MessagePack here makes sense given the binary protocol."</div>
        </div>
        <div class="activity-time">1d ago</div>
      </div>

      <div class="activity-item">
        <div class="activity-icon">📦</div>
        <div class="activity-body">
          <div class="activity-title">Released <a href="#">nebula-ui v2.4.0</a></div>
          <div class="activity-meta">New: DateRangePicker, Command Palette, and 12 bug fixes</div>
        </div>
        <div class="activity-time">2d ago</div>
      </div>

      <div class="activity-item">
        <div class="activity-icon">🍴</div>
        <div class="activity-body">
          <div class="activity-title">Forked <a href="#">tokio-rs/tokio</a> — Async runtime for Rust</div>
          <div class="activity-meta">Experimenting with custom task schedulers</div>
        </div>
        <div class="activity-time">3d ago</div>
      </div>

    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="footer-links">
      <a href="#">Terms</a>
      <a href="#">Privacy</a>
      <a href="#">Security</a>
      <a href="#">Status</a>
      <a href="#">Docs</a>
      <a href="#">Contact</a>
    </div>
    <div class="footer-brand">GitHub, Inc. © 2026</div>
  </footer>

</div>

<script>
  // Generate contribution cells
  const container = document.getElementById('cells');
  const levels = [0,0,0,1,1,2,2,3,4];
  const weeks = 26;
  for (let w = 0; w < weeks; w++) {
    const col = document.createElement('div');
    col.className = 'cell-col';
    for (let d = 0; d < 7; d++) {
      const cell = document.createElement('div');
      const lvl = levels[Math.floor(Math.random() * levels.length)];
      cell.className = 'cell' + (lvl ? ' l' + lvl : '');
      col.appendChild(cell);
    }
    container.appendChild(col);
  }

  // Animated counter
  function animateCount(el, target, suffix='') {
    let start = 0;
    const duration = 1200;
    const step = timestamp => {
      if (!start) start = timestamp;
      const progress = Math.min((timestamp - start) / duration, 1);
      const val = Math.floor(progress * target);
      el.textContent = val.toLocaleString() + suffix;
      if (progress < 1) requestAnimationFrame(step);
      else el.textContent = target.toLocaleString() + suffix;
    };
    requestAnimationFrame(step);
  }

  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        const nums = document.querySelectorAll('.stat-num');
        const vals = [847, 312, 2400];
        const sfx = ['','',''];
        nums.forEach((el, i) => {
          if (i === 2) animateCount(el, 2.4, 'k');
          else animateCount(el, vals[i]);
        });
        observer.disconnect();
      }
    });
  }, { threshold: 0.3 });

  const statsEl = document.querySelector('.stats-row');
  if (statsEl) observer.observe(statsEl);

  // 3D tilt on cards
  document.querySelectorAll('.repo-card').forEach(card => {
    card.addEventListener('mousemove', e => {
      const r = card.getBoundingClientRect();
      const x = e.clientX - r.left - r.width / 2;
      const y = e.clientY - r.top - r.height / 2;
      card.style.transform = `translateY(-3px) rotateY(${x * 0.015}deg) rotateX(${-y * 0.015}deg)`;
    });
    card.addEventListener('mouseleave', () => {
      card.style.transform = '';
    });
  });
</script>
</body>
</html>
