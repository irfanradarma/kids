<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🎮 Kids Game Zone!</title>
  <link href="https://fonts.googleapis.com/css2?family=Boogaloo&family=Quicksand:wght@500;700&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #0d0d1a;
      --surface: #13132a;
      --border: rgba(255,255,255,0.08);
      --white: #ffffff;
      --muted: rgba(255,255,255,0.55);

      --g1: #ff5e78;
      --g2: #00d4b4;
      --g3: #ffd44f;
      --g4: #a78bfa;

      --glow1: rgba(255,94,120,0.35);
      --glow2: rgba(0,212,180,0.35);
      --glow3: rgba(255,212,79,0.35);
      --glow4: rgba(167,139,250,0.35);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: 'Quicksand', sans-serif;
      background: var(--bg);
      min-height: 100vh;
      overflow-x: hidden;
      cursor: default;
    }

    /* ---- STARS ---- */
    #stars {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
    }
    .star {
      position: absolute;
      background: #fff;
      border-radius: 50%;
      animation: twinkle var(--d, 3s) ease-in-out infinite alternate;
    }
    @keyframes twinkle {
      from { opacity: 0.15; transform: scale(1); }
      to   { opacity: 0.9;  transform: scale(1.5); }
    }

    /* ---- SHOOTING STAR ---- */
    .shoot {
      position: fixed;
      width: 120px;
      height: 2px;
      background: linear-gradient(90deg, rgba(255,255,255,0.8), transparent);
      border-radius: 2px;
      animation: shoot var(--sd, 4s) var(--ss, 2s) linear infinite;
      opacity: 0;
      z-index: 0;
      pointer-events: none;
    }
    @keyframes shoot {
      0%   { opacity: 0; transform: translateX(-120px) rotate(-20deg); }
      5%   { opacity: 1; }
      50%  { opacity: 0; transform: translateX(110vw) rotate(-20deg); }
      100% { opacity: 0; transform: translateX(110vw) rotate(-20deg); }
    }

    /* ---- LAYOUT ---- */
    .wrap {
      position: relative;
      z-index: 1;
      max-width: 800px;
      margin: 0 auto;
      padding: 48px 20px 80px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 48px;
    }

    /* ---- HEADER ---- */
    .header {
      text-align: center;
      animation: fadeDown 0.6s ease both;
    }

    .planet-ring {
      position: relative;
      display: inline-block;
      margin-bottom: 16px;
    }
    .planet-ring .p {
      font-size: clamp(56px, 12vw, 80px);
      display: block;
      animation: bob 3.5s ease-in-out infinite;
      line-height: 1;
    }
    @keyframes bob {
      0%,100% { transform: translateY(0) rotate(-5deg); }
      50%      { transform: translateY(-14px) rotate(5deg); }
    }

    /* Orbiting mini planet */
    .orbit {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 90px;
      height: 90px;
      margin: -45px 0 0 -45px;
      animation: spin 6s linear infinite;
      pointer-events: none;
    }
    .orbit-dot {
      position: absolute;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      font-size: 18px;
    }
    @keyframes spin {
      from { transform: rotate(0deg); }
      to   { transform: rotate(360deg); }
    }

    h1 {
      font-family: 'Boogaloo', cursive;
      font-size: clamp(2.4rem, 9vw, 4.2rem);
      color: var(--white);
      letter-spacing: 1px;
      line-height: 1;
    }
    .tagline {
      margin-top: 10px;
      color: var(--muted);
      font-size: clamp(0.95rem, 2.5vw, 1.1rem);
      font-weight: 700;
    }

    /* ---- GAME LIST ---- */
    .game-list {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    /* ---- GAME CARD ---- */
    .card {
      display: flex;
      align-items: center;
      gap: 20px;
      background: var(--surface);
      border: 2px solid var(--border);
      border-radius: 24px;
      padding: 20px 24px;
      text-decoration: none;
      position: relative;
      overflow: hidden;
      transition:
        transform 0.22s cubic-bezier(.34,1.56,.64,1),
        border-color 0.22s ease,
        box-shadow 0.22s ease;
      animation: slideIn 0.5s ease both;
      cursor: pointer;
      -webkit-tap-highlight-color: transparent;
    }

    .card:nth-child(1) { animation-delay: 0.1s; --accent: var(--g1); --glow: var(--glow1); }
    .card:nth-child(2) { animation-delay: 0.2s; --accent: var(--g2); --glow: var(--glow2); }
    .card:nth-child(3) { animation-delay: 0.3s; --accent: var(--g3); --glow: var(--glow3); }

    /* Accent left bar */
    .card::before {
      content: '';
      position: absolute;
      left: 0; top: 12px; bottom: 12px;
      width: 4px;
      border-radius: 4px;
      background: var(--accent);
      transition: height 0.2s ease;
    }

    /* Glow sweep on hover */
    .card::after {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at 20% 50%, var(--glow) 0%, transparent 65%);
      opacity: 0;
      transition: opacity 0.3s ease;
      pointer-events: none;
    }

    @media (hover: hover) {
      .card:hover {
        transform: translateX(8px) scale(1.02);
        border-color: var(--accent);
        box-shadow: 0 8px 32px var(--glow);
      }
      .card:hover::after { opacity: 1; }
      .card:hover .go-btn { background: var(--accent); color: #000; transform: scale(1.1); }
      .card:hover .go-btn .arrow { transform: translateX(3px); }
    }

    /* Active press (touch) */
    .card:active {
      transform: scale(0.98);
    }

    /* Emoji bubble */
    .emoji-bubble {
      width: 64px;
      height: 64px;
      min-width: 64px;
      border-radius: 18px;
      background: rgba(255,255,255,0.06);
      border: 1.5px solid rgba(255,255,255,0.1);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 32px;
      transition: transform 0.3s cubic-bezier(.34,1.56,.64,1);
      flex-shrink: 0;
    }
    .card:hover .emoji-bubble,
    .card:active .emoji-bubble {
      transform: scale(1.15) rotate(-6deg);
    }

    .card-body {
      flex: 1;
      min-width: 0;
    }
    .card-tag {
      font-size: 0.68rem;
      font-weight: 700;
      letter-spacing: 1.2px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 4px;
    }
    .card-title {
      font-family: 'Boogaloo', cursive;
      font-size: clamp(1.25rem, 4vw, 1.6rem);
      color: var(--white);
      line-height: 1.1;
      margin-bottom: 4px;
    }
    .card-desc {
      font-size: 0.82rem;
      font-weight: 500;
      color: var(--muted);
      line-height: 1.45;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    /* GO button */
    .go-btn {
      flex-shrink: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 4px;
      width: 52px;
      height: 44px;
      border-radius: 14px;
      background: rgba(255,255,255,0.08);
      color: var(--white);
      font-family: 'Boogaloo', cursive;
      font-size: 1rem;
      letter-spacing: 0.5px;
      border: 1.5px solid rgba(255,255,255,0.1);
      transition:
        background 0.2s ease,
        transform 0.2s cubic-bezier(.34,1.56,.64,1),
        color 0.2s ease;
      white-space: nowrap;
    }
    .arrow {
      display: inline-block;
      transition: transform 0.2s ease;
      font-size: 1.1rem;
    }

    /* ---- COMING SOON ---- */
    .card.soon {
      opacity: 0.5;
      pointer-events: none;
    }
    .badge-soon {
      position: absolute;
      top: 12px; right: 12px;
      font-size: 0.6rem;
      font-weight: 700;
      letter-spacing: 1px;
      text-transform: uppercase;
      background: rgba(255,255,255,0.12);
      color: rgba(255,255,255,0.5);
      padding: 3px 9px;
      border-radius: 99px;
    }

    /* ---- QUICK NAV DOTS ---- */
    .nav-dots {
      display: flex;
      gap: 10px;
      align-items: center;
      justify-content: center;
      animation: fadeUp 0.6s ease 0.5s both;
    }
    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      opacity: 0.3;
      transition: all 0.2s ease;
      cursor: pointer;
      border: none;
      padding: 0;
    }
    .dot.g1 { background: var(--g1); }
    .dot.g2 { background: var(--g2); }
    .dot.g3 { background: var(--g3); }
    .dot:hover { opacity: 1; transform: scale(1.4); }

    /* ---- FOOTER ---- */
    .footer {
      color: rgba(255,255,255,0.22);
      font-size: 0.8rem;
      font-weight: 600;
      text-align: center;
    }
    .footer a { color: rgba(120,180,255,0.6); text-decoration: none; }

    /* ---- ANIMATIONS ---- */
    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes slideIn {
      from { opacity: 0; transform: translateX(-24px); }
      to   { opacity: 1; transform: translateX(0); }
    }

    /* Mobile tweaks */
    @media (max-width: 480px) {
      .card { padding: 16px; gap: 14px; }
      .emoji-bubble { width: 52px; height: 52px; min-width: 52px; font-size: 26px; border-radius: 14px; }
      .go-btn { width: 44px; height: 40px; font-size: 0.9rem; }
      .card-desc { display: none; }
    }
  </style>
</head>
<body>

<div id="stars"></div>

<div class="wrap">

  <!-- HEADER -->
  <header class="header">
    <div class="planet-ring">
      <span class="p">🪐</span>
      <div class="orbit"><span class="orbit-dot">⭐</span></div>
    </div>
    <h1>Kids Game Zone</h1>
    <p class="tagline">Pilih game favoritmu dan mulai petualangan! 🚀</p>
  </header>

  <!-- GAME LIST -->
  <div class="game-list" role="list">

    <a class="card" href="rocketman.html" role="listitem" aria-label="Main Apollo Exploration">
      <div class="emoji-bubble" aria-hidden="true">🚀</div>
      <div class="card-body">
        <div class="card-tag">Logic &amp; Coding</div>
        <div class="card-title">Apollo Exploration</div>
        <div class="card-desc">Susun perintah dan selesaikan labirin luar angkasa!</div>
      </div>
      <div class="go-btn" aria-hidden="true">
        <span class="arrow">→</span>
      </div>
    </a>

    <a class="card" href="gravity.html" role="listitem" aria-label="Main Ball Drop">
      <div class="emoji-bubble" aria-hidden="true">🌊</div>
      <div class="card-body">
        <div class="card-tag">Physics Puzzle</div>
        <div class="card-title">Ball Drop</div>
        <div class="card-desc">Atur gravitasi dan selesaikan tiap level dengan strategi!</div>
      </div>
      <div class="go-btn" aria-hidden="true">
        <span class="arrow">→</span>
      </div>
    </a>

    <a class="card" href="flag.html" role="listitem" aria-label="Main Flag Guess">
      <div class="emoji-bubble" aria-hidden="true">🌎</div>
      <div class="card-body">
        <div class="card-tag">General Knowledge</div>
        <div class="card-title">Flag Guess</div>
        <div class="card-desc">Tebak nama negara dari benderanya — seberapa jauh kamu tahu?</div>
      </div>
      <div class="go-btn" aria-hidden="true">
        <span class="arrow">→</span>
      </div>
    </a>

  </div>

  <!-- NAV DOTS (decorative scroll cue) -->
  <nav class="nav-dots" aria-label="Game shortcuts">
    <button class="dot g1" onclick="document.querySelectorAll('.card')[0].focus()" title="Apollo Exploration"></button>
    <button class="dot g2" onclick="document.querySelectorAll('.card')[1].focus()" title="Ball Drop"></button>
    <button class="dot g3" onclick="document.querySelectorAll('.card')[2].focus()" title="Flag Guess"></button>
  </nav>

  <footer class="footer">
    Made with ❤️ for kids &nbsp;·&nbsp;
    <a href="https://github.com/irfanradarma/kids" target="_blank">View on GitHub</a>
  </footer>

</div>

<script>
  /* Stars */
  function makeStars() {
    const c = document.getElementById('stars');
    c.innerHTML = '';
    const n = window.innerWidth > 1024 ? 180 : window.innerWidth > 600 ? 110 : 60;
    for (let i = 0; i < n; i++) {
      const s = document.createElement('div');
      s.className = 'star';
      const sz = Math.random() * 2.2 + 0.4;
      s.style.cssText = `width:${sz}px;height:${sz}px;top:${Math.random()*100}%;left:${Math.random()*100}%;--d:${(Math.random()*3+1.5).toFixed(1)}s;animation-delay:${(Math.random()*4).toFixed(1)}s`;
      c.appendChild(s);
    }
  }
  makeStars();
  let rt; window.addEventListener('resize', () => { clearTimeout(rt); rt = setTimeout(makeStars, 250); });

  /* Shooting stars */
  for (let i = 0; i < 3; i++) {
    const sh = document.createElement('div');
    sh.className = 'shoot';
    sh.style.cssText = `top:${15 + i*25}%;left:0;--sd:${5+i*3}s;--ss:${i*4}s`;
    document.body.appendChild(sh);
  }

  /* Card focus scroll for dot nav */
  document.querySelectorAll('.card').forEach(card => {
    card.addEventListener('focus', () => card.scrollIntoView({ behavior: 'smooth', block: 'center' }));
  });
</script>
</body>
</html>