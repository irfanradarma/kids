<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>🪐 Kids Game Zone</title>
  <link href="https://fonts.googleapis.com/css2?family=Boogaloo&family=Baloo+2:wght@500;700;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg:#070714; --surface:#0f0f24; --border:rgba(255,255,255,0.07);
      --white:#fff; --muted:rgba(255,255,255,0.50);
      --c1:#ff4d6d; --c1g:rgba(255,77,109,0.28);
      --c2:#00cfb4; --c2g:rgba(0,207,180,0.28);
      --c3:#ffc43d; --c3g:rgba(255,196,61,0.28);
      --spring:cubic-bezier(0.34,1.56,0.64,1);
      --ease:cubic-bezier(0.25,0.46,0.45,0.94);
    }
    *,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
    html,body{width:100%;height:100%;overflow:hidden;font-family:'Baloo 2',cursive;background:var(--bg);color:var(--white);}

    /* ── COSMOS ── */
    #cosmos{position:fixed;inset:0;z-index:0;pointer-events:none;overflow:hidden;}
    .nebula{position:absolute;border-radius:50%;filter:blur(90px);opacity:0.16;animation:nebFloat var(--nd,18s) ease-in-out infinite alternate;}
    .neb1{width:650px;height:420px;background:#5533ff;top:-120px;left:-160px;--nd:20s;}
    .neb2{width:500px;height:360px;background:#ff3366;bottom:-90px;right:-120px;--nd:17s;}
    .neb3{width:380px;height:280px;background:#00ffcc;top:35%;left:58%;--nd:23s;}
    @keyframes nebFloat{from{transform:translate(0,0) scale(1);}to{transform:translate(28px,18px) scale(1.07);}}
    .star{position:absolute;border-radius:50%;background:#fff;animation:twinkle var(--d,3s) ease-in-out infinite alternate;}
    @keyframes twinkle{from{opacity:0.1;transform:scale(1);}to{opacity:0.92;transform:scale(1.7);}}
    .shoot{position:absolute;height:2px;background:linear-gradient(90deg,rgba(255,255,255,0.85),transparent);border-radius:2px;opacity:0;animation:shoot var(--sd,6s) var(--ss,0s) linear infinite;}
    @keyframes shoot{0%{width:0;opacity:0;transform:translateX(0) rotate(-18deg);}5%{opacity:1;}20%{width:160px;}40%{opacity:0;transform:translateX(60vw) rotate(-18deg);width:160px;}100%{opacity:0;transform:translateX(60vw) rotate(-18deg);}}

    /* ── HUB ── */
    #hub{position:fixed;inset:0;z-index:10;display:flex;flex-direction:column;align-items:center;overflow-y:auto;overflow-x:hidden;padding:36px 16px 64px;transition:opacity 0.4s var(--ease),transform 0.4s var(--ease);}
    #hub.hiding{opacity:0;transform:scale(0.93) translateY(-14px);pointer-events:none;}

    .hub-header{text-align:center;margin-bottom:28px;animation:dropIn 0.7s var(--spring) both;}
    .mascot-wrap{position:relative;display:inline-block;margin-bottom:10px;}
    .mascot{font-size:clamp(58px,13vw,86px);display:block;line-height:1;animation:planetBob 5s ease-in-out infinite;filter:drop-shadow(0 0 30px rgba(120,100,255,0.55));}
    @keyframes planetBob{0%,100%{transform:rotate(-7deg) translateY(0);}25%{transform:rotate(0deg) translateY(-12px);}50%{transform:rotate(7deg) translateY(-18px);}75%{transform:rotate(0deg) translateY(-12px);}}
    .orbit-ring{position:absolute;top:50%;left:50%;width:104px;height:104px;margin:-52px 0 0 -52px;animation:orbitSpin 4s linear infinite;pointer-events:none;}
    .orbit-star{position:absolute;top:-5px;left:50%;transform:translateX(-50%);font-size:20px;}
    @keyframes orbitSpin{to{transform:rotate(360deg);}}
    .hub-title{font-family:'Boogaloo',cursive;font-size:clamp(2.6rem,10vw,4.6rem);color:var(--white);line-height:1;letter-spacing:1px;text-shadow:0 0 50px rgba(150,120,255,0.45);}
    .hub-sub{margin-top:8px;font-size:clamp(0.95rem,2.5vw,1.15rem);font-weight:500;color:var(--muted);}

    /* score pills */
    .score-strip{display:flex;gap:10px;flex-wrap:wrap;justify-content:center;margin-bottom:26px;animation:dropIn 0.7s var(--spring) 0.12s both;}
    .score-pill{display:flex;align-items:center;gap:7px;padding:6px 16px;background:rgba(255,255,255,0.06);border:1.5px solid rgba(255,255,255,0.10);border-radius:999px;font-size:0.82rem;font-weight:700;color:var(--muted);}
    .sp-val{font-size:1rem;font-weight:800;color:var(--white);}

    /* cards */
    .cards-wrap{width:100%;max-width:780px;display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px;}

    .game-card{position:relative;overflow:hidden;border-radius:28px;border:2px solid var(--border);background:var(--surface);cursor:pointer;text-decoration:none;display:flex;flex-direction:column;transition:transform 0.28s var(--spring),border-color 0.25s,box-shadow 0.25s;animation:cardUp 0.6s var(--spring) both;-webkit-tap-highlight-color:transparent;outline:none;user-select:none;}
    .game-card:nth-child(1){--accent:var(--c1);--glow:var(--c1g);animation-delay:0.15s;}
    .game-card:nth-child(2){--accent:var(--c2);--glow:var(--c2g);animation-delay:0.25s;}
    .game-card:nth-child(3){--accent:var(--c3);--glow:var(--c3g);animation-delay:0.35s;}
    .game-card::before{content:'';position:absolute;inset:0;z-index:0;background:radial-gradient(ellipse at 28% 40%,var(--glow) 0%,transparent 60%);opacity:0;transition:opacity 0.35s;pointer-events:none;}
    .game-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:4px;background:var(--accent);transform:scaleX(0);transform-origin:left;transition:transform 0.35s var(--spring);}
    @media(hover:hover){
      .game-card:hover{transform:translateY(-10px) scale(1.03);border-color:var(--accent);box-shadow:0 16px 50px var(--glow),0 0 0 1px var(--accent);}
      .game-card:hover::before{opacity:1;}
      .game-card:hover::after{transform:scaleX(1);}
      .game-card:hover .card-emoji-bg{transform:rotate(-8deg) scale(1.14);}
      .game-card:hover .card-go{background:var(--accent);color:#000;transform:scale(1.12);}
    }
    .game-card:active{transform:scale(0.97);}

    .card-art{position:relative;z-index:1;display:flex;align-items:center;justify-content:center;padding:26px 20px 14px;}
    .card-emoji-bg{width:88px;height:88px;border-radius:22px;background:rgba(255,255,255,0.05);border:2px solid rgba(255,255,255,0.09);display:flex;align-items:center;justify-content:center;font-size:44px;transition:transform 0.3s var(--spring);}
    .card-body{position:relative;z-index:1;padding:0 20px 20px;flex:1;display:flex;flex-direction:column;gap:5px;}
    .card-genre{font-size:0.65rem;font-weight:700;letter-spacing:1.4px;text-transform:uppercase;color:var(--accent);}
    .card-name{font-family:'Boogaloo',cursive;font-size:clamp(1.3rem,4vw,1.75rem);color:var(--white);line-height:1.05;}
    .card-desc{font-size:0.82rem;font-weight:500;color:var(--muted);line-height:1.5;flex:1;}
    .card-footer{display:flex;align-items:center;justify-content:space-between;margin-top:10px;}
    .card-badge{font-size:0.62rem;font-weight:700;letter-spacing:0.8px;text-transform:uppercase;padding:4px 10px;border-radius:999px;background:rgba(255,255,255,0.07);color:rgba(255,255,255,0.45);border:1px solid rgba(255,255,255,0.10);}
    .card-go{width:42px;height:42px;border-radius:14px;background:rgba(255,255,255,0.08);border:1.5px solid rgba(255,255,255,0.13);display:flex;align-items:center;justify-content:center;font-size:1.2rem;transition:background 0.22s,transform 0.22s var(--spring),color 0.22s;}

    /* teaser */
    .teaser{margin-top:10px;width:100%;max-width:780px;padding:16px 20px;background:rgba(255,255,255,0.03);border:1.5px dashed rgba(255,255,255,0.11);border-radius:18px;display:flex;align-items:center;gap:12px;animation:cardUp 0.6s var(--spring) 0.48s both;}
    .teaser-ico{font-size:2rem;}
    .teaser-txt{font-size:0.82rem;font-weight:600;color:var(--muted);line-height:1.55;}
    .teaser-txt strong{color:rgba(255,255,255,0.68);}

    /* ── GAME VIEW ── */
    #game-view{position:fixed;inset:0;z-index:50;display:flex;flex-direction:column;background:#000;opacity:0;pointer-events:none;transition:opacity 0.35s var(--ease);}
    #game-view.visible{opacity:1;pointer-events:all;}

    #game-topbar{display:flex;align-items:center;gap:10px;padding:0 14px;height:52px;min-height:52px;background:rgba(7,7,20,0.97);border-bottom:1.5px solid rgba(255,255,255,0.08);backdrop-filter:blur(14px);z-index:60;flex-shrink:0;}

    #back-btn{display:flex;align-items:center;gap:8px;padding:7px 16px 7px 10px;background:rgba(255,255,255,0.07);border:1.5px solid rgba(255,255,255,0.14);border-radius:999px;color:var(--white);font-family:'Baloo 2',cursive;font-size:0.92rem;font-weight:700;cursor:pointer;white-space:nowrap;transition:background 0.18s,border-color 0.18s,transform 0.15s;flex-shrink:0;}
    #back-btn:hover{background:rgba(255,255,255,0.14);border-color:rgba(255,255,255,0.3);}
    #back-btn:active{transform:scale(0.96);}
    #back-btn .back-ico{font-size:1.15rem;}

    #topbar-emoji{font-size:1.4rem;flex-shrink:0;}
    #topbar-title{font-family:'Boogaloo',cursive;font-size:1.15rem;color:var(--white);letter-spacing:0.5px;flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;}

    .switcher-btns{display:flex;gap:7px;flex-shrink:0;}
    .sw-btn{width:36px;height:36px;border-radius:12px;background:rgba(255,255,255,0.06);border:1.5px solid rgba(255,255,255,0.10);display:flex;align-items:center;justify-content:center;font-size:1.2rem;cursor:pointer;transition:background 0.18s,border-color 0.18s,transform 0.15s;position:relative;}
    .sw-btn:hover{background:rgba(255,255,255,0.14);border-color:rgba(255,255,255,0.28);transform:scale(1.09);}
    .sw-btn:active{transform:scale(0.93);}
    .sw-btn.current{border-color:rgba(255,255,255,0.38);background:rgba(255,255,255,0.13);}
    .sw-btn .sw-tip{position:absolute;bottom:-30px;left:50%;transform:translateX(-50%);white-space:nowrap;font-size:0.62rem;font-weight:700;background:rgba(7,7,20,0.92);color:rgba(255,255,255,0.72);padding:3px 8px;border-radius:6px;pointer-events:none;opacity:0;transition:opacity 0.15s;}
    .sw-btn:hover .sw-tip{opacity:1;}

    #game-frame{flex:1;border:none;width:100%;height:100%;background:#000;}

    /* loader */
    #frame-loader{position:absolute;inset:0;z-index:55;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:18px;background:var(--bg);pointer-events:none;opacity:1;transition:opacity 0.45s;}
    #frame-loader.done{opacity:0;}
    .loader-planet{font-size:60px;animation:planetBob 2s ease-in-out infinite;}
    .loader-bar{width:180px;height:5px;border-radius:5px;background:rgba(255,255,255,0.10);overflow:hidden;}
    .loader-fill{height:100%;border-radius:5px;background:linear-gradient(90deg,#ff4d6d,#00cfb4,#ffc43d);animation:loadFill 1.2s ease-in-out infinite;}
    @keyframes loadFill{0%{width:0%;margin-left:0;}50%{width:70%;margin-left:10%;}100%{width:0%;margin-left:100%;}}
    .loader-txt{font-family:'Boogaloo',cursive;font-size:1.2rem;color:var(--muted);letter-spacing:0.8px;}

    @keyframes dropIn{from{opacity:0;transform:translateY(-22px);}to{opacity:1;transform:translateY(0);}}
    @keyframes cardUp{from{opacity:0;transform:translateY(28px);}to{opacity:1;transform:translateY(0);}}

    @media(max-width:480px){
      .card-art{padding:22px 16px 12px;}
      .card-emoji-bg{width:76px;height:76px;font-size:38px;}
      .card-body{padding:0 16px 18px;}
      .sw-btn .sw-tip{display:none;}
      #game-topbar{padding:0 10px;gap:8px;}
    }
    @media(max-width:360px){.score-strip{display:none;}}
  </style>
</head>
<body>

<div id="cosmos">
  <div class="nebula neb1"></div>
  <div class="nebula neb2"></div>
  <div class="nebula neb3"></div>
</div>

<!-- ═══ HUB ═══ -->
<div id="hub">
  <header class="hub-header">
    <div class="mascot-wrap">
      <span class="mascot">🪐</span>
      <div class="orbit-ring"><span class="orbit-star">⭐</span></div>
    </div>
    <h1 class="hub-title">Kids Game Zone</h1>
    <p class="hub-sub">Pilih game favoritmu dan mulai petualangan! 🚀</p>
  </header>

  <div class="score-strip">
    <div class="score-pill"><span>🎮</span><span>Games Played:</span><span class="sp-val" id="sp-played">0</span></div>
    <div class="score-pill"><span>🔥</span><span>Session:</span><span class="sp-val" id="sp-session">0</span></div>
    <div class="score-pill"><span>⭐</span><span>Stars:</span><span class="sp-val" id="sp-stars">0</span></div>
  </div>

  <div class="cards-wrap">

    <div class="game-card" data-href="rocketman.html" data-name="Apollo Exploration" data-emoji="🚀" tabindex="0" role="button" aria-label="Main Apollo Exploration">
      <div class="card-art"><div class="card-emoji-bg">🚀</div></div>
      <div class="card-body">
        <div class="card-genre">Logic &amp; Coding</div>
        <div class="card-name">Apollo Exploration</div>
        <div class="card-desc">Susun perintah dan bantu roket melewati labirin luar angkasa!</div>
        <div class="card-footer">
          <span class="card-badge">5 Levels</span>
          <div class="card-go">→</div>
        </div>
      </div>
    </div>

    <div class="game-card" data-href="gravity.html" data-name="Ball Drop" data-emoji="🌊" tabindex="0" role="button" aria-label="Main Ball Drop">
      <div class="card-art"><div class="card-emoji-bg">🌊</div></div>
      <div class="card-body">
        <div class="card-genre">Physics Puzzle</div>
        <div class="card-name">Ball Drop</div>
        <div class="card-desc">Jatuhkan blok, atur gravitasi — selesaikan setiap level!</div>
        <div class="card-footer">
          <span class="card-badge">Story Mode</span>
          <div class="card-go">→</div>
        </div>
      </div>
    </div>

    <div class="game-card" data-href="flag.html" data-name="Flag Guess" data-emoji="🌎" tabindex="0" role="button" aria-label="Main Flag Guess">
      <div class="card-art"><div class="card-emoji-bg">🌎</div></div>
      <div class="card-body">
        <div class="card-genre">General Knowledge</div>
        <div class="card-name">Flag Guess</div>
        <div class="card-desc">Tebak nama negara dari benderanya — 150+ negara!</div>
        <div class="card-footer">
          <span class="card-badge">150+ Flags</span>
          <div class="card-go">→</div>
        </div>
      </div>
    </div>

  </div>

  <div class="teaser">
    <span class="teaser-ico">🛸</span>
    <p class="teaser-txt"><strong>Lebih banyak game segera hadir!</strong> Pantau terus untuk petualangan baru, quiz seru, dan puzzle keren.</p>
  </div>

  <footer style="margin-top:36px;color:rgba(255,255,255,0.18);font-size:0.78rem;font-weight:600;text-align:center;">
    Made with ❤️ for kids &nbsp;·&nbsp;
    <a href="https://github.com/irfanradarma/kids" target="_blank" style="color:rgba(120,180,255,0.48);text-decoration:none;">View on GitHub</a>
  </footer>
</div>

<!-- ═══ GAME VIEW ═══ -->
<div id="game-view">
  <div id="game-topbar">
    <button id="back-btn" aria-label="Kembali ke menu">
      <span class="back-ico">🪐</span> Game Zone
    </button>
    <span id="topbar-emoji" aria-hidden="true"></span>
    <span id="topbar-title"></span>
    <div class="switcher-btns" id="switcherBtns"></div>
  </div>

  <div id="frame-loader">
    <span class="loader-planet">🚀</span>
    <div class="loader-bar"><div class="loader-fill"></div></div>
    <span class="loader-txt">Memuat game…</span>
  </div>

  <iframe id="game-frame" title="Game" allowfullscreen></iframe>
</div>

<script>
/* ── COSMOS ── */
(function(){
  const c = document.getElementById('cosmos');
  const n = window.innerWidth > 900 ? 200 : window.innerWidth > 500 ? 120 : 70;
  for(let i=0;i<n;i++){
    const s=document.createElement('div'); s.className='star';
    const sz=Math.random()*2.3+0.3;
    s.style.cssText=`width:${sz}px;height:${sz}px;top:${Math.random()*100}%;left:${Math.random()*100}%;--d:${(Math.random()*3.5+1.5).toFixed(1)}s;animation-delay:${(Math.random()*5).toFixed(1)}s`;
    c.appendChild(s);
  }
  for(let i=0;i<4;i++){
    const sh=document.createElement('div'); sh.className='shoot';
    sh.style.cssText=`top:${8+i*22}%;left:${(Math.random()*25).toFixed(0)}%;--sd:${6+i*2.5}s;--ss:${(i*3.5).toFixed(1)}s`;
    c.appendChild(sh);
  }
})();

/* ── GAME REGISTRY ── */
const GAMES = [
  {href:'rocketman.html', name:'Apollo Exploration', emoji:'🚀'},
  {href:'gravity.html',   name:'Ball Drop',          emoji:'🌊'},
  {href:'flag.html',      name:'Flag Guess',         emoji:'🌎'},
];

/* ── STATS ── */
const stats = {played:0, session:0, stars:0};
function refreshStats(){
  document.getElementById('sp-played').textContent  = stats.played;
  document.getElementById('sp-session').textContent = stats.session;
  document.getElementById('sp-stars').textContent   = stats.stars;
}

/* ── ELEMENTS ── */
const hub      = document.getElementById('hub');
const gameView = document.getElementById('game-view');
const frame    = document.getElementById('game-frame');
const loader   = document.getElementById('frame-loader');
const topTitle = document.getElementById('topbar-title');
const topEmoji = document.getElementById('topbar-emoji');
const switcher = document.getElementById('switcherBtns');
const backBtn  = document.getElementById('back-btn');
let currentHref = null;

/* ── SWITCHER ── */
function buildSwitcher(activeHref){
  switcher.innerHTML='';
  GAMES.forEach(g=>{
    const btn=document.createElement('div');
    btn.className='sw-btn'+(g.href===activeHref?' current':'');
    btn.setAttribute('role','button');
    btn.setAttribute('tabindex','0');
    btn.setAttribute('aria-label','Main '+g.name);
    btn.innerHTML=`${g.emoji}<span class="sw-tip">${g.name}</span>`;
    btn.addEventListener('click',()=>{ if(g.href!==currentHref) openGame(g.href); });
    btn.addEventListener('keydown',e=>{ if(e.key==='Enter') btn.click(); });
    switcher.appendChild(btn);
  });
}

/* ── OPEN GAME ── */
function openGame(href){
  const g = GAMES.find(x=>x.href===href);
  if(!g) return;
  currentHref = href;
  stats.played++;
  stats.session++;
  stats.stars = stats.played + Math.floor(stats.session/2);
  refreshStats();

  topTitle.textContent = g.name;
  topEmoji.textContent = g.emoji;
  buildSwitcher(href);

  loader.classList.remove('done');
  hub.classList.add('hiding');
  gameView.classList.add('visible');

  setTimeout(()=>{ frame.src = href; }, 80);
  frame.onload = ()=>{ setTimeout(()=>loader.classList.add('done'), 300); };
}

/* ── GO HOME ── */
function goHome(){
  gameView.classList.remove('visible');
  hub.classList.remove('hiding');
  setTimeout(()=>{ frame.src='about:blank'; currentHref=null; }, 400);
}

/* ── CARD CLICKS ── */
document.querySelectorAll('.game-card').forEach(card=>{
  const fn=()=>openGame(card.dataset.href);
  card.addEventListener('click', fn);
  card.addEventListener('keydown',e=>{ if(e.key==='Enter'||e.key===' '){ e.preventDefault(); fn(); } });
});

/* ── BACK ── */
backBtn.addEventListener('click', goHome);
document.addEventListener('keydown',e=>{ if(e.key==='Escape'&&gameView.classList.contains('visible')) goHome(); });

refreshStats();
</script>
</body>
</html>