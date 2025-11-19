---
title: Chatbot
---

<!-- HERO + CONTROLS -->
<header class="site-header" role="banner">
  <div class="brand">
    <div class="logo" aria-hidden="true">🤖</div>
    <div>
      <h1>Udify Chat</h1>
      <p class="tag">Ask anything — voice & text supported</p>
    </div>
  </div>

  <div class="controls">
    <button id="themeToggle" class="icon-btn" aria-label="Toggle theme">🌙</button>
    <button id="shareBtn" class="icon-btn" aria-label="Share link">🔗</button>
    <button id="infoToggle" class="icon-btn" aria-label="Open info">❔</button>
  </div>
</header>

<div class="layout">
  <aside class="meta" id="metaPanel" aria-hidden="false">
    <div class="meta-inner">
      <h2>About this bot</h2>
      <p>Voice-enabled assistant hosted on Udify. Helpful for quick research, debugging, and casual chat. Uses microphone permission if you allow it.</p>

      <h3>Quick tips</h3>
      <ul>
        <li>Click the mic icon inside the chat to speak.</li>
        <li>Use the theme toggle for dark/light modes.</li>
        <li>On mobile, tap the floating button to open this panel.</li>
      </ul>

      <h3>FAQ</h3>
      <details>
        <summary>Embed blank?</summary>
        If the iframe is blank, the host may block embedding. Try opening the bot link directly to verify.
      </details>

      <div class="meta-footer">
        <small>Made with ❤️ · GitHub Pages</small>
      </div>
    </div>
  </aside>

  <main class="chat-area" id="chatArea" role="main">
    <div class="chat-shell">
      <!-- your iframe -->
      <iframe id="chatFrame"
              src="https://udify.app/chatbot/sI7tIcJbUKYk9pHy"
              title="Udify Chatbot"
              allow="microphone"
              frameborder="0"
              sandbox="allow-scripts allow-same-origin allow-forms">
      </iframe>
    </div>
  </main>
</div>

<button id="fab" class="fab" aria-label="Open info">❔</button>

<style>
/* ---------- Variables & reset ---------- */
:root{
  --bg-1: #0f172a; --bg-2: #0b1226;
  --text: #e6eef8;        /* primary readable text on dark */
  --muted: #9aa6b2;       /* secondary text */
  --accent: #60a5fa;
  --glass: rgba(255,255,255,0.06);
  --radius: 14px;
}
[data-theme="light"]{
  --bg-1:#f7f9fc; --bg-2:#eef2fb;
  --text: #0b1220;        /* primary readable text on light */
  --muted: #4b5563;
  --accent: #2563eb;
  --glass: rgba(255,255,255,0.7);
}
*{box-sizing:border-box}
html,body{height:100%}
body{
  margin:0;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  color:var(--text);
  background: linear-gradient(160deg,var(--bg-1),var(--bg-2));
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  padding:18px;
  overflow-y:overlay;
}

/* subtle background blobs */
body::before{
  content:"";
  position:fixed;
  inset:-10% -20%;
  background:
    radial-gradient(30vw 30vw at 10% 20%, rgba(96,165,250,0.06), transparent 15%),
    radial-gradient(25vw 25vw at 90% 80%, rgba(99,102,241,0.05), transparent 12%);
  z-index:0;
  pointer-events:none;
}

/* ---------- Header ---------- */
.site-header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:12px;
  max-width:1200px;
  margin:0 auto 18px;
  position:relative;
  z-index:2;
}
.brand{display:flex; align-items:center; gap:12px}
.logo{width:56px; height:56px; border-radius:12px; display:grid; place-items:center; font-size:26px; background:linear-gradient(135deg,#1e3a8a,#60a5fa)}
.brand h1{margin:0;font-size:18px; color:var(--text)}
.tag{margin:0; color:var(--muted); font-size:13px}
.controls{display:flex; gap:8px}
.icon-btn{background:var(--glass); border:0; padding:8px 10px; border-radius:10px; cursor:pointer; font-size:16px}

/* ---------- Layout ---------- */
.layout{display:grid; grid-template-columns:320px 1fr; gap:20px; max-width:1200px; margin:0 auto; align-items:start; position:relative; z-index:2}
.meta{
  background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
  border-radius:var(--radius);
  padding:18px;
  color:var(--text);
  box-shadow:0 10px 30px rgba(2,6,23,0.6);
  backdrop-filter: blur(8px) saturate(120%);
  border:1px solid rgba(255,255,255,0.03);
}
.meta h2{margin-top:0}
.meta p, .meta ul li, .meta details summary{color:var(--text)}
.meta ul{padding-left:18px; margin:6px 0 12px}
.meta-footer{margin-top:22px; color:var(--muted); font-size:13px}

/* ---------- Chat card ---------- */
.chat-area{display:flex; align-items:flex-start; justify-content:center}
.chat-shell{
  width:100%;
  min-height:560px;
  border-radius:var(--radius);
  padding:12px;
  background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
  box-shadow: 0 18px 40px rgba(2,6,23,0.6);
  border:1px solid rgba(255,255,255,0.03);
  overflow:hidden;
  display:flex; flex-direction:column;
  animation: lift .55s cubic-bezier(.2,.9,.3,1);
}
@keyframes lift{ from{transform:translateY(12px); opacity:0} to{transform:none; opacity:1} }

.chat-shell iframe{
  width:100%;
  height:700px;
  border:0;
  border-radius:10px;
  background:transparent;
  display:block;
  max-width:100%;
}

/* ---------- FAB (mobile) ---------- */
.fab{
  position:fixed;
  right:18px;
  bottom:22px;
  z-index:60;
  border:0;
  background:linear-gradient(135deg,var(--accent), #7dd3fc 90%);
  color:#042a2b;
  padding:12px 14px;
  border-radius:999px;
  box-shadow: 0 10px 30px rgba(2,6,23,0.35);
  cursor:pointer;
  display:none;
}

/* ---------- Responsive: mobile view ---------- */
@media (max-width:900px){
  body{padding:12px}
  .layout{grid-template-columns:1fr; gap:12px; margin-bottom:80px}
  /* meta becomes a slide-over */
  .meta{
    position:fixed;
    right:12px;
    top:72px;                /* safer top offset so it won't overlap header */
    width:82%;
    max-width:420px;
    transform:translateX(110%);
    transition:transform .28s cubic-bezier(.2,.9,.3,1);
    box-shadow: 0 30px 60px rgba(2,6,23,0.6);
    display:block;
    height:calc(100vh - 96px);
    overflow:auto;
  }
  .meta.open{transform:translateX(0)}
  /* chat-shell uses viewport height minus header & controls; iframe fits 100% of shell */
  .chat-shell{
    min-height:unset;
    height: calc(100vh - 120px); /* most phones: header + small gap ≈ 120px */
    padding:8px;
  }
  .chat-shell iframe{
    height:100%;
    max-height: calc(100vh - 120px);
    border-radius:10px;
  }
  .controls{gap:6px}
  .fab{display:block}
  .site-header{margin-bottom:8px}
}

/* ---------- Light-mode tweaks ---------- */
[data-theme="light"] .brand h1, [data-theme="light"] .tag{color:var(--text)}
</style>

<script>
/* Respect reduced motion */
if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
  document.documentElement.style.setProperty('--prefers-reduced-motion','reduce');
}

/* Theme toggle */
(function(){
  const btn = document.getElementById('themeToggle');
  const stored = localStorage.getItem('theme') || (window.matchMedia && window.matchMedia('(prefers-color-scheme: light)').matches ? 'light' : 'dark');
  if(stored === 'light') document.documentElement.setAttribute('data-theme','light');

  btn.addEventListener('click', ()=>{
    const isDark = document.documentElement.getAttribute('data-theme') !== 'light';
    if(isDark) {
      document.documentElement.setAttribute('data-theme','light');
      localStorage.setItem('theme','light');
      btn.textContent='🌙';
    } else {
      document.documentElement.removeAttribute('data-theme');
      localStorage.setItem('theme','dark');
      btn.textContent='☀️';
    }
  });
})();

/* Info panel toggle (desktop & mobile) */
(function(){
  const infoToggle = document.getElementById('infoToggle');
  const meta = document.getElementById('metaPanel');
  const fab = document.getElementById('fab');
  const shareBtn = document.getElementById('shareBtn');

  function openMeta() {
    meta.classList.add('open');
    meta.setAttribute('aria-hidden','false');
  }
  function closeMeta(){
    meta.classList.remove('open');
    meta.setAttribute('aria-hidden','true');
  }

  infoToggle.addEventListener('click', ()=>{
    meta.classList.toggle('open');
    const open = meta.classList.contains('open');
    meta.setAttribute('aria-hidden', !open);
  });

  fab.addEventListener('click', openMeta);

  // Close meta if clicked outside on mobile
  document.addEventListener('click', (e)=>{
    if(window.innerWidth <= 900 && meta.classList.contains('open')){
      const inside = meta.contains(e.target) || e.target.id === 'fab' || e.target.id === 'infoToggle';
      if(!inside) closeMeta();
    }
  });

  // Share / copy page link
  shareBtn.addEventListener('click', async ()=>{
    const url = location.href;
    try {
      await navigator.clipboard.writeText(url);
      shareBtn.textContent = '✅';
      setTimeout(()=> shareBtn.textContent = '🔗', 1400);
    } catch(e){
      alert('Copy failed — please copy the URL manually.');
    }
  });
})();
</script>
