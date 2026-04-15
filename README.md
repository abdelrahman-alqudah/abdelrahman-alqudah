
<style>
  @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Press+Start+2P&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    background: #0a0c0a;
    font-family: 'Share Tech Mono', monospace;
    color: #c8f0a0;
    overflow: hidden;
    border-radius: 12px;
    position: relative;
  }

  /* ── SCANLINE OVERLAY ── */
  .profile-root::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(0deg, transparent, transparent 3px, rgba(0,0,0,0.08) 3px, rgba(0,0,0,0.08) 4px);
    pointer-events: none;
    z-index: 100;
  }

  /* ── HEADER ── */
  .hdr {
    position: relative;
    background: #0d1a0d;
    border-bottom: 2px solid #2d5a1b;
    padding: 28px 28px 20px;
    overflow: hidden;
  }

  /* Minecraft pixel sky backdrop */
  .sky-blocks {
    position: absolute;
    top: 0; right: 0;
    width: 220px; height: 100%;
    display: grid;
    grid-template-columns: repeat(11, 20px);
    grid-template-rows: repeat(7, 20px);
    opacity: 0.35;
  }
  .bl { width: 20px; height: 20px; }
  .bl-sky  { background: #3a6bab; border: 1px solid #2d5490; }
  .bl-cld  { background: #c8c8c8; border: 1px solid #a0a0a0; }
  .bl-lf   { background: #3d8c2a; border: 1px solid #2d6a1e; }
  .bl-dk   { background: #1a4010; border: 1px solid #102a08; }
  .bl-stn  { background: #5a5a5a; border: 1px solid #404040; }
  .bl-drt  { background: #6b4226; border: 1px solid #4e3019; }
  .bl-tr   { background: #2d4d1e; border: 1px solid #1e3413; }

  /* CoD HUD crosshair top-left */
  .crosshair {
    position: absolute;
    top: 16px; left: 16px;
    width: 24px; height: 24px;
    opacity: 0.5;
  }
  .crosshair::before, .crosshair::after {
    content: '';
    position: absolute;
    background: #5aff3c;
  }
  .crosshair::before { width: 2px; height: 100%; left: 50%; transform: translateX(-50%); }
  .crosshair::after  { width: 100%; height: 2px; top: 50%; transform: translateY(-50%); }

  /* CoD corner brackets */
  .brackets {
    position: absolute;
    inset: 10px;
    pointer-events: none;
  }
  .bk {
    position: absolute;
    width: 18px; height: 18px;
    border-color: #4adf28;
    border-style: solid;
    opacity: 0.6;
  }
  .bk-tl { top: 0; left: 0; border-width: 2px 0 0 2px; }
  .bk-tr { top: 0; right: 0; border-width: 2px 2px 0 0; }
  .bk-bl { bottom: 0; left: 0; border-width: 0 0 2px 2px; }
  .bk-br { bottom: 0; right: 0; border-width: 0 2px 2px 0; }

  .op-label {
    font-size: 10px;
    color: #5aff3c;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 6px;
    opacity: 0.8;
  }

  .op-name {
    font-family: 'Press Start 2P', monospace;
    font-size: 15px;
    color: #ffffff;
    line-height: 1.5;
    text-shadow: 0 0 12px #3aff1a88;
    margin-bottom: 4px;
  }

  .op-sub {
    font-size: 11px;
    color: #7acc50;
    letter-spacing: 2px;
    margin-bottom: 18px;
  }

  /* Health / XP bars */
  .bars-row {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }
  .bar-item {
    display: flex;
    flex-direction: column;
    gap: 4px;
    min-width: 140px;
  }
  .bar-lbl {
    font-size: 9px;
    color: #5aff3c;
    letter-spacing: 2px;
  }
  .bar-track {
    height: 8px;
    background: #1a2e1a;
    border: 1px solid #2d5a1b;
    position: relative;
    overflow: hidden;
  }
  .bar-fill {
    height: 100%;
    position: relative;
    animation: fillIn 1.2s ease-out forwards;
    transform-origin: left;
  }
  .bar-fill::after {
    content: '';
    position: absolute;
    right: 0; top: 0; bottom: 0;
    width: 3px;
    background: #fff;
    opacity: 0.6;
    animation: pulse 1.4s ease-in-out infinite;
  }
  @keyframes fillIn { from { width: 0 !important; } }
  @keyframes pulse { 0%,100%{opacity:0.3} 50%{opacity:0.9} }

  .bar-security { background: #3adf22; width: 92%; }
  .bar-arch     { background: #22aaff; width: 88%; }
  .bar-infra    { background: #ffaa22; width: 78%; }

  /* Pixel avatar */
  .avatar-wrap {
    position: absolute;
    bottom: 0; right: 28px;
    width: 80px; height: 90px;
  }

  /* ── BODY ── */
  .body { padding: 20px 28px; display: flex; flex-direction: column; gap: 20px; }

  /* Section label */
  .sec-label {
    font-size: 9px;
    color: #5aff3c;
    letter-spacing: 3px;
    border-left: 3px solid #3adf22;
    padding-left: 8px;
    margin-bottom: 10px;
  }

  /* ── MISSION BRIEFING ── */
  .briefing {
    background: #0d1a0d;
    border: 1px solid #2d5a1b;
    padding: 14px 16px;
    position: relative;
  }
  .briefing::before {
    content: 'CLASSIFIED';
    position: absolute;
    top: -8px; right: 12px;
    font-size: 8px;
    background: #c8310a;
    color: #fff;
    padding: 2px 8px;
    letter-spacing: 2px;
  }
  .brief-row {
    display: grid;
    grid-template-columns: 90px 1fr;
    gap: 2px 8px;
    font-size: 11px;
    line-height: 1.9;
  }
  .brief-key { color: #5aff3c; opacity: 0.7; }
  .brief-val { color: #d4f0b0; }

  /* ── MINECRAFT SKILL TREE ── */
  .skill-world {
    background: #0d1a0d;
    border: 1px solid #2d5a1b;
    padding: 14px;
    position: relative;
  }

  .mc-world {
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  /* Sky strip */
  .mc-sky {
    height: 36px;
    background: #3a6bab;
    display: flex;
    align-items: center;
    padding: 0 10px;
    gap: 6px;
    position: relative;
    overflow: hidden;
  }
  .mc-sun {
    width: 24px; height: 24px;
    background: #ffee44;
    border: 3px solid #ddcc00;
    flex-shrink: 0;
  }
  .mc-cloud {
    height: 14px;
    background: #e0e0e0;
    border: 2px solid #c0c0c0;
    flex-shrink: 0;
  }

  /* Terrain strip */
  .mc-terrain {
    height: 20px;
    display: flex;
  }
  .mc-blk {
    flex: 1;
    border: 1px solid rgba(0,0,0,0.3);
  }
  .g { background: #4a9e2a; }
  .d { background: #6b4226; }
  .s { background: #6e6e6e; }
  .o { background: #4a3b1a; }

  /* Skill columns */
  .skill-cols {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
    background: #1a0d05;
    padding: 10px 8px;
    border-top: 2px solid #2d1a08;
  }

  .skill-col {
    background: #0d0a06;
    border: 2px solid;
    padding: 10px 8px;
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  .skill-col.diamond { border-color: #44ccee; }
  .skill-col.iron    { border-color: #aabbcc; }
  .skill-col.gold    { border-color: #ffcc22; }

  .skill-icon {
    width: 24px; height: 24px;
    border: 2px solid rgba(255,255,255,0.15);
    display: grid;
    place-items: center;
    font-size: 14px;
    flex-shrink: 0;
  }

  .skill-tier {
    font-family: 'Press Start 2P', monospace;
    font-size: 6px;
    letter-spacing: 1px;
  }
  .diamond .skill-tier { color: #44ccee; }
  .iron    .skill-tier { color: #aabbcc; }
  .gold    .skill-tier { color: #ffcc22; }

  .skill-name {
    font-size: 10px;
    color: #d4f0b0;
    font-weight: bold;
    margin-bottom: 2px;
  }
  .skill-items {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 3px;
  }
  .skill-items li {
    font-size: 9px;
    color: #7acc50;
    padding-left: 8px;
    position: relative;
  }
  .skill-items li::before {
    content: '›';
    position: absolute;
    left: 0;
    color: #3adf22;
  }

  /* Underground strip */
  .mc-underground {
    height: 18px;
    display: flex;
  }
  .u { background: #2a1a0a; border: 1px solid #1a0d05; flex: 1; }
  .u.coal { background: #1a1a1a; }
  .u.iron2 { background: #7a5a3a; }
  .u.diamond2 { background: #1a4a5a; }
  .u.lava { background: #cc3300; }

  /* ── LOADOUT GRID ── */
  .loadout-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 8px;
  }

  .weapon-card {
    background: #0d1a0d;
    border: 1px solid #2d5a1b;
    padding: 10px 12px;
    position: relative;
    overflow: hidden;
  }
  .weapon-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: #3adf22;
  }
  .wc-cat {
    font-size: 8px;
    color: #5aff3c;
    letter-spacing: 2px;
    margin-bottom: 4px;
  }
  .wc-name {
    font-size: 12px;
    color: #ffffff;
    margin-bottom: 8px;
  }
  .wc-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 4px;
  }
  .tag {
    font-size: 8px;
    padding: 2px 6px;
    border: 1px solid;
    letter-spacing: 1px;
  }
  .tag-g { border-color: #2d5a1b; color: #7acc50; }
  .tag-b { border-color: #1b3a5a; color: #7aacc0; }

  /* ── STAT BARS (full loadout) ── */
  .stat-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 6px;
  }
  .stat-name { font-size: 10px; color: #7acc50; width: 90px; flex-shrink: 0; }
  .stat-track {
    flex: 1;
    height: 6px;
    background: #1a2e1a;
    border: 1px solid #2d5a1b;
    overflow: hidden;
  }
  .stat-fill {
    height: 100%;
    animation: fillIn 1.4s ease-out forwards;
  }
  .sf-cs    { background: #c8f; width: 95%; }
  .sf-net   { background: #8cf; width: 90%; }
  .sf-cpp   { background: #fc8; width: 70%; }
  .sf-php   { background: #f88; width: 65%; }
  .sf-doc   { background: #4df; width: 82%; }
  .sf-linux { background: #8f8; width: 80%; }
  .sf-git   { background: #ffa; width: 95%; }
  .sf-mssql { background: #f4a; width: 92%; }
  .sf-pg    { background: #8af; width: 72%; }
  .stat-pct { font-size: 9px; color: #5aff3c; width: 30px; text-align: right; flex-shrink: 0; }

  /* ── INTEL / GITHUB CARDS ── */
  .intel-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
  }
  .intel-card {
    background: #0d1a0d;
    border: 1px solid #2d5a1b;
    padding: 12px 10px;
    text-align: center;
  }
  .ic-val {
    font-family: 'Press Start 2P', monospace;
    font-size: 13px;
    color: #5aff3c;
    margin-bottom: 4px;
  }
  .ic-lbl { font-size: 8px; color: #7acc50; letter-spacing: 1px; }

  /* ── COMMS ── */
  .comms-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }
  .comm-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    background: #0d1a0d;
    border: 1px solid #2d5a1b;
    padding: 10px 16px;
    text-decoration: none;
    color: #c8f0a0;
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    letter-spacing: 2px;
    transition: background 0.15s, border-color 0.15s;
    cursor: pointer;
  }
  .comm-btn:hover { background: #162a16; border-color: #5aff3c; }
  .comm-icon {
    width: 16px; height: 16px;
    border: 1px solid #5aff3c;
    display: grid;
    place-items: center;
    flex-shrink: 0;
  }

  /* ── FOOTER ── */
  .ftr {
    background: #060e06;
    border-top: 2px solid #2d5a1b;
    padding: 12px 28px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 8px;
  }
  .ftr-left { font-size: 9px; color: #3adf22; letter-spacing: 2px; opacity: 0.7; }
  .ftr-right { font-size: 9px; color: #3adf22; opacity: 0.5; }

  /* ping dot */
  .ping {
    display: inline-block;
    width: 7px; height: 7px;
    background: #3adf22;
    border-radius: 50%;
    margin-right: 6px;
    animation: blink 1.4s step-end infinite;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.1} }

  /* Scrolling ticker */
  .ticker-wrap {
    background: #060e06;
    border-top: 1px solid #2d5a1b;
    border-bottom: 1px solid #2d5a1b;
    overflow: hidden;
    height: 22px;
    display: flex;
    align-items: center;
  }
  .ticker {
    display: flex;
    gap: 40px;
    white-space: nowrap;
    animation: tick 22s linear infinite;
    font-size: 9px;
    color: #5aff3c;
    letter-spacing: 2px;
  }
  @keyframes tick { from { transform: translateX(0); } to { transform: translateX(-50%); } }

  /* Animated entrance */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
  .body > * { animation: fadeUp 0.5s ease-out both; }
  .body > *:nth-child(1) { animation-delay: 0.1s; }
  .body > *:nth-child(2) { animation-delay: 0.2s; }
  .body > *:nth-child(3) { animation-delay: 0.3s; }
  .body > *:nth-child(4) { animation-delay: 0.4s; }
  .body > *:nth-child(5) { animation-delay: 0.5s; }
  .body > *:nth-child(6) { animation-delay: 0.6s; }

  @media (max-width: 520px) {
    .loadout-grid { grid-template-columns: 1fr; }
    .intel-row { grid-template-columns: repeat(2, 1fr); }
    .skill-cols { grid-template-columns: 1fr; }
    .op-name { font-size: 11px; }
    .bars-row { gap: 10px; }
    .bar-item { min-width: 120px; }
  }
</style>

<h2 class="sr-only">GitHub profile for Abd Elrahman Alqudah — Back-End Developer and DevSecOps engineer with skills in ASP.NET Core, Docker, and security-first architecture.</h2>

<div class="profile-root">

  <!-- HEADER -->
  <div class="hdr">
    <div class="crosshair"></div>
    <div class="brackets">
      <div class="bk bk-tl"></div>
      <div class="bk bk-tr"></div>
      <div class="bk bk-bl"></div>
      <div class="bk bk-br"></div>
    </div>

    <!-- Minecraft sky blocks (decorative) -->
    <div class="sky-blocks" aria-hidden="true">
      <div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div>
      <div class="bl bl-sky"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-cld"></div><div class="bl bl-sky"></div>
      <div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div><div class="bl bl-sky"></div>
      <div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div><div class="bl bl-lf"></div>
      <div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div><div class="bl bl-dk"></div>
      <div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div><div class="bl bl-stn"></div>
      <div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div><div class="bl bl-drt"></div>
    </div>

    <div style="position:relative;z-index:2;padding-left:30px;">
      <div class="op-label">&#x25BA; OPERATOR DETECTED</div>
      <div class="op-name">ABD ELRAHMAN<br>ALQUDAH</div>
      <div class="op-sub">BACK-END &nbsp;&#x2022;&nbsp; DEVSECOPS &nbsp;&#x2022;&nbsp; ARCHITECT</div>
      <div class="bars-row">
        <div class="bar-item">
          <div class="bar-lbl">SECURITY XP</div>
          <div class="bar-track"><div class="bar-fill bar-security"></div></div>
        </div>
        <div class="bar-item">
          <div class="bar-lbl">ARCHITECTURE</div>
          <div class="bar-track"><div class="bar-fill bar-arch"></div></div>
        </div>
        <div class="bar-item">
          <div class="bar-lbl">INFRASTRUCTURE</div>
          <div class="bar-track"><div class="bar-fill bar-infra"></div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- TICKER -->
  <div class="ticker-wrap" aria-hidden="true">
    <div class="ticker">
      <span>&#x25A0; ACTIVE OPERATOR &nbsp;&#x2022;&nbsp; ASP.NET CORE &nbsp;&#x2022;&nbsp; JWT AUTH &nbsp;&#x2022;&nbsp; DOCKER &nbsp;&#x2022;&nbsp; RBAC &nbsp;&#x2022;&nbsp; CLEAN ARCHITECTURE &nbsp;&#x2022;&nbsp; SQL SERVER &nbsp;&#x2022;&nbsp; SOLID PRINCIPLES &nbsp;&#x2022;&nbsp; LINUX &nbsp;&#x2022;&nbsp; DEVSECOPS &nbsp;&#x2022;&nbsp; LARAVEL</span>
      <span>&#x25A0; ACTIVE OPERATOR &nbsp;&#x2022;&nbsp; ASP.NET CORE &nbsp;&#x2022;&nbsp; JWT AUTH &nbsp;&#x2022;&nbsp; DOCKER &nbsp;&#x2022;&nbsp; RBAC &nbsp;&#x2022;&nbsp; CLEAN ARCHITECTURE &nbsp;&#x2022;&nbsp; SQL SERVER &nbsp;&#x2022;&nbsp; SOLID PRINCIPLES &nbsp;&#x2022;&nbsp; LINUX &nbsp;&#x2022;&nbsp; DEVSECOPS &nbsp;&#x2022;&nbsp; LARAVEL</span>
    </div>
  </div>

  <div class="body">

    <!-- MISSION BRIEFING -->
    <div>
      <div class="sec-label">MISSION BRIEFING</div>
      <div class="briefing">
        <div class="brief-row">
          <span class="brief-key">CALLSIGN</span><span class="brief-val">Kurtbey</span>
          <span class="brief-key">CLASS</span><span class="brief-val">Back-End Developer</span>
          <span class="brief-key">DOCTRINE</span><span class="brief-val">Secure By Design</span>
          <span class="brief-key">OBJECTIVE</span><span class="brief-val">Predictable. Hardened. Stable.</span>
          <span class="brief-key">STATUS</span><span class="brief-val"><span class="ping"></span>ONLINE</span>
        </div>
      </div>
    </div>

    <!-- MINECRAFT SKILL WORLD -->
    <div>
      <div class="sec-label">SKILL WORLD</div>
      <div class="skill-world">
        <div class="mc-world">
          <div class="mc-sky" aria-hidden="true">
            <div class="mc-sun"></div>
            <div class="mc-cloud" style="width:40px"></div>
            <div class="mc-cloud" style="width:28px; margin-left:14px;"></div>
          </div>
          <div class="mc-terrain" aria-hidden="true">
            <div class="mc-blk g"></div><div class="mc-blk g"></div><div class="mc-blk g"></div><div class="mc-blk g"></div><div class="mc-blk g"></div>
            <div class="mc-blk d"></div><div class="mc-blk d"></div><div class="mc-blk d"></div><div class="mc-blk d"></div><div class="mc-blk d"></div>
            <div class="mc-blk s"></div><div class="mc-blk s"></div><div class="mc-blk s"></div><div class="mc-blk s"></div><div class="mc-blk s"></div>
          </div>
          <div class="skill-cols">
            <div class="skill-col diamond">
              <div class="skill-tier">DIAMOND</div>
              <div class="skill-name">Architecture</div>
              <ul class="skill-items">
                <li>Clean Architecture</li>
                <li>SOLID Principles</li>
                <li>DDD patterns</li>
              </ul>
            </div>
            <div class="skill-col iron">
              <div class="skill-tier">IRON</div>
              <div class="skill-name">Security</div>
              <ul class="skill-items">
                <li>JWT Auth</li>
                <li>RBAC Systems</li>
                <li>Hardened APIs</li>
              </ul>
            </div>
            <div class="skill-col gold">
              <div class="skill-tier">GOLD</div>
              <div class="skill-name">Infrastructure</div>
              <ul class="skill-items">
                <li>Docker</li>
                <li>Linux Admin</li>
                <li>Git workflows</li>
              </ul>
            </div>
          </div>
          <div class="mc-underground" aria-hidden="true">
            <div class="u"></div><div class="u coal"></div><div class="u"></div><div class="u iron2"></div><div class="u"></div>
            <div class="u coal"></div><div class="u"></div><div class="u diamond2"></div><div class="u"></div><div class="u"></div>
            <div class="u lava"></div><div class="u"></div><div class="u coal"></div><div class="u diamond2"></div><div class="u"></div>
          </div>
        </div>
      </div>
    </div>

    <!-- LOADOUT -->
    <div>
      <div class="sec-label">LOADOUT — WEAPONS</div>
      <div class="loadout-grid">
        <div class="weapon-card">
          <div class="wc-cat">PRIMARY</div>
          <div class="wc-name">ASP.NET Core</div>
          <div class="wc-tags">
            <span class="tag tag-g">C#</span>
            <span class="tag tag-g">REST API</span>
            <span class="tag tag-b">EXPERT</span>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">SECONDARY</div>
          <div class="wc-name">Laravel / PHP</div>
          <div class="wc-tags">
            <span class="tag tag-g">MVC</span>
            <span class="tag tag-g">Eloquent</span>
            <span class="tag tag-b">ADV</span>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">EQUIPMENT</div>
          <div class="wc-name">Docker + Linux</div>
          <div class="wc-tags">
            <span class="tag tag-g">Containers</span>
            <span class="tag tag-g">CI/CD</span>
            <span class="tag tag-b">ADV</span>
          </div>
        </div>
        <div class="weapon-card">
          <div class="wc-cat">DATABASE</div>
          <div class="wc-name">SQL Server / PG</div>
          <div class="wc-tags">
            <span class="tag tag-g">MSSQL</span>
            <span class="tag tag-g">MySQL</span>
            <span class="tag tag-b">EXPERT</span>
          </div>
        </div>
      </div>
    </div>

    <!-- SKILL LEVELS -->
    <div>
      <div class="sec-label">OPERATOR STATS</div>
      <div style="background:#0d1a0d;border:1px solid #2d5a1b;padding:14px 16px;">
        <div class="stat-row"><div class="stat-name">C#</div><div class="stat-track"><div class="stat-fill sf-cs"></div></div><div class="stat-pct">95%</div></div>
        <div class="stat-row"><div class="stat-name">ASP.NET</div><div class="stat-track"><div class="stat-fill sf-net"></div></div><div class="stat-pct">90%</div></div>
        <div class="stat-row"><div class="stat-name">C++</div><div class="stat-track"><div class="stat-fill sf-cpp"></div></div><div class="stat-pct">70%</div></div>
        <div class="stat-row"><div class="stat-name">PHP / Laravel</div><div class="stat-track"><div class="stat-fill sf-php"></div></div><div class="stat-pct">65%</div></div>
        <div class="stat-row"><div class="stat-name">Docker</div><div class="stat-track"><div class="stat-fill sf-doc"></div></div><div class="stat-pct">82%</div></div>
        <div class="stat-row"><div class="stat-name">Linux</div><div class="stat-track"><div class="stat-fill sf-linux"></div></div><div class="stat-pct">80%</div></div>
        <div class="stat-row"><div class="stat-name">Git</div><div class="stat-track"><div class="stat-fill sf-git"></div></div><div class="stat-pct">95%</div></div>
        <div class="stat-row"><div class="stat-name">SQL Server</div><div class="stat-track"><div class="stat-fill sf-mssql"></div></div><div class="stat-pct">92%</div></div>
        <div class="stat-row"><div class="stat-name">PostgreSQL</div><div class="stat-track"><div class="stat-fill sf-pg"></div></div><div class="stat-pct">72%</div></div>
      </div>
    </div>

    <!-- INTEL STATS -->
    <div>
      <div class="sec-label">FIELD INTEL</div>
      <div class="intel-row">
        <div class="intel-card">
          <div class="ic-val">∞</div>
          <div class="ic-lbl">COMMITS</div>
        </div>
        <div class="intel-card">
          <div class="ic-val" id="streak-val">—</div>
          <div class="ic-lbl">DAY STREAK</div>
        </div>
        <div class="intel-card">
          <div class="ic-val">100%</div>
          <div class="ic-lbl">SECURE BUILDS</div>
        </div>
      </div>
    </div>

    <!-- COMMS -->
    <div>
      <div class="sec-label">ESTABLISH COMMS</div>
      <div class="comms-row">
        <a class="comm-btn" href="https://www.linkedin.com/in/abd-elarhman/" target="_blank" rel="noopener">
          <div class="comm-icon">
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none">
              <rect x="0" y="3" width="2" height="7" fill="#5aff3c"/>
              <rect x="0" y="0" width="2" height="2" fill="#5aff3c"/>
              <rect x="3" y="3" width="2" height="7" fill="#5aff3c"/>
              <rect x="3" y="3" width="7" height="2" fill="#5aff3c"/>
              <rect x="8" y="5" width="2" height="5" fill="#5aff3c"/>
            </svg>
          </div>
          LINKEDIN
        </a>
        <a class="comm-btn" href="https://github.com/Kurtbey1" target="_blank" rel="noopener">
          <div class="comm-icon">
            <svg width="10" height="10" viewBox="0 0 10 10" fill="none">
              <circle cx="5" cy="4" r="3" stroke="#5aff3c" stroke-width="1.5" fill="none"/>
              <rect x="3" y="6" width="4" height="4" fill="#5aff3c" rx="1"/>
            </svg>
          </div>
          GITHUB
        </a>
      </div>
    </div>

  </div>

  <!-- FOOTER -->
  <div class="ftr">
    <div class="ftr-left">&#x25A0; STAY SOLID. STAY SECURE. &#x25A0;</div>
    <div class="ftr-right">ABD ELRAHMAN ALQUDAH // KURTBEY1</div>
  </div>

</div>

<script>
  const s = document.getElementById('streak-val');
  let n = 0;
  const t = setInterval(() => {
    n += Math.floor(Math.random() * 7) + 3;
    if (s) s.textContent = n;
    if (n >= 47) { if (s) s.textContent = '47'; clearInterval(t); }
  }, 60);
</script>
