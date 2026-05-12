<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🎮 Kids Games!</title>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --sky: #1a1a2e;
      --deep: #16213e;
      --card1: #ff6b6b;
      --card2: #4ecdc4;
      --card3: #ffe66d;
      --card4: #a29bfe;
      --white: #ffffff;
      --soft: #f8f9fa;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: 'Nunito', sans-serif;
      background: var(--sky);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ---- STARS ---- */
    .stars {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
    }
    .star {
      position: absolute;
      background: white;
      border-radius: 50%;
      animation: twinkle var(--d, 3s) infinite alternate;
    }
    @keyframes twinkle {
      from { opacity: 0.2; transform: scale(1); }
      to   { opacity: 1;   transform: scale(1.4); }
    }

    /* ---- RESPONSIVE LAYOUT ---- */
    .container {
      position: relative;
      z-index: 1;
      max-width: 1200px; /* Increased for wider desktop view */
      margin: 0 auto;
      padding: 20px;
    }

    @media (min-width: 768px) {
      .container { padding: 40px 40px 80px; }
    }

    /* ---- HEADER ---- */
    .header {
      text-align: center;
      margin-bottom: 40px;
      animation: fadeDown 0.7s ease both;
    }

    .header .planet {
      font-size: clamp(50px, 10vw, 72px); /* Dynamic size */
      display: inline-block;
      animation: bob 3s ease-in-out infinite;
      filter: drop-shadow(0 0 24px rgba(255,200,60,0.5));
    }

    @keyframes bob {
      0%, 100% { transform: translateY(0); }
      50%       { transform: translateY(-12px); }
    }

    .header h1 {
      font-family: 'Fredoka One', cursive;
      font-size: clamp(2rem, 8vw, 4rem);
      color: var(--white);
      letter-spacing: 1px;
      margin-top: 8px;
      text-shadow: 0 4px 20px rgba(255,230,100,0.4);
    }

    .header p {
      color: #b2bec3;
      font-size: clamp(0.9rem, 2vw, 1.1rem);
      font-weight: 600;
      margin-top: 8px;
    }

    /* ---- DYNAMIC GRID ---- */
    .games-grid {
      display: grid;
      /* Adapts from 1 column on mobile to multiple on desktop */
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); 
      gap: 20px;
    }

    @media (min-width: 1024px) {
      .games-grid { gap: 32px; }
    }

    /* ---- CARD ---- */
    .card {
      border-radius: 24px;
      padding: 24px;
      text-decoration: none;
      display: flex;
      flex-direction: column;
      gap: 12px;
      position: relative;
      overflow: hidden;
      transition: transform 0.25s cubic-bezier(.34,1.56,.64,1), box-shadow 0.25s ease;
      animation: fadeUp 0.6s ease both;
      cursor: pointer;
    }

    /* Desktop hover effects only on pointing devices */
    @media (hover: hover) {
      .card:hover {
        transform: translateY(-8px) scale(1.02);
        box-shadow: 0 24px 56px rgba(0,0,0,0.35);
      }
      .card:hover .card-cta { background: #fff; }
      .card:hover .card-cta .arrow { transform: translateX(4px); }
    }

    .card:nth-child(1) { background: var(--card1); animation-delay: 0.1s; }
    .card:nth-child(2) { background: var(--card2); animation-delay: 0.2s; }
    .card:nth-child(3) { background: var(--card3); animation-delay: 0.3s; }
    .card:nth-child(4) { background: var(--card4); animation-delay: 0.4s; }

    /* Decorative blob */
    .card::before {
      content: '';
      position: absolute;
      width: 150px;
      height: 150px;
      background: rgba(255,255,255,0.12);
      border-radius: 50%;
      top: -40px;
      right: -30px;
      pointer-events: none;
    }

    .card-emoji {
      font-size: 48px;
      line-height: 1;
      filter: drop-shadow(2px 4px 8px rgba(0,0,0,0.2));
    }

    .card-tag {
      font-family: 'Fredoka One', cursive;
      font-size: 0.7rem;
      letter-spacing: 1px;
      text-transform: uppercase;
      background: rgba(0,0,0,0.18);
      color: rgba(255,255,255,0.9);
      padding: 4px 12px;
      border-radius: 99px;
      width: fit-content;
    }

    .card h2 {
      font-family: 'Fredoka One', cursive;
      font-size: 1.6rem;
      color: var(--white);
      line-height: 1.1;
    }

    .card p {
      font-size: 0.9rem;
      font-weight: 700;
      color: rgba(255,255,255,0.85);
      line-height: 1.5;
      flex: 1;
    }

    .card-cta {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(255,255,255,0.9);
      color: #333;
      font-family: 'Fredoka One', cursive;
      font-size: 0.9rem;
      padding: 10px 18px;
      border-radius: 99px;
      width: fit-content;
      margin-top: 8px;
    }

    /* ---- FOOTER ---- */
    .footer {
      text-align: center;
      margin-top: 60px;
      color: #636e72;
      font-size: 0.85rem;
      font-weight: 700;
      padding-bottom: 20px;
    }
    .footer a { color: #74b9ff; text-decoration: none; }

    /* ---- ANIMATIONS ---- */
    @keyframes fadeDown {
      from { opacity: 0; transform: translateY(-20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>

<div class="stars" id="stars"></div>

<div class="container">
  <header class="header">
    <div class="planet">🪐</div>
    <h1>Kids Game Zone</h1>
    <p>Pilih game dan mulai bermain! 🎉</p>
  </header>

  <div class="games-grid">
    <!-- Game 1 -->
    <a class="card" href="rocketman.html">
      <div class="card-emoji">🚀</div>
      <span class="card-tag">Logic &amp; Coding</span>
      <h2>Apollo Exploration</h2>
      <p>Bantu roket menemukan jalan ke bumi! Susun perintah dengan benar dan selesaikan labirin luar angkasa.</p>
      <div class="card-cta">Main Sekarang <span class="arrow">→</span></div>
    </a>

    <!-- Game 2 -->
    <a class="card" href="gravity.html">
      <div class="card-emoji">🌊</div>
      <span class="card-tag">Physics Puzzle</span>
      <h2>Ball Drop</h2>
      <p>Jatuhkan blok dan atur gravitasi! Selesaikan tiap level dengan strategi yang tepat.</p>
      <div class="card-cta">Main Sekarang <span class="arrow">→</span></div>
    </a>

    <!-- Game 3 -->
    <a class="card" href="flag.html">
      <div class="card-emoji">🌎</div>
      <span class="card-tag">General Knowledge</span>
      <h2>Flag Guess</h2>
      <p>Tebak nama negara dari benderanya</p>
      <div class="card-cta">Main Sekarang <span class="arrow">→</span></div>
    </a>
  </div>

  <footer class="footer">
    Made with ❤️ for kids &nbsp;·&nbsp;
    <a href="https://github.com/irfanradarma/kids" target="_blank">View on GitHub</a>
  </footer>
</div>

<script>
  // Dynamic Star Generation based on screen area
  function generateStars() {
    const container = document.getElementById('stars');
    container.innerHTML = ''; // Clear existing stars
    
    // Determine number of stars based on screen width
    const screenWidth = window.innerWidth;
    let starCount = 60; // Mobile
    if (screenWidth > 768) starCount = 120; // Tablet
    if (screenWidth > 1200) starCount = 200; // Desktop

    for (let i = 0; i < starCount; i++) {
      const s = document.createElement('div');
      s.className = 'star';
      const size = Math.random() * 2.5 + 0.5;
      s.style.cssText = `
        width:${size}px; height:${size}px;
        top:${Math.random()*100}%;
        left:${Math.random()*100}%;
        --d:${(Math.random()*3+1.5).toFixed(1)}s;
        animation-delay:${(Math.random()*3).toFixed(1)}s;
      `;
      container.appendChild(s);
    }
  }

  // Initial load
  generateStars();

  // Refresh stars on window resize to ensure full coverage
  let resizeTimer;
  window.addEventListener('resize', () => {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(generateStars, 250);
  });
</script>
</body>
</html>