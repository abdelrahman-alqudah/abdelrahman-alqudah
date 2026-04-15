<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abd Elrahman Alqudah — Operator Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Press+Start+2P&family=Rajdhani:wght@400;600;700&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --green:#3adf22;--green-dim:#2d5a1b;--green-glow:#3adf2244;
  --bg:#060a06;--bg2:#0d1a0d;--bg3:#111f11;
  --text:#c8f0a0;--text-dim:#7acc50;--text-muted:#4a8a3a;
  --red:#ff3b30;--amber:#ffaa22;--blue:#22aaff;--diamond:#44ccee;
}
html{background:var(--bg);color:var(--text);font-family:'Share Tech Mono',monospace}
body{min-height:100vh;overflow-x:hidden}

/* ─── SCANLINES ─── */
body::after{
  content:'';position:fixed;inset:0;pointer-events:none;z-index:9999;
  background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,.06) 2px,rgba(0,0,0,.06) 4px);
}

/* ─── NOISE TEXTURE ─── */
body::before{
  content:'';position:fixed;inset:0;pointer-events:none;z-index:9998;opacity:.03;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
}

/* ─── WRAPPER ─── */
.wrap{max-width:860px;margin:0 auto;padding:0 0 40px}

/* ─── BOOT SCREEN ─── */
#boot{
  position:fixed;inset:0;background:#000;z-index:10000;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:12px;
  font-family:'Press Start 2P',monospace;color:var(--green);font-size:11px;
}
#boot .logo{font-size:18px;letter-spacing:4px;margin-bottom:16px;text-shadow:0 0 20px var(--green)}
#boot .bar-wrap{width:280px;height:8px;border:1px solid var(--green-dim);position:relative;overflow:hidden}
#boot .bar-inner{height:100%;background:var(--green);width:0;animation:boot 2.2s ease-out forwards}
@keyframes boot{to{width:100%}}
#boot .log{font-size:7px;color:var(--text-dim);letter-spacing:1px;animation:blink2 .6s step-end infinite}
@keyframes blink2{0%,100%{opacity:1}50%{opacity:.2}}

/* ─── HEADER / HUD ─── */
.hdr{
  position:relative;background:var(--bg2);border-bottom:2px solid var(--green-dim);
  padding:0;overflow:hidden;min-height:220px;
}
.hdr-bg{
  position:absolute;inset:0;
  background:linear-gradient(135deg,#0d1a0d 0%,#060e06 60%,#0a1e15 100%);
}

/* CoD map grid overlay */
.map-overlay{
  position:absolute;inset:0;opacity:.07;
  background-image:linear-gradient(var(--green) 1px,transparent 1px),linear-gradient(90deg,var(--green) 1px,transparent 1px);
  background-size:28px 28px;
}

/* Terrain silhouette */
.terrain-svg{position:absolute;bottom:0;left:0;right:0;opacity:.18}

/* Corner HUD brackets */
.hud-corner{position:absolute;width:28px;height:28px;border:2px solid var(--green)}
.hud-corner.tl{top:12px;left:12px;border-right:none;border-bottom:none}
.hud-corner.tr{top:12px;right:12px;border-left:none;border-bottom:none}
.hud-corner.bl{bottom:12px;left:12px;border-right:none;border-top:none}
.hud-corner.br{bottom:12px;right:12px;border-left:none;border-top:none}

/* Crosshair */
.crosshair{position:absolute;top:18px;left:18px;width:20px;height:20px;opacity:.6}
.crosshair::before,.crosshair::after{content:'';position:absolute;background:var(--green)}
.crosshair::before{width:1px;height:100%;left:50%}
.crosshair::after{width:100%;height:1px;top:50%}

/* Radar */
.radar{
  position:absolute;top:16px;right:60px;width:80px;height:80px;
  border:1px solid var(--green-dim);border-radius:50%;overflow:hidden;opacity:.7;
}
.radar-inner{width:100%;height:100%;background:radial-gradient(ellipse at center,#0d2a0d,#030603);position:relative}
.radar-sweep{
  position:absolute;top:50%;left:50%;width:50%;height:1px;
  background:linear-gradient(90deg,transparent,var(--green));
  transform-origin:left center;
  animation:sweep 3s linear infinite;
}
@keyframes sweep{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
.radar-dot{position:absolute;width:4px;height:4px;border-radius:50%;background:var(--green);animation:ping 1.5s ease-in-out infinite}
.radar-dot.d1{top:30%;left:60%;animation-delay:.4s}
.radar-dot.d2{top:60%;left:35%;animation-delay:.9s}
.radar-dot.d3{top:45%;left:70%;animation-delay:1.4s}
@keyframes ping{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.3;transform:scale(1.5)}}
.radar-cross{position:absolute;inset:0;display:flex;align-items:center;justify-content:center}
.radar-cross::before,.radar-cross::after{content:'';position:absolute;background:rgba(58,223,34,.15)}
.radar-cross::before{width:1px;height:100%}
.radar-cross::after{width:100%;height:1px}
.radar-ring{position:absolute;border:1px solid rgba(58,223,34,.1);border-radius:50%}
.radar-ring.r1{width:40%;height:40%;top:30%;left:30%}
.radar-ring.r2{width:70%;height:70%;top:15%;left:15%}

/* Operator content */
.hdr-content{
  position:relative;z-index:2;padding:28px 28px 24px 44px;
  display:grid;grid-template-columns:1fr auto;gap:16px;align-items:start;
}
.op-badge{
  font-size:8px;color:var(--green);letter-spacing:4px;
  display:flex;align-items:center;gap:8px;margin-bottom:8px;
}
.op-badge::before{content:'';display:inline-block;width:8px;height:8px;border-radius:50%;background:var(--green);animation:blink2 1.2s step-end infinite}
.op-name{
  font-family:'Press Start 2P',monospace;font-size:16px;color:#fff;
  line-height:1.6;margin-bottom:6px;
  text-shadow:0 0 30px rgba(58,223,34,.3);
}
.op-class{font-size:11px;color:var(--text-dim);letter-spacing:3px;margin-bottom:20px}

/* Bars */
.bar-group{display:flex;flex-direction:column;gap:8px}
.bar-item{display:flex;align-items:center;gap:10px}
.bar-lbl{font-size:9px;color:var(--text-dim);letter-spacing:1px;width:100px;flex-shrink:0}
.bar-track{flex:1;height:5px;background:#0a140a;border:1px solid var(--green-dim);overflow:hidden;position:relative}
.bar-fill{height:100%;animation:fillIn 1.5s ease-out both}
@keyframes fillIn{from{width:0!important}}
.bar-fill::after{content:'';position:absolute;right:0;top:0;bottom:0;width:2px;background:#fff;opacity:.7;animation:pulse 1.6s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:.2}50%{opacity:.9}}
.bar-pct{font-size:9px;color:var(--green);width:28px;text-align:right;flex-shrink:0}

.bsec{background:var(--green);width:92%}
.barch{background:var(--blue);width:88%}
.binfra{background:var(--amber);width:78%}

/* Pixel Operator figure */
.op-figure{position:relative;width:90px}
.pixel-char{display:grid;gap:0;image-rendering:pixelated}

/* ─── KILL FEED ─── */
.killfeed{
  background:#000;border-left:2px solid var(--red);border-bottom:1px solid #1a0000;
  padding:6px 12px;font-size:9px;color:rgba(255,255,255,.85);
  display:flex;flex-direction:column;gap:3px;overflow:hidden;
}
.kf-row{display:flex;align-items:center;gap:8px;animation:kfIn .3s ease-out}
@keyframes kfIn{from{opacity:0;transform:translateX(20px)}}
.kf-attacker{color:var(--green)}
.kf-victim{color:var(--red);opacity:.7}
.kf-weapon{
  font-size:7px;padding:1px 5px;border:1px solid rgba(255,255,255,.2);
  color:rgba(255,255,255,.5);letter-spacing:1px;
}
.kf-icon{color:var(--green);font-size:10px}

/* ─── TICKER ─── */
.ticker-wrap{
  background:#030603;border-top:1px solid var(--green-dim);border-bottom:1px solid var(--green-dim);
  overflow:hidden;height:24px;display:flex;align-items:center;
}
.ticker{
  display:flex;gap:48px;white-space:nowrap;
  animation:tick 28s linear infinite;
  font-size:9px;color:var(--green);letter-spacing:2px;
}
@keyframes tick{from{transform:translateX(0)}to{transform:translateX(-50%)}}
.ticker span + span::before{content:'◆';margin-right:48px;opacity:.5}

/* ─── BODY ─── */
.body{display:flex;flex-direction:column;gap:1px;background:var(--green-dim)}
.section{background:var(--bg);padding:20px 28px}
.sec-hdr{
  display:flex;align-items:center;gap:10px;margin-bottom:14px;
  font-size:9px;color:var(--green);letter-spacing:3px;text-transform:uppercase;
}
.sec-hdr::before{content:'';width:3px;height:16px;background:var(--green);flex-shrink:0}
.sec-hdr .sec-num{color:var(--text-muted);margin-left:auto;font-size:8px}

/* ─── MISSION BRIEFING ─── */
.brief-card{
  background:var(--bg2);border:1px solid var(--green-dim);padding:16px 18px;
  position:relative;display:grid;grid-template-columns:1fr 1fr;gap:0 24px;
}
.brief-card::before{
  content:'// CLASSIFIED //';position:absolute;top:-9px;right:14px;
  font-size:7px;background:var(--red);color:#fff;padding:2px 10px;letter-spacing:3px;
}
.brief-row{display:grid;grid-template-columns:90px 1fr;gap:3px 8px;font-size:11px;line-height:2}
.bk{color:var(--text-dim);opacity:.75}
.bv{color:#d4f0b0}
.status-dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--green);margin-right:5px;animation:blink2 1.2s step-end infinite}

/* ─── MINECRAFT SKILL WORLD ─── */
.mc-world{background:var(--bg2);border:1px solid var(--green-dim);overflow:hidden}

/* Sky */
.mc-sky{
  height:52px;
  background:linear-gradient(180deg,#1a3a6b 0%,#3a6bab 60%,#5a8bcb 100%);
  display:flex;align-items:flex-end;padding:0 12px 0;gap:8px;position:relative;overflow:hidden;
}
.mc-sun{
  position:absolute;top:8px;left:16px;
  width:20px;height:20px;background:#ffee44;border:2px solid #ddcc00;
  box-shadow:0 0 16px #ffee6688;
}
.mc-cloud{height:12px;background:#d8d8d8;border:2px solid #b8b8b8;flex-shrink:0;margin-bottom:8px}
.mc-star{position:absolute;width:2px;height:2px;background:#fff;opacity:.6}

/* Terrain row */
.mc-terrain{display:flex;height:24px}
.mc-blk{flex:1;border:1px solid rgba(0,0,0,.35)}
.g{background:#4a9e2a}.g2{background:#5ab83a}
.d{background:#6b4226}.d2{background:#7a4e30}
.s{background:#6e6e6e}.s2{background:#585858}
.o{background:#4a3b1a}

/* Skill columns */
.skill-cols{display:grid;grid-template-columns:repeat(3,1fr);gap:0}
.skill-col{
  background:#0a0805;border-top:2px solid;padding:14px 12px;
  display:flex;flex-direction:column;gap:8px;
}
.skill-col.diamond{border-color:var(--diamond)}
.skill-col.iron{border-color:#aabbcc}
.skill-col.gold{border-color:#ffcc22}
.skill-tier-label{
  font-family:'Press Start 2P',monospace;font-size:5px;letter-spacing:2px;margin-bottom:2px;
}
.diamond .skill-tier-label{color:var(--diamond)}
.iron .skill-tier-label{color:#aabbcc}
.gold .skill-tier-label{color:#ffcc22}
.skill-col-name{font-size:11px;color:#d4f0b0;font-weight:700;letter-spacing:1px}
.skill-list{list-style:none;display:flex;flex-direction:column;gap:4px}
.skill-list li{font-size:9px;color:var(--text-dim);padding-left:10px;position:relative;line-height:1.5}
.skill-list li::before{content:'›';position:absolute;left:0;color:var(--green)}

/* Underground */
.mc-underground{display:flex;height:20px}
.u{flex:1;border:1px solid rgba(0,0,0,.4);background:#1e0e05}
.u.coal{background:#181818}.u.iron2{background:#6a4e32}.u.dia{background:#0a3a4a}.u.lava{background:#cc3300}.u.gold2{background:#8a6600}

/* Ore labels */
.mc-legend{
  background:#030503;border-top:1px solid #1a0d05;
  display:flex;gap:16px;padding:8px 12px;flex-wrap:wrap;
}
.mc-ore{display:flex;align-items:center;gap:5px;font-size:8px;color:var(--text-muted)}
.ore-dot{width:8px;height:8px;border:1px solid rgba(0,0,0,.4);flex-shrink:0}

/* ─── LOADOUT ─── */
.loadout-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:1px;background:var(--green-dim)}
.weapon-card{
  background:var(--bg2);padding:14px 16px;position:relative;overflow:hidden;
  transition:background .15s;
}
.weapon-card:hover{background:#121e12}
.weapon-card::before{content:'';position:absolute;top:0;left:0;width:2px;height:100%;background:var(--green)}
.weapon-card::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(58,223,34,.03),transparent);
  pointer-events:none;
}
.wc-cat{font-size:7px;color:var(--text-dim);letter-spacing:3px;margin-bottom:4px}
.wc-name{font-size:13px;color:#fff;margin-bottom:10px;font-family:'Rajdhani',sans-serif;font-weight:700;letter-spacing:1px}
.wc-tags{display:flex;flex-wrap:wrap;gap:4px}
.tag{font-size:7px;padding:2px 7px;border:1px solid;letter-spacing:1px}
.tag-g{border-color:var(--green-dim);color:var(--text-dim)}
.tag-b{border-color:#1b3a5a;color:#7aacc0}
.tag-r{border-color:#5a1b1b;color:#c07a7a}
.wc-damage{
  position:absolute;top:12px;right:14px;
  font-family:'Press Start 2P',monospace;font-size:8px;color:var(--green);
}

/* Attachment bars */
.attach-bars{margin-top:10px;display:flex;flex-direction:column;gap:4px}
.att-row{display:flex;align-items:center;gap:6px}
.att-lbl{font-size:7px;color:var(--text-muted);width:52px;flex-shrink:0}
.att-track{flex:1;height:3px;background:#0a140a;border:1px solid #1a2a1a;overflow:hidden}
.att-fill{height:100%}

/* ─── OPERATOR STATS ─── */
.stats-card{background:var(--bg2);border:1px solid var(--green-dim);padding:16px 18px}
.stat-row{display:flex;align-items:center;gap:10px;margin-bottom:8px}
.stat-name{font-size:10px;color:var(--text-dim);width:90px;flex-shrink:0}
.stat-track{flex:1;height:6px;background:#0a140a;border:1px solid var(--green-dim);overflow:hidden;position:relative}
.stat-fill{height:100%;animation:fillIn 1.6s ease-out both}
.sf-cs{background:#dd88ff;width:95%}.sf-net{background:#88ccff;width:90%}
.sf-cpp{background:#ffcc88;width:70%}.sf-php{background:#ff8888;width:65%}
.sf-doc{background:#44ddff;width:82%}.sf-linux{background:#88ff88;width:80%}
.sf-git{background:#ffffa0;width:95%}.sf-mssql{background:#ff88cc;width:92%}
.sf-pg{background:#88aaff;width:72%}
.stat-pct{font-size:9px;color:var(--green);width:30px;text-align:right;flex-shrink:0}

/* Stat delay stagger */
.stat-row:nth-child(1) .stat-fill{animation-delay:.05s}
.stat-row:nth-child(2) .stat-fill{animation-delay:.1s}
.stat-row:nth-child(3) .stat-fill{animation-delay:.15s}
.stat-row:nth-child(4) .stat-fill{animation-delay:.2s}
.stat-row:nth-child(5) .stat-fill{animation-delay:.25s}
.stat-row:nth-child(6) .stat-fill{animation-delay:.3s}
.stat-row:nth-child(7) .stat-fill{animation-delay:.35s}
.stat-row:nth-child(8) .stat-fill{animation-delay:.4s}
.stat-row:nth-child(9) .stat-fill{animation-delay:.45s}

/* ─── FIELD INTEL ─── */
.intel-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--green-dim)}
.intel-card{
  background:var(--bg2);padding:16px 12px;text-align:center;
  position:relative;overflow:hidden;
}
.intel-card::after{
  content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--green);
  animation:scan 2.5s ease-in-out infinite;transform:scaleX(0);transform-origin:left;
}
@keyframes scan{0%{transform:scaleX(0);transform-origin:left}50%{transform:scaleX(1);transform-origin:left}51%{transform:scaleX(1);transform-origin:right}100%{transform:scaleX(0);transform-origin:right}}
.intel-card:nth-child(2)::after{animation-delay:.8s}
.intel-card:nth-child(3)::after{animation-delay:1.6s}
.ic-val{font-family:'Press Start 2P',monospace;font-size:14px;color:var(--green);margin-bottom:6px;display:block}
.ic-lbl{font-size:7px;color:var(--text-muted);letter-spacing:2px}
.ic-sub{font-size:7px;color:var(--text-muted);margin-top:2px}

/* ─── COD PRESTIGE ─── */
.prestige-section{background:var(--bg2);border:1px solid var(--green-dim);padding:16px 18px}
.prestige-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:8px}
.prestige-item{display:flex;flex-direction:column;align-items:center;gap:6px}
.prestige-badge{
  width:44px;height:44px;border:2px solid;display:grid;place-items:center;
  font-size:18px;position:relative;
  transition:transform .2s;cursor:default;
}
.prestige-badge:hover{transform:scale(1.1)}
.prestige-badge.earned{box-shadow:0 0 12px var(--green-glow)}
.prestige-badge.locked{opacity:.3;filter:grayscale(1)}
.pb-1{border-color:var(--green);background:#030803}
.pb-2{border-color:var(--blue);background:#020510}
.pb-3{border-color:var(--amber);background:#100800}
.pb-4{border-color:var(--diamond);background:#020a10}
.pb-5{border-color:var(--red);background:#100202}
.prestige-name{font-size:7px;color:var(--text-dim);text-align:center;letter-spacing:1px}

/* ─── COMMS ─── */
.comms-row{display:flex;gap:10px;flex-wrap:wrap}
.comm-btn{
  display:flex;align-items:center;gap:10px;
  background:var(--bg2);border:1px solid var(--green-dim);padding:12px 18px;
  text-decoration:none;color:var(--text);font-family:'Share Tech Mono',monospace;
  font-size:11px;letter-spacing:2px;
  transition:background .15s,border-color .15s,box-shadow .15s;cursor:pointer;
}
.comm-btn:hover{background:#162a16;border-color:var(--green);box-shadow:0 0 12px var(--green-glow)}
.comm-icon{width:18px;height:18px;border:1px solid var(--green);display:grid;place-items:center;flex-shrink:0}

/* ─── FOOTER ─── */
.ftr{
  background:#030603;border-top:2px solid var(--green-dim);
  padding:14px 28px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:8px;
}
.ftr-l{font-size:8px;color:var(--green);letter-spacing:2px;opacity:.8}
.ftr-r{font-size:8px;color:var(--text-muted);opacity:.6}
.ftr-center{font-family:'Press Start 2P',monospace;font-size:6px;color:var(--text-dim);letter-spacing:1px;text-align:center}

/* ─── ENTRANCE ─── */
.section{animation:fadeUp .5s ease-out both}
.s1{animation-delay:.05s}.s2{animation-delay:.12s}.s3{animation-delay:.19s}
.s4{animation-delay:.26s}.s5{animation-delay:.33s}.s6{animation-delay:.4s}
.s7{animation-delay:.47s}.s8{animation-delay:.54s}
@keyframes fadeUp{from{opacity:0;transform:translateY(8px)}}

/* ─── RESPONSIVE ─── */
@media(max-width:600px){
  .hdr-content{grid-template-columns:1fr}
  .loadout-grid{grid-template-columns:1fr}
  .intel-grid{grid-template-columns:repeat(2,1fr)}
  .skill-cols{grid-template-columns:1fr}
  .prestige-grid{grid-template-columns:repeat(3,1fr)}
  .op-name{font-size:12px}
  .brief-card{grid-template-columns:1fr}
}
</style>
</head>
<body>

<!-- BOOT SCREEN -->
<div id="boot">
  <div class="logo">▶ OPERATOR</div>
  <div style="font-size:8px;letter-spacing:2px;margin-bottom:12px;color:var(--text-dim)">LOADING PROFILE DATA...</div>
  <div class="bar-wrap"><div class="bar-inner"></div></div>
  <div class="log" id="boot-log">INITIALIZING...</div>
</div>

<div class="wrap" id="main" style="opacity:0">

  <!-- HEADER -->
  <div class="hdr">
    <div class="hdr-bg"></div>
    <div class="map-overlay"></div>

    <svg class="terrain-svg" viewBox="0 0 860 80" preserveAspectRatio="none" fill="none">
      <path d="M0 80 L0 50 L40 45 L80 48 L120 40 L160 42 L200 35 L240 38 L280 30 L320 33 L360 28 L400 32 L440 25 L480 28 L520 22 L560 26 L600 20 L640 24 L680 18 L720 22 L760 16 L800 20 L860 15 L860 80 Z" fill="#2d5a1b" opacity=".4"/>
      <path d="M0 80 L0 60 L60 55 L120 58 L180 52 L240 55 L300 48 L360 51 L420 45 L480 49 L540 43 L600 47 L660 41 L720 44 L780 38 L860 42 L860 80 Z" fill="#1a3a0d" opacity=".5"/>
    </svg>

    <div class="hud-corner tl"></div>
    <div class="hud-corner tr"></div>
    <div class="hud-corner bl"></div>
    <div class="hud-corner br"></div>
    <div class="crosshair"></div>

    <div class="radar">
      <div class="radar-inner">
        <div class="radar-cross"></div>
        <div class="radar-ring r1"></div>
        <div class="radar-ring r2"></div>
        <div class="radar-sweep"></div>
        <div class="radar-dot d1"></div>
        <div class="radar-dot d2"></div>
        <div class="radar-dot d3"></div>
      </div>
    </div>

    <div class="hdr-content">
      <div>
        <div class="op-badge">OPERATOR IDENTIFIED</div>
        <div class="op-name">ABD ELRAHMAN<br>ALQUDAH</div>
        <div class="op-class">BACK-END &nbsp;▸&nbsp; DEVSECOPS &nbsp;▸&nbsp; ARCHITECT</div>
        <div class="bar-group">
          <div class="bar-item">
            <span class="bar-lbl">SECURITY XP</span>
            <div class="bar-track"><div class="bar-fill bsec" style="animation-delay:.3s"></div></div>
            <span class="bar-pct">92%</span>
          </div>
          <div class="bar-item">
            <span class="bar-lbl">ARCHITECTURE</span>
            <div class="bar-track"><div class="bar-fill barch" style="animation-delay:.4s"></div></div>
            <span class="bar-pct">88%</span>
          </div>
          <div class="bar-item">
            <span class="bar-lbl">INFRASTRUCTURE</span>
            <div class="bar-track"><div class="bar-fill binfra" style="animation-delay:.5s"></div></div>
            <span class="bar-pct">78%</span>
          </div>
        </div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:center;gap:8px;padding-top:40px">
        <!-- Pixel operator SVG -->
        <svg width="60" height="80" viewBox="0 0 12 16" image-rendering="pixelated" style="width:60px;height:80px">
          <!-- head -->
          <rect x="3" y="0" width="6" height="6" fill="#8B6914"/>
          <!-- helmet -->
          <rect x="2" y="0" width="8" height="3" fill="#1a3a1a"/>
          <rect x="3" y="1" width="6" height="1" fill="#3adf22" opacity=".6"/>
          <!-- visor -->
          <rect x="3" y="2" width="6" height="2" fill="#003311"/>
          <!-- face -->
          <rect x="4" y="3" width="1" height="1" fill="#3adf22"/>
          <rect x="7" y="3" width="1" height="1" fill="#3adf22"/>
          <!-- body -->
          <rect x="2" y="6" width="8" height="6" fill="#1e2e1e"/>
          <rect x="2" y="6" width="8" height="1" fill="#2a3a2a"/>
          <!-- chest insignia -->
          <rect x="5" y="8" width="2" height="2" fill="#3adf22"/>
          <!-- left arm -->
          <rect x="0" y="6" width="2" height="5" fill="#1e2e1e"/>
          <!-- right arm -->
          <rect x="10" y="6" width="2" height="5" fill="#1e2e1e"/>
          <!-- gun -->
          <rect x="11" y="8" width="3" height="1" fill="#333"/>
          <!-- legs -->
          <rect x="2" y="12" width="3" height="4" fill="#151e15"/>
          <rect x="7" y="12" width="3" height="4" fill="#151e15"/>
          <!-- boots -->
          <rect x="2" y="15" width="3" height="1" fill="#111"/>
          <rect x="7" y="15" width="3" height="1" fill="#111"/>
        </svg>
        <div style="font-size:7px;color:var(--text-dim);letter-spacing:1px">KURTBEY</div>
        <div style="font-size:6px;color:var(--green);letter-spacing:2px">LVL 55 ✦</div>
      </div>
    </div>

    <!-- Kill feed -->
    <div class="killfeed" id="killfeed"></div>
  </div>

  <!-- TICKER -->
  <div class="ticker-wrap">
    <div class="ticker">
      <span>◼ ACTIVE OPERATOR &nbsp;•&nbsp; ASP.NET CORE &nbsp;•&nbsp; JWT AUTH &nbsp;•&nbsp; DOCKER &nbsp;•&nbsp; RBAC &nbsp;•&nbsp; CLEAN ARCHITECTURE &nbsp;•&nbsp; SQL SERVER &nbsp;•&nbsp; SOLID PRINCIPLES &nbsp;•&nbsp; LINUX &nbsp;•&nbsp; DEVSECOPS &nbsp;•&nbsp; LARAVEL &nbsp;•&nbsp; GIT &nbsp;•&nbsp; C# &nbsp;•&nbsp; POSTGRESQL &nbsp;•&nbsp; MICROSERVICES</span>
      <span>◼ ACTIVE OPERATOR &nbsp;•&nbsp; ASP.NET CORE &nbsp;•&nbsp; JWT AUTH &nbsp;•&nbsp; DOCKER &nbsp;•&nbsp; RBAC &nbsp;•&nbsp; CLEAN ARCHITECTURE &nbsp;•&nbsp; SQL SERVER &nbsp;•&nbsp; SOLID PRINCIPLES &nbsp;•&nbsp; LINUX &nbsp;•&nbsp; DEVSECOPS &nbsp;•&nbsp; LARAVEL &nbsp;•&nbsp; GIT &nbsp;•&nbsp; C# &nbsp;•&nbsp; POSTGRESQL &nbsp;•&nbsp; MICROSERVICES</span>
    </div>
  </div>

  <div class="body">

    <!-- MISSION BRIEFING -->
    <div class="section s1">
      <div class="sec-hdr">MISSION BRIEFING <span class="sec-num">01</span></div>
      <div class="brief-card">
        <div class="brief-row">
          <span class="bk">CALLSIGN</span><span class="bv">Kurtbey</span>
          <span class="bk">FACTION</span><span class="bv">GHOST SQUADRON</span>
          <span class="bk">CLEARANCE</span><span class="bv">SIGMA-7</span>
          <span class="bk">STATUS</span><span class="bv"><span class="status-dot"></span>ONLINE</span>
        </div>
        <div class="brief-row">
          <span class="bk">CLASS</span><span class="bv">Back-End Dev</span>
          <span class="bk">DOCTRINE</span><span class="bv">Secure By Design</span>
          <span class="bk">OBJECTIVE</span><span class="bv">Predictable &amp; Hardened</span>
          <span class="bk">K/D RATIO</span><span class="bv">4.7 : 1</span>
        </div>
      </div>
    </div>

    <!-- COD PRESTIGE -->
    <div class="section s2">
      <div class="sec-hdr">PRESTIGE RANKS <span class="sec-num">02</span></div>
      <div class="prestige-section">
        <div class="prestige-grid">
          <div class="prestige-item">
            <div class="prestige-badge pb-1 earned">⚔</div>
            <div class="prestige-name">ARCHITECT</div>
          </div>
          <div class="prestige-item">
            <div class="prestige-badge pb-2 earned">🛡</div>
            <div class="prestige-name">DEFENDER</div>
          </div>
          <div class="prestige-item">
            <div class="prestige-badge pb-3 earned">⚡</div>
            <div class="prestige-name">PHANTOM</div>
          </div>
          <div class="prestige-item">
            <div class="prestige-badge pb-4 earned">💎</div>
            <div class="prestige-name">DIAMOND</div>
          </div>
          <div class="prestige-item">
            <div class="prestige-badge pb-5 locked">★</div>
            <div class="prestige-name">MASTER</div>
          </div>
        </div>
        <div style="margin-top:14px;padding-top:12px;border-top:1px solid var(--green-dim)">
          <div style="font-size:8px;color:var(--text-dim);letter-spacing:1px;margin-bottom:6px">SEASONAL XP PROGRESS</div>
          <div style="display:flex;align-items:center;gap:10px">
            <div style="flex:1;height:8px;background:#0a140a;border:1px solid var(--green-dim);overflow:hidden">
              <div style="height:100%;width:73%;background:linear-gradient(90deg,var(--green),#88ffaa);animation:fillIn 2s ease-out both;animation-delay:.6s"></div>
            </div>
            <span style="font-family:'Press Start 2P',monospace;font-size:8px;color:var(--green)">73%</span>
          </div>
        </div>
      </div>
    </div>

    <!-- MINECRAFT SKILL WORLD -->
    <div class="section s3">
      <div class="sec-hdr">SKILL WORLD — MINECRAFT MODE <span class="sec-num">03</span></div>
      <div class="mc-world">
        <div class="mc-sky">
          <div class="mc-sun"></div>
          <div class="mc-cloud" style="width:48px;margin-left:44px"></div>
          <div class="mc-cloud" style="width:32px;margin-left:12px"></div>
          <div class="mc-cloud" style="width:22px;margin-left:30px"></div>
          <!-- pixel stars -->
          <div class="mc-star" style="top:6px;right:80px"></div>
          <div class="mc-star" style="top:12px;right:140px;opacity:.4"></div>
          <div class="mc-star" style="top:4px;right:200px;opacity:.7"></div>
        </div>
        <div class="mc-terrain">
          <div class="mc-blk g2"></div><div class="mc-blk g"></div><div class="mc-blk g2"></div><div class="mc-blk g"></div><div class="mc-blk g2"></div>
          <div class="mc-blk d2"></div><div class="mc-blk d"></div><div class="mc-blk d2"></div><div class="mc-blk d"></div><div class="mc-blk d2"></div>
          <div class="mc-blk s2"></div><div class="mc-blk s"></div><div class="mc-blk s2"></div><div class="mc-blk s"></div><div class="mc-blk s2"></div>
        </div>
        <div class="skill-cols">
          <div class="skill-col diamond">
            <div class="skill-tier-label">◆ DIAMOND TIER</div>
            <div class="skill-col-name">Architecture</div>
            <ul class="skill-list">
              <li>Clean Architecture</li>
              <li>SOLID Principles</li>
              <li>DDD Patterns</li>
              <li>Microservices</li>
            </ul>
          </div>
          <div class="skill-col iron">
            <div class="skill-tier-label">⬛ IRON TIER</div>
            <div class="skill-col-name">Security</div>
            <ul class="skill-list">
              <li>JWT / OAuth2</li>
              <li>RBAC Systems</li>
              <li>Hardened APIs</li>
              <li>DevSecOps</li>
            </ul>
          </div>
          <div class="skill-col gold">
            <div class="skill-tier-label">★ GOLD TIER</div>
            <div class="skill-col-name">Infrastructure</div>
            <ul class="skill-list">
              <li>Docker / K8s</li>
              <li>Linux Admin</li>
              <li>Git Workflows</li>
              <li>CI/CD Pipelines</li>
            </ul>
          </div>
        </div>
        <div class="mc-underground">
          <div class="u"></div><div class="u coal"></div><div class="u"></div><div class="u iron2"></div><div class="u"></div>
          <div class="u coal"></div><div class="u dia"></div><div class="u"></div><div class="u gold2"></div><div class="u"></div>
          <div class="u lava"></div><div class="u"></div><div class="u coal"></div><div class="u dia"></div><div class="u iron2"></div>
        </div>
        <div class="mc-legend">
          <div class="mc-ore"><div class="ore-dot" style="background:#181818"></div>Coal = Core Logic</div>
          <div class="mc-ore"><div class="ore-dot" style="background:#6a4e32"></div>Iron = Security</div>
          <div class="mc-ore"><div class="ore-dot" style="background:#0a3a4a"></div>Diamond = Architecture</div>
          <div class="mc-ore"><div class="ore-dot" style="background:#8a6600"></div>Gold = Infrastructure</div>
          <div class="mc-ore"><div class="ore-dot" style="background:#cc3300"></div>Lava = Hot Deployments</div>
        </div>
      </div>
    </div>

    <!-- LOADOUT -->
    <div class="section s4">
      <div class="sec-hdr">OPERATOR LOADOUT <span class="sec-num">04</span></div>
      <div class="loadout-grid">
        <div class="weapon-card">
          <div class="wc-cat">PRIMARY WEAPON</div>
          <div class="wc-name">ASP.NET Core</div>
          <div class="wc-damage">95 DMG</div>
          <div class="wc-tags">
            <span class="tag tag-g">C#</span>
            <span class="tag tag-g">REST API</span>
            <span class="tag tag-g">gRPC</span>
            <span class="tag tag-b">EXPERT</span>
          </div>
          <div class="attach-bars">
            <div class="att-row"><span class="att-lbl">RANGE</span><div class="att-track"><div class="att-fill" style="width:90%;background:var(--green)"></div></div></div>
            <div class="att-row"><span class="att-lbl">DAMAGE</span><div class="att-track"><div class="att-fill" style="width:95%;background:var(--red)"></div></div></div>
            <div class="att-row"><span class="att-lbl">CONTROL</span><div class="att-track"><div class="att-fill" style="width:88%;background:var(--blue)"></div></div></div>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">SECONDARY WEAPON</div>
          <div class="wc-name">Laravel / PHP</div>
          <div class="wc-damage">65 DMG</div>
          <div class="wc-tags">
            <span class="tag tag-g">MVC</span>
            <span class="tag tag-g">Eloquent</span>
            <span class="tag tag-b">ADVANCED</span>
          </div>
          <div class="attach-bars">
            <div class="att-row"><span class="att-lbl">RANGE</span><div class="att-track"><div class="att-fill" style="width:70%;background:var(--green)"></div></div></div>
            <div class="att-row"><span class="att-lbl">DAMAGE</span><div class="att-track"><div class="att-fill" style="width:65%;background:var(--red)"></div></div></div>
            <div class="att-row"><span class="att-lbl">CONTROL</span><div class="att-track"><div class="att-fill" style="width:75%;background:var(--blue)"></div></div></div>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">TACTICAL EQUIPMENT</div>
          <div class="wc-name">Docker + Linux</div>
          <div class="wc-damage">82 DMG</div>
          <div class="wc-tags">
            <span class="tag tag-g">Containers</span>
            <span class="tag tag-g">CI/CD</span>
            <span class="tag tag-b">ADVANCED</span>
          </div>
          <div class="attach-bars">
            <div class="att-row"><span class="att-lbl">RANGE</span><div class="att-track"><div class="att-fill" style="width:82%;background:var(--green)"></div></div></div>
            <div class="att-row"><span class="att-lbl">UPTIME</span><div class="att-track"><div class="att-fill" style="width:95%;background:var(--amber)"></div></div></div>
            <div class="att-row"><span class="att-lbl">SPEED</span><div class="att-track"><div class="att-fill" style="width:78%;background:var(--blue)"></div></div></div>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">DATABASE ORDNANCE</div>
          <div class="wc-name">SQL Server / PG</div>
          <div class="wc-damage">92 DMG</div>
          <div class="wc-tags">
            <span class="tag tag-g">MSSQL</span>
            <span class="tag tag-g">MySQL</span>
            <span class="tag tag-g">PostgreSQL</span>
            <span class="tag tag-b">EXPERT</span>
          </div>
          <div class="attach-bars">
            <div class="att-row"><span class="att-lbl">QUERY SPD</span><div class="att-track"><div class="att-fill" style="width:92%;background:var(--green)"></div></div></div>
            <div class="att-row"><span class="att-lbl">RELIABILITY</span><div class="att-track"><div class="att-fill" style="width:98%;background:var(--amber)"></div></div></div>
            <div class="att-row"><span class="att-lbl">SCALE</span><div class="att-track"><div class="att-fill" style="width:85%;background:var(--blue)"></div></div></div>
          </div>
        </div>
      </div>
    </div>

    <!-- OPERATOR STATS -->
    <div class="section s5">
      <div class="sec-hdr">OPERATOR STATS <span class="sec-num">05</span></div>
      <div class="stats-card">
        <div class="stat-row"><div class="stat-name">C# / .NET</div><div class="stat-track"><div class="stat-fill sf-cs"></div></div><div class="stat-pct">95%</div></div>
        <div class="stat-row"><div class="stat-name">ASP.NET Core</div><div class="stat-track"><div class="stat-fill sf-net"></div></div><div class="stat-pct">90%</div></div>
        <div class="stat-row"><div class="stat-name">C++</div><div class="stat-track"><div class="stat-fill sf-cpp"></div></div><div class="stat-pct">70%</div></div>
        <div class="stat-row"><div class="stat-name">PHP / Laravel</div><div class="stat-track"><div class="stat-fill sf-php"></div></div><div class="stat-pct">65%</div></div>
        <div class="stat-row"><div class="stat-name">Docker</div><div class="stat-track"><div class="stat-fill sf-doc"></div></div><div class="stat-pct">82%</div></div>
        <div class="stat-row"><div class="stat-name">Linux Admin</div><div class="stat-track"><div class="stat-fill sf-linux"></div></div><div class="stat-pct">80%</div></div>
        <div class="stat-row"><div class="stat-name">Git</div><div class="stat-track"><div class="stat-fill sf-git"></div></div><div class="stat-pct">95%</div></div>
        <div class="stat-row"><div class="stat-name">SQL Server</div><div class="stat-track"><div class="stat-fill sf-mssql"></div></div><div class="stat-pct">92%</div></div>
        <div class="stat-row"><div class="stat-name">PostgreSQL</div><div class="stat-track"><div class="stat-fill sf-pg"></div></div><div class="stat-pct">72%</div></div>
      </div>
    </div>

    <!-- FIELD INTEL -->
    <div class="section s6">
      <div class="sec-hdr">FIELD INTEL <span class="sec-num">06</span></div>
      <div class="intel-grid">
        <div class="intel-card">
          <span class="ic-val">∞</span>
          <div class="ic-lbl">COMMITS</div>
          <div class="ic-sub">ALL-TIME</div>
        </div>
        <div class="intel-card">
          <span class="ic-val" id="streak-val">0</span>
          <div class="ic-lbl">DAY STREAK</div>
          <div class="ic-sub">CURRENT</div>
        </div>
        <div class="intel-card">
          <span class="ic-val">100%</span>
          <div class="ic-lbl">SECURE BUILDS</div>
          <div class="ic-sub">ZERO BREACHES</div>
        </div>
        <div class="intel-card">
          <span class="ic-val">4.7</span>
          <div class="ic-lbl">K/D RATIO</div>
          <div class="ic-sub">BUG/FEATURE</div>
        </div>
        <div class="intel-card">
          <span class="ic-val" id="uptime-val">99.9</span>
          <div class="ic-lbl">UPTIME %</div>
          <div class="ic-sub">PRODUCTION</div>
        </div>
        <div class="intel-card">
          <span class="ic-val">LVL 55</span>
          <div class="ic-lbl">PRESTIGE</div>
          <div class="ic-sub">MAX RANK</div>
        </div>
      </div>
    </div>

    <!-- COMMS -->
    <div class="section s7">
      <div class="sec-hdr">ESTABLISH COMMS <span class="sec-num">07</span></div>
      <div class="comms-row">
        <a class="comm-btn" href="https://www.linkedin.com/in/abd-elarhman/" target="_blank" rel="noopener">
          <div class="comm-icon">
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none">
              <rect x="0" y="3" width="2" height="7" fill="var(--green)"/>
              <rect x="0" y="0" width="2" height="2" fill="var(--green)"/>
              <rect x="3" y="3" width="2" height="7" fill="var(--green)"/>
              <rect x="3" y="3" width="7" height="2" fill="var(--green)"/>
              <rect x="8" y="5" width="2" height="5" fill="var(--green)"/>
            </svg>
          </div>
          ▸ LINKEDIN
        </a>
        <a class="comm-btn" href="https://github.com/Kurtbey1" target="_blank" rel="noopener">
          <div class="comm-icon">
            <svg width="12" height="12" viewBox="0 0 12 12" fill="none">
              <path d="M6 0C2.69 0 0 2.75 0 6.15c0 2.72 1.72 5.02 4.1 5.83.3.06.41-.13.41-.29v-1.04c-1.66.37-2.01-.81-2.01-.81-.27-.7-.66-.88-.66-.88-.54-.37.04-.37.04-.37.6.04.92.63.92.63.53.93 1.4.66 1.74.5.05-.39.21-.66.38-.81-1.33-.15-2.73-.68-2.73-3.01 0-.66.23-1.2.61-1.63-.06-.15-.27-.77.06-1.6 0 0 .5-.16 1.63.62a5.53 5.53 0 0 1 1.48-.2c.5.01 1 .07 1.48.2 1.13-.78 1.62-.62 1.62-.62.33.83.12 1.45.06 1.6.38.43.61.97.61 1.63 0 2.34-1.4 2.86-2.74 3.01.22.19.41.56.41 1.13v1.68c0 .16.11.36.41.29A6.17 6.17 0 0 0 12 6.15C12 2.75 9.31 0 6 0z" fill="var(--green)"/>
            </svg>
          </div>
          ▸ GITHUB
        </a>
        <a class="comm-btn" href="mailto:kurtbey@example.com">
          <div class="comm-icon">
            <svg width="12" height="10" viewBox="0 0 12 10" fill="none">
              <rect x="0" y="0" width="12" height="10" rx="1" stroke="var(--green)" stroke-width="1" fill="none"/>
              <path d="M0 1 L6 6 L12 1" stroke="var(--green)" stroke-width="1" fill="none"/>
            </svg>
          </div>
          ▸ EMAIL
        </a>
      </div>
    </div>

  </div>

  <!-- FOOTER -->
  <div class="ftr">
    <div class="ftr-l">◼ STAY SOLID. STAY SECURE. STAY HARDENED.</div>
    <div class="ftr-center">ABD ELRAHMAN ALQUDAH // KURTBEY1<br><span style="color:var(--text-muted);font-size:6px">BACK-END OPERATOR — GHOST SQUADRON</span></div>
    <div class="ftr-r">BUILD v4.7.2025</div>
  </div>

</div>

<script>
// Boot sequence
const bootLogs = [
  'MOUNTING FILESYSTEM...',
  'LOADING OPERATOR DATA...',
  'VERIFYING CLEARANCE...',
  'DECRYPTING PROFILE...',
  'ESTABLISHING COMMS...',
  'PROFILE READY.',
];
let li = 0;
const logEl = document.getElementById('boot-log');
const logInt = setInterval(() => {
  if (li < bootLogs.length) {
    logEl.textContent = bootLogs[li++];
  } else {
    clearInterval(logInt);
  }
}, 340);

setTimeout(() => {
  const boot = document.getElementById('boot');
  const main = document.getElementById('main');
  boot.style.transition = 'opacity .4s';
  boot.style.opacity = '0';
  setTimeout(() => {
    boot.style.display = 'none';
    main.style.opacity = '1';
    main.style.transition = 'opacity .4s';
  }, 400);
}, 2600);

// Streak counter
const sv = document.getElementById('streak-val');
let n = 0;
const t = setInterval(() => {
  n += Math.floor(Math.random() * 6) + 2;
  if (sv) sv.textContent = n;
  if (n >= 47) { if (sv) sv.textContent = '47'; clearInterval(t); }
}, 55);

// Uptime counter
const uv = document.getElementById('uptime-val');
let up = 97.2;
const ut = setInterval(() => {
  up = Math.min(99.9, up + (Math.random() * .4));
  if (uv) uv.textContent = up.toFixed(1);
  if (up >= 99.9) { if (uv) uv.textContent = '99.9'; clearInterval(ut); }
}, 80);

// Kill feed
const kills = [
  ['KURTBEY', 'SPAGHETTI CODE', 'CLEAN ARCH'],
  ['KURTBEY', 'SQL INJECTION', 'RBAC'],
  ['KURTBEY', 'MEMORY LEAK', 'PROFILER'],
  ['KURTBEY', 'RACE CONDITION', 'MUTEX LOCK'],
  ['KURTBEY', 'N+1 QUERY', 'EAGER LOAD'],
  ['KURTBEY', 'NULL REF', 'NULL SAFETY'],
  ['KURTBEY', 'TECH DEBT', 'REFACTOR'],
];
const kf = document.getElementById('killfeed');
let ki = 0;
function addKill() {
  const k = kills[ki % kills.length];
  const row = document.createElement('div');
  row.className = 'kf-row';
  row.innerHTML = `<span class="kf-attacker">${k[0]}</span><span class="kf-icon">⊕</span><span class="kf-weapon">${k[2]}</span><span style="color:rgba(255,255,255,.4)">eliminated</span><span class="kf-victim">${k[1]}</span>`;
  kf.insertBefore(row, kf.firstChild);
  if (kf.children.length > 3) kf.removeChild(kf.lastChild);
  ki++;
}
// Initial kills
setTimeout(() => addKill(), 3000);
setTimeout(() => addKill(), 5500);
setTimeout(() => addKill(), 8200);
setInterval(() => addKill(), 5000);
</script>
</body>
</html>
