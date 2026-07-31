<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LUBILUBIJBI's Servers</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#150E0B;
    --bg-panel:#1F1512;
    --border:#3A241A;
    --ember:#FF6A2B;
    --ember-soft:#FF8A4C;
    --glow:#FFB84D;
    --crimson:#B23A2E;
    --text:#F2E6DC;
    --text-dim:#B8A79A;
    --green:#6FCB6F;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  body{
    background:var(--bg);
    color:var(--text);
    font-family:'Inter', sans-serif;
    line-height:1.5;
  }
  h1,h2,h3,.display{font-family:'Rajdhani', sans-serif; font-weight:700; letter-spacing:.02em;}
  .mono{font-family:'JetBrains Mono', monospace;}
  a{color:inherit;}
  .wrap{max-width:1080px; margin:0 auto; padding:0 24px;}

  .crack-divider{
    height:36px; margin:0 auto; max-width:1080px;
    background-repeat:no-repeat; background-position:center;
    background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 900 36' preserveAspectRatio='none'%3E%3Cpath d='M0 18 L120 18 L140 6 L160 26 L180 18 L340 18 L360 30 L380 10 L400 18 L560 18 L580 4 L600 24 L620 18 L780 18 L800 28 L820 12 L840 18 L900 18' stroke='%23FF6A2B' stroke-width='2' fill='none' opacity='0.65'/%3E%3C/svg%3E");
    opacity:.8;
  }

  header{
    position:sticky; top:0; z-index:20;
    background:rgba(21,14,11,.9); backdrop-filter:blur(6px);
    border-bottom:1px solid var(--border);
  }
  .nav{display:flex; align-items:center; justify-content:space-between; padding:16px 24px;}
  .logo{display:flex; align-items:center; gap:10px; font-size:19px;}
  .logo .cube{
    width:26px; height:26px;
    background:linear-gradient(135deg, var(--ember), var(--crimson));
    box-shadow:0 0 12px rgba(255,106,43,.6);
  }
  .logo b{color:var(--ember-soft);}
  nav.links{display:flex; gap:26px; font-size:15px; color:var(--text-dim);}
  nav.links a:hover{color:var(--ember-soft);}

  .hero{padding:72px 24px 48px; text-align:center;}
  .status-pill{
    display:inline-flex; align-items:center; gap:8px;
    border:1px solid var(--border); border-radius:999px;
    padding:6px 16px; font-size:13px; color:var(--text-dim);
    font-family:'JetBrains Mono', monospace; margin-bottom:28px;
  }
  .dot{width:8px; height:8px; border-radius:50%; background:var(--green); box-shadow:0 0 8px var(--green); animation:pulse 1.6s ease-in-out infinite;}
  @keyframes pulse{0%,100%{opacity:1; transform:scale(1);} 50%{opacity:.4; transform:scale(1.3);}}

  .hero h1{font-size:56px; line-height:1.05; color:var(--text);}
  .hero h1 .accent{
    background:linear-gradient(90deg, var(--ember), var(--glow));
    -webkit-background-clip:text; background-clip:text; color:transparent;
  }
  .hero p{max-width:520px; margin:22px auto 34px; color:var(--text-dim); font-size:17px;}
  .cta-row{display:flex; gap:14px; justify-content:center; flex-wrap:wrap;}
  .btn{
    font-family:'Rajdhani', sans-serif; font-weight:700; font-size:16px;
    padding:13px 26px; border-radius:6px; cursor:pointer; border:1px solid transparent;
    display:inline-flex; align-items:center; gap:8px; text-decoration:none;
  }
  .btn-primary{background:linear-gradient(90deg, var(--ember), var(--crimson)); color:#180B08; box-shadow:0 6px 20px rgba(255,106,43,.25);}
  .btn-ghost{border-color:var(--border); color:var(--text); background:transparent;}
  .btn-ghost:hover{border-color:var(--ember);}

  section{padding:56px 24px;}
  .section-head{margin-bottom:30px;}
  .section-head h2{font-size:30px;}
  .section-head p{color:var(--text-dim); margin-top:8px; font-size:15px;}

  .discord-panel{
    background:var(--bg-panel); border:1px solid var(--border); border-radius:10px;
    padding:26px; display:flex; align-items:center; justify-content:space-between; gap:16px; flex-wrap:wrap;
  }
  .discord-panel .ip-line a{
    font-family:'JetBrains Mono', monospace; font-size:16px; color:var(--ember-soft); text-decoration:none;
  }
  .discord-panel .ip-line a:hover{text-decoration:underline;}
  .copy-btn{
    background:var(--bg); border:1px solid var(--border); color:var(--text-dim);
    font-family:'JetBrains Mono', monospace; font-size:12px; padding:8px 12px; border-radius:5px; cursor:pointer;
    flex:none;
  }
  .copy-btn:hover{border-color:var(--ember); color:var(--ember-soft);}
  .copy-btn.copied{color:var(--green); border-color:var(--green);}

  .servers-grid{display:grid; grid-template-columns:repeat(auto-fit, minmax(280px,1fr)); gap:20px;}
  .server-card{
    background:var(--bg-panel); border:1px solid var(--border); border-radius:10px;
    overflow:hidden; position:relative;
    transition:border-color .15s, transform .15s;
  }
  .server-card:hover{border-color:var(--ember); transform:translateY(-2px);}
  .banner{
    width:100%; aspect-ratio:1/1; object-fit:cover; display:block;
    border-bottom:1px solid var(--border);
  }
  .card-body{padding:20px;}
  .tag{
    display:inline-block; font-family:'JetBrains Mono', monospace; font-size:11px;
    padding:3px 9px; border-radius:4px; margin-bottom:12px; letter-spacing:.05em;
  }
  .tag.pvp{background:rgba(255,106,43,.15); color:var(--ember-soft); border:1px solid rgba(255,106,43,.35);}
  .tag.hardcore{background:rgba(178,58,46,.18); color:#E8756A; border:1px solid rgba(178,58,46,.4);}
  .tag.lifesteal{background:rgba(220,40,40,.18); color:#FF6B6B; border:1px solid rgba(220,40,40,.4);}
  .tag.smp{background:rgba(111,203,111,.15); color:var(--green); border:1px solid rgba(111,203,111,.35);}
  .tag.ranked{background:rgba(255,184,77,.15); color:var(--glow); border:1px solid rgba(255,184,77,.35);}
  .tag.newgen{background:rgba(178,130,255,.15); color:#C7A8FF; border:1px solid rgba(178,130,255,.4);}

  .server-card h3{font-size:22px; margin-bottom:6px;}
  .server-card .desc{color:var(--text-dim); font-size:14px; margin-bottom:16px;}
  .server-card .row{
    display:flex; align-items:center; justify-content:space-between; gap:10px;
    background:var(--bg); border:1px solid var(--border); border-radius:6px;
    padding:9px 12px; margin-bottom:8px;
  }
  .server-card .row .info{min-width:0;}
  .server-card .row .label{font-size:10px; text-transform:uppercase; letter-spacing:.08em; color:var(--text-dim); display:block; margin-bottom:2px;}
  .server-card .row .val{font-family:'JetBrains Mono', monospace; font-size:13px; color:var(--text); overflow:hidden; text-overflow:ellipsis; white-space:nowrap; display:block;}
  .server-card .row a.val{text-decoration:none;}
  .server-card .row a.val:hover{color:var(--ember-soft); text-decoration:underline;}
  .apply-note{
    font-size:12.5px; color:var(--glow); background:rgba(255,184,77,.1);
    border:1px solid rgba(255,184,77,.3); border-radius:6px; padding:9px 12px; margin-bottom:8px;
  }

  footer{
    border-top:1px solid var(--border); padding:34px 24px; text-align:center;
    color:var(--text-dim); font-size:13px;
  }
  footer .logo{justify-content:center; margin-bottom:10px;}
  footer p{max-width:480px; margin:0 auto 6px;}

  @media(max-width:600px){
    .hero h1{font-size:38px;}
    nav.links{display:none;}
  }
</style>
</head>
<body>

<header>
  <div class="nav">
    <div class="logo"><div class="cube"></div><b>LUBILUBIJBI</b>'s Servers</div>
    <nav class="links">
      <a href="#servers">Server</a>
      <a href="#discord">Discord</a>
    </nav>
  </div>
</header>

<section class="hero">
  <div class="status-pill"><span class="dot"></span> SEASON 1 IST LIVE</div>
  <h1>LUBILUBIJBI'S <span class="accent">SERVERS</span></h1>
  <p>Die brutalste PvP-Arena in Minecraft. Töten. Ranglisten. Wiederholen. Keine Gnade.</p>
  <div class="cta-row">
    <a class="btn btn-primary" href="#servers">Server ansehen</a>
    <a class="btn btn-ghost" href="#discord">Discord beitreten</a>
  </div>
</section>

<div class="crack-divider"></div>

<section id="discord">
  <div class="wrap">
    <div class="section-head">
      <h2>Unser <span style="color:var(--ember-soft)">Discord</span></h2>
      <p>Tritt der Community bei, bleib auf dem Laufenden und connecte dich mit anderen Spielern.</p>
    </div>
    <div class="discord-panel">
      <div class="ip-line"><a href="https://discord.gg/ApC2SgtqAT" target="_blank" rel="noopener">discord.gg/ApC2SgtqAT</a></div>
      <button class="copy-btn" data-copy="https://discord.gg/ApC2SgtqAT">KOPIEREN</button>
    </div>
  </div>
</section>

<div class="crack-divider"></div>

<section id="servers">
  <div class="wrap">
    <div class="section-head">
      <h2>Unsere Server</h2>
      <p>Sechs einzigartige Welten. Eine Community. Wähl dein Schlachtfeld.</p>
    </div>
    <div class="servers-grid">

      <div class="server-card">
        <img class="banner" src="pvp3.png" alt="PvP3 Banner">
        <div class="card-body">
          <span class="tag pvp">PVP</span>
          <h3>PvP3</h3>
          <div class="desc">A gen Server with good community!</div>
          <div class="row">
            <div class="info"><span class="label">Server IP</span><span class="val">pvp3lubi.minekeep.gg</span></div>
            <button class="copy-btn" data-copy="pvp3lubi.minekeep.gg">KOPIEREN</button>
          </div>
          <div class="row">
            <div class="info"><span class="label">Discord</span><a class="val" href="https://discord.gg/RnAFUkh3rh" target="_blank" rel="noopener">discord.gg/RnAFUkh3rh</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/RnAFUkh3rh">KOPIEREN</button>
          </div>
        </div>
      </div>

      <div class="server-card">
        <img class="banner" src="pvp3newgen.png" alt="PvP3 New Generation Banner">
        <div class="card-body">
          <span class="tag newgen">NEW GENERATION</span>
          <h3>PvP3 | New Generation</h3>
          <div class="desc">The new PvP3 server!</div>
          <div class="row">
            <div class="info"><span class="label">Server IP</span><span class="val">pvp3lubijbi.minekeep.gg</span></div>
            <button class="copy-btn" data-copy="pvp3lubijbi.minekeep.gg">KOPIEREN</button>
          </div>
          <div class="row">
            <div class="info"><span class="label">Discord</span><a class="val" href="https://discord.gg/wtsSA2Fpcj" target="_blank" rel="noopener">discord.gg/wtsSA2Fpcj</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/wtsSA2Fpcj">KOPIEREN</button>
          </div>
        </div>
      </div>

      <div class="server-card">
        <img class="banner" src="lubsmp.png" alt="LUBSMP Banner">
        <div class="card-body">
          <span class="tag hardcore">HARDCORE</span>
          <h3>LUBSMP</h3>
          <div class="desc">A minecraft HARDCORE server, no script!</div>
          <div class="row">
            <div class="info"><span class="label">Server IP</span><span class="val">lubsmp.minekeep.gg</span></div>
            <button class="copy-btn" data-copy="lubsmp.minekeep.gg">KOPIEREN</button>
          </div>
          <div class="row">
            <div class="info"><span class="label">Discord</span><a class="val" href="https://discord.gg/TyRQPAKZGV" target="_blank" rel="noopener">discord.gg/TyRQPAKZGV</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/TyRQPAKZGV">KOPIEREN</button>
          </div>
        </div>
      </div>

      <div class="server-card">
        <img class="banner" src="pvpsteal3.png" alt="PvPSteal3 Banner">
        <div class="card-body">
          <span class="tag lifesteal">LIFESTEAL</span>
          <h3>PvPSteal3</h3>
          <div class="desc">Just a normal lifesteal server...</div>
          <div class="row">
            <div class="info"><span class="label">Server IP</span><span class="val">pvpsteal3.minekeep.gg</span></div>
            <button class="copy-btn" data-copy="pvpsteal3.minekeep.gg">KOPIEREN</button>
          </div>
          <div class="row">
            <div class="info"><span class="label">Discord</span><a class="val" href="https://discord.gg/r5TUjbBn3P" target="_blank" rel="noopener">discord.gg/r5TUjbBn3P</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/r5TUjbBn3P">KOPIEREN</button>
          </div>
        </div>
      </div>

      <div class="server-card">
        <img class="banner" src="pvp3smp.png" alt="PvP3SMP Banner">
        <div class="card-body">
          <span class="tag smp">SMP</span>
          <h3>PvP3SMP</h3>
          <div class="desc">A SMP</div>
          <div class="row">
            <div class="info"><span class="label">Server IP</span><span class="val">pvp3smp.minekeep.gg</span></div>
            <button class="copy-btn" data-copy="pvp3smp.minekeep.gg">KOPIEREN</button>
          </div>
          <div class="row">
            <div class="info"><span class="label">Discord</span><a class="val" href="https://discord.gg/r5TUjbBn3P" target="_blank" rel="noopener">discord.gg/r5TUjbBn3P</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/r5TUjbBn3P">KOPIEREN</button>
          </div>
        </div>
      </div>

      <div class="server-card">
        <img class="banner" src="rankedbounty.png" alt="Ranked Bounty SMP Banner">
        <div class="card-body">
          <span class="tag ranked">RANKED · BEWERBUNG</span>
          <h3>Ranked Bounty SMP</h3>
          <div class="desc">Ranglisten-SMP mit Kopfgeldjagd.</div>
          <div class="apply-note">Beitritt nur nach Bewerbung im Discord.</div>
          <div class="row">
            <div class="info"><span class="label">Discord (Bewerbung)</span><a class="val" href="https://discord.gg/xuaVX7xJfJ" target="_blank" rel="noopener">discord.gg/xuaVX7xJfJ</a></div>
            <button class="copy-btn" data-copy="https://discord.gg/xuaVX7xJfJ">KOPIEREN</button>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<footer>
  <div class="logo"><div class="cube"></div><b>LUBILUBIJBI</b>'s Servers</div>
  <p>Das ultimative kompetitive Minecraft-PvP-Netzwerk. Erlebe unvergleichlichen Kampf, raue Survival-Welten und eine lebendige Elite-Community.</p>
  <p style="margin-top:14px; opacity:.6;">© 2026 LUBILUBIJBI Network. Kein offizielles Minecraft-Produkt. Nicht von Mojang genehmigt oder unterstützt.</p>
</footer>

<script>
  document.querySelectorAll('.copy-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      const text = btn.dataset.copy;
      navigator.clipboard?.writeText(text).catch(()=>{});
      const original = btn.textContent;
      btn.textContent = 'KOPIERT ✓';
      btn.classList.add('copied');
      setTimeout(() => { btn.textContent = original; btn.classList.remove('copied'); }, 1500);
    });
  });
</script>

</body>
</html>
