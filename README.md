
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Rajdhani:wght@300;400;600;700&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body { background: #000; overflow-x: hidden; }

  #github-profile {
    font-family: 'Space Mono', monospace;
    background: #000510;
    min-height: 100vh;
    color: #e0e0ff;
    position: relative;
    overflow: hidden;
    padding: 0;
  }

  #starfield {
    position: absolute; inset: 0; z-index: 0; pointer-events: none;
  }

  .hero {
    position: relative;
    z-index: 2;
    padding: 40px 24px 20px;
    text-align: center;
  }

  .glitch-name {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(28px, 6vw, 52px);
    font-weight: 900;
    color: #fff;
    letter-spacing: 4px;
    position: relative;
    display: inline-block;
    animation: flicker 6s infinite;
    text-shadow:
      0 0 8px #00f7ff,
      0 0 20px #00f7ff44,
      0 0 40px #00f7ff22;
  }

  .glitch-name::before,
  .glitch-name::after {
    content: attr(data-text);
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
  }

  .glitch-name::before {
    color: #ff006680;
    animation: glitch1 3s infinite;
    clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
  }

  .glitch-name::after {
    color: #00f7ff80;
    animation: glitch2 3s infinite;
    clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
  }

  @keyframes glitch1 {
    0%, 90%, 100% { transform: translate(0); }
    92% { transform: translate(-3px, 1px); }
    94% { transform: translate(3px, -1px); }
    96% { transform: translate(-2px, 2px); }
  }

  @keyframes glitch2 {
    0%, 90%, 100% { transform: translate(0); }
    91% { transform: translate(3px, -1px); }
    93% { transform: translate(-3px, 1px); }
    95% { transform: translate(2px, -2px); }
  }

  @keyframes flicker {
    0%, 95%, 100% { opacity: 1; }
    96% { opacity: 0.8; }
    97% { opacity: 1; }
    98% { opacity: 0.6; }
    99% { opacity: 1; }
  }

  .hero-subtitle {
    font-family: 'Rajdhani', sans-serif;
    font-size: 14px;
    font-weight: 300;
    letter-spacing: 6px;
    color: #00f7ffaa;
    text-transform: uppercase;
    margin-top: 8px;
    animation: fadeInUp 1s ease 0.3s both;
  }

  .orb-container {
    margin: 20px auto;
    width: 120px; height: 120px;
    position: relative;
    animation: fadeInUp 1s ease 0.5s both;
  }

  .orb {
    width: 120px; height: 120px;
    border-radius: 50%;
    background: radial-gradient(circle at 35% 35%, #00f7ff, #7b00ff, #ff0066, #000510);
    animation: orbPulse 4s ease-in-out infinite, orbRotate 8s linear infinite;
    box-shadow:
      0 0 30px #00f7ff55,
      0 0 60px #7b00ff44,
      inset 0 0 30px #7b00ff33;
    position: relative;
    z-index: 1;
  }

  .orb-ring {
    position: absolute;
    top: -12px; left: -12px;
    width: 144px; height: 144px;
    border-radius: 50%;
    border: 1px solid #00f7ff33;
    animation: ringPulse 3s ease-in-out infinite;
  }

  .orb-ring2 {
    position: absolute;
    top: -24px; left: -24px;
    width: 168px; height: 168px;
    border-radius: 50%;
    border: 1px solid #7b00ff22;
    animation: ringPulse 3s ease-in-out infinite 1s;
  }

  @keyframes orbPulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
  }

  @keyframes orbRotate {
    from { filter: hue-rotate(0deg); }
    to { filter: hue-rotate(360deg); }
  }

  @keyframes ringPulse {
    0%, 100% { transform: scale(1); opacity: 0.5; }
    50% { transform: scale(1.1); opacity: 1; }
  }

  .terminal-badges {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 8px;
    margin: 16px auto;
    max-width: 560px;
    animation: fadeInUp 1s ease 0.7s both;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 5px 14px;
    border-radius: 2px;
    border: 1px solid;
    position: relative;
    overflow: hidden;
    cursor: default;
    transition: all 0.2s;
    letter-spacing: 1px;
  }

  .badge::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.06), transparent);
    transform: translateX(-100%);
    transition: transform 0.4s;
  }

  .badge:hover::before { transform: translateX(100%); }
  .badge:hover { transform: translateY(-2px); }

  .b-cyan { color: #00f7ff; border-color: #00f7ff44; background: #00f7ff0d; }
  .b-purple { color: #bf80ff; border-color: #7b00ff44; background: #7b00ff0d; }
  .b-pink { color: #ff6eb4; border-color: #ff006644; background: #ff00660d; }
  .b-green { color: #00ff88; border-color: #00ff4444; background: #00ff440d; }
  .b-amber { color: #ffb347; border-color: #ff880044; background: #ff88000d; }

  .section {
    position: relative;
    z-index: 2;
    margin: 0 16px 20px;
    animation: fadeInUp 0.8s ease both;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 14px;
    padding-bottom: 8px;
    border-bottom: 1px solid #ffffff10;
  }

  .section-icon {
    font-size: 16px;
    color: #00f7ff;
  }

  .section-title {
    font-family: 'Orbitron', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 4px;
    color: #00f7ffcc;
    text-transform: uppercase;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, #00f7ff22, transparent);
  }

  .terminal-block {
    background: #000c1a;
    border: 1px solid #00f7ff22;
    border-radius: 6px;
    padding: 16px;
    position: relative;
    overflow: hidden;
  }

  .terminal-block::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, #00f7ff66, transparent);
  }

  .terminal-dots {
    display: flex; gap: 6px; margin-bottom: 12px;
  }

  .dot { width: 10px; height: 10px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #febc2e; }
  .dot-g { background: #28c840; }

  .terminal-line {
    font-size: 12px;
    line-height: 2;
    color: #a0c0d0;
  }

  .t-prompt { color: #00ff8866; }
  .t-cmd { color: #00f7ff; }
  .t-val { color: #bf80ff; }
  .t-str { color: #ffb347; }
  .t-comment { color: #404868; }
  .t-ok { color: #00ff88; }

  .cursor-blink {
    display: inline-block;
    width: 8px; height: 14px;
    background: #00f7ff;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
    margin-left: 2px;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(90px, 1fr));
    gap: 8px;
  }

  .skill-chip {
    background: #0a0a1a;
    border: 1px solid #ffffff15;
    border-radius: 4px;
    padding: 8px 6px;
    text-align: center;
    font-size: 10px;
    color: #c0c8e8;
    letter-spacing: 0.5px;
    transition: all 0.25s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .skill-chip:hover {
    border-color: var(--chip-color);
    color: var(--chip-color);
    background: #0a0a2a;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px var(--chip-glow);
  }

  .skill-chip .chip-icon {
    display: block;
    font-size: 18px;
    margin-bottom: 4px;
    filter: grayscale(0.4);
    transition: filter 0.25s;
  }

  .skill-chip:hover .chip-icon { filter: grayscale(0); }

  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
    margin-bottom: 12px;
  }

  .stat-box {
    background: #000c1a;
    border: 1px solid #ffffff12;
    border-radius: 6px;
    padding: 12px 8px;
    text-align: center;
    position: relative;
    overflow: hidden;
    transition: all 0.2s;
  }

  .stat-box:hover {
    border-color: #00f7ff33;
    transform: translateY(-2px);
  }

  .stat-box::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--bar-color);
    transform: scaleX(0);
    transition: transform 0.4s ease;
  }

  .stat-box:hover::after { transform: scaleX(1); }

  .stat-num {
    font-family: 'Orbitron', sans-serif;
    font-size: 20px;
    font-weight: 700;
    color: #fff;
    text-shadow: 0 0 8px var(--bar-color);
  }

  .stat-label {
    font-size: 9px;
    letter-spacing: 2px;
    color: #404868;
    margin-top: 3px;
    text-transform: uppercase;
  }

  .projects-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }

  .project-card {
    background: #000c1a;
    border: 1px solid #ffffff12;
    border-radius: 6px;
    padding: 14px;
    transition: all 0.3s;
    cursor: pointer;
    position: relative;
    overflow: hidden;
  }

  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: var(--proj-color);
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .project-card:hover::before { transform: scaleX(1); }
  .project-card:hover {
    border-color: var(--proj-border);
    transform: translateY(-3px);
    box-shadow: 0 8px 24px var(--proj-shadow);
  }

  .proj-title {
    font-family: 'Orbitron', sans-serif;
    font-size: 10px;
    font-weight: 700;
    color: #e0e8ff;
    letter-spacing: 1px;
    margin-bottom: 6px;
  }

  .proj-desc {
    font-size: 10px;
    color: #5a6480;
    line-height: 1.6;
    margin-bottom: 8px;
  }

  .proj-tags {
    display: flex; gap: 4px; flex-wrap: wrap;
  }

  .proj-tag {
    font-size: 8px;
    padding: 2px 7px;
    border-radius: 2px;
    border: 1px solid;
    letter-spacing: 0.5px;
  }

  .connect-row {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    justify-content: center;
  }

  .connect-btn {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    padding: 8px 16px;
    border-radius: 3px;
    border: 1px solid;
    background: transparent;
    cursor: pointer;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    display: inline-block;
  }

  .connect-btn::before {
    content: '';
    position: absolute;
    inset: 0;
    background: currentColor;
    opacity: 0;
    transition: opacity 0.2s;
  }

  .connect-btn:hover::before { opacity: 0.1; }
  .connect-btn:hover { transform: translateY(-2px); }

  .btn-cyan { color: #00f7ff; border-color: #00f7ff66; }
  .btn-purple { color: #bf80ff; border-color: #7b00ff66; }
  .btn-pink { color: #ff6eb4; border-color: #ff006666; }
  .btn-green { color: #00ff88; border-color: #00ff4466; }

  .scan-line {
    position: absolute;
    width: 100%;
    height: 1px;
    background: linear-gradient(90deg, transparent, #00f7ff15, #00f7ff30, #00f7ff15, transparent);
    animation: scan 8s linear infinite;
    pointer-events: none;
    z-index: 1;
  }

  @keyframes scan {
    0% { top: -2px; }
    100% { top: 100%; }
  }

  .glass-divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, #00f7ff22, #7b00ff22, transparent);
    margin: 8px 0 16px;
  }

  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .quote-block {
    border-left: 2px solid #00f7ff44;
    padding: 10px 14px;
    background: #00f7ff06;
    border-radius: 0 4px 4px 0;
    font-size: 11px;
    font-style: italic;
    color: #6080a0;
    line-height: 1.8;
  }

  .footer-ascii {
    text-align: center;
    font-size: 9px;
    color: #1a2040;
    letter-spacing: 2px;
    padding: 16px 0 8px;
    font-family: 'Space Mono', monospace;
  }

  .neon-separator {
    display: flex;
    align-items: center;
    gap: 8px;
    margin: 6px 0 14px;
  }

  .nsep-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, transparent, #ffffff15);
  }

  .nsep-diamond {
    width: 6px; height: 6px;
    background: #00f7ff;
    transform: rotate(45deg);
    box-shadow: 0 0 6px #00f7ff;
  }

  .nsep-line-r {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, #ffffff15, transparent);
  }

  .activity-bar {
    display: flex;
    align-items: flex-end;
    gap: 3px;
    height: 48px;
    padding: 0 4px;
  }

  .bar-col {
    flex: 1;
    background: #00f7ff;
    border-radius: 2px 2px 0 0;
    opacity: 0.6;
    transition: opacity 0.2s;
    min-width: 4px;
    animation: barGrow 1s ease both;
  }

  .bar-col:hover { opacity: 1; }

  @keyframes barGrow {
    from { transform: scaleY(0); transform-origin: bottom; }
    to { transform: scaleY(1); transform-origin: bottom; }
  }
</style>

<div id="github-profile">
  <canvas id="starfield"></canvas>
  <div class="scan-line"></div>

  <div class="hero">
    <div class="glitch-name" data-text="YOUR NAME HERE">YOUR NAME HERE</div>
    <div class="hero-subtitle">CS Student &nbsp;·&nbsp; COEP Technological University &nbsp;·&nbsp; Pune</div>

    <div class="orb-container">
      <div class="orb-ring2"></div>
      <div class="orb-ring"></div>
      <div class="orb"></div>
    </div>

    <div class="terminal-badges">
      <span class="badge b-cyan">⬡ Full Stack Dev</span>
      <span class="badge b-purple">⬢ ML / AI Enthusiast</span>
      <span class="badge b-pink">◈ Open Source</span>
      <span class="badge b-green">▸ Problem Solver</span>
      <span class="badge b-amber">⬟ COEP 2025</span>
    </div>
  </div>

  <div class="glass-divider"></div>

  <!-- ABOUT -->
  <div class="section" style="animation-delay:0.2s">
    <div class="section-header">
      <span class="section-icon">◉</span>
      <span class="section-title">Profile.json</span>
      <div class="section-line"></div>
    </div>

    <div class="terminal-block">
      <div class="terminal-dots">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
      </div>
      <div class="terminal-line"><span class="t-prompt">~/profile $ </span><span class="t-cmd">cat</span> <span class="t-str">about.json</span></div>
      <div class="terminal-line" style="margin-top:8px"><span class="t-comment">{</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"name"</span><span class="t-comment">:</span> <span class="t-str">"Your Name"</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"university"</span><span class="t-comment">:</span> <span class="t-str">"COEP Technological University"</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"degree"</span><span class="t-comment">:</span> <span class="t-str">"B.Tech Computer Science"</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"role"</span><span class="t-comment">:</span> <span class="t-str">"Student Developer &amp; Builder"</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"currently_learning"</span><span class="t-comment">:</span> <span class="t-str">["DSA", "System Design", "ML"]</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"interests"</span><span class="t-comment">:</span> <span class="t-str">["Open Source", "Competitive Programming", "Building Cool Stuff"]</span><span class="t-comment">,</span></div>
      <div class="terminal-line">&nbsp;&nbsp;<span class="t-val">"status"</span><span class="t-comment">:</span> <span class="t-ok">✓ "Available for Opportunities"</span></div>
      <div class="terminal-line"><span class="t-comment">}</span> <span class="cursor-blink"></span></div>
    </div>
  </div>

  <!-- STATS -->
  <div class="section" style="animation-delay:0.35s">
    <div class="section-header">
      <span class="section-icon">◈</span>
      <span class="section-title">Stats.sys</span>
      <div class="section-line"></div>
    </div>

    <div class="stats-row">
      <div class="stat-box" style="--bar-color:#00f7ff">
        <div class="stat-num" style="--bar-color:#00f7ff">42+</div>
        <div class="stat-label">Repos</div>
      </div>
      <div class="stat-box" style="--bar-color:#7b00ff">
        <div class="stat-num" style="--bar-color:#7b00ff">500+</div>
        <div class="stat-label">Commits</div>
      </div>
      <div class="stat-box" style="--bar-color:#ff0066">
        <div class="stat-num" style="--bar-color:#ff0066">∞</div>
        <div class="stat-label">Curiosity</div>
      </div>
    </div>

    <div class="terminal-block" style="padding:12px 14px">
      <div style="font-size:10px; color:#304060; letter-spacing:2px; margin-bottom:8px; text-transform:uppercase">Contribution Activity</div>
      <div class="activity-bar" id="activity-bars"></div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section" style="animation-delay:0.5s">
    <div class="section-header">
      <span class="section-icon">◎</span>
      <span class="section-title">Skills.exe</span>
      <div class="section-line"></div>
    </div>

    <div class="skills-grid">
      <div class="skill-chip" style="--chip-color:#61DAFB;--chip-glow:#61DAFB22"><span class="chip-icon">⚛</span>React</div>
      <div class="skill-chip" style="--chip-color:#3776AB;--chip-glow:#3776AB22"><span class="chip-icon">🐍</span>Python</div>
      <div class="skill-chip" style="--chip-color:#f7df1e;--chip-glow:#f7df1e22"><span class="chip-icon">JS</span>JavaScript</div>
      <div class="skill-chip" style="--chip-color:#00ADD8;--chip-glow:#00ADD822"><span class="chip-icon">Go</span>Golang</div>
      <div class="skill-chip" style="--chip-color:#FF6B35;--chip-glow:#FF6B3522"><span class="chip-icon">☁</span>Node.js</div>
      <div class="skill-chip" style="--chip-color:#4DB33D;--chip-glow:#4DB33D22"><span class="chip-icon">🍃</span>MongoDB</div>
      <div class="skill-chip" style="--chip-color:#F05032;--chip-glow:#F0503222"><span class="chip-icon">⑂</span>Git</div>
      <div class="skill-chip" style="--chip-color:#2496ED;--chip-glow:#2496ED22"><span class="chip-icon">🐳</span>Docker</div>
      <div class="skill-chip" style="--chip-color:#bf80ff;--chip-glow:#bf80ff22"><span class="chip-icon">🧠</span>ML</div>
      <div class="skill-chip" style="--chip-color:#00ff88;--chip-glow:#00ff8822"><span class="chip-icon">C++</span>C / C++</div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section" style="animation-delay:0.65s">
    <div class="section-header">
      <span class="section-icon">⬡</span>
      <span class="section-title">Projects.log</span>
      <div class="section-line"></div>
    </div>

    <div class="projects-grid">
      <div class="project-card" style="--proj-color:linear-gradient(90deg,#00f7ff,transparent);--proj-border:#00f7ff33;--proj-shadow:#00f7ff11">
        <div class="proj-title">◈ PROJECT ONE</div>
        <div class="proj-desc">Replace with your best project description. Keep it punchy.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:#00f7ff;border-color:#00f7ff44">React</span>
          <span class="proj-tag" style="color:#bf80ff;border-color:#7b00ff44">Node</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:linear-gradient(90deg,#bf80ff,transparent);--proj-border:#7b00ff33;--proj-shadow:#7b00ff11">
        <div class="proj-title">◈ PROJECT TWO</div>
        <div class="proj-desc">Another amazing project. Show what you've built with passion.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:#ffb347;border-color:#ff880044">Python</span>
          <span class="proj-tag" style="color:#00ff88;border-color:#00ff4444">ML</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:linear-gradient(90deg,#ff6eb4,transparent);--proj-border:#ff006633;--proj-shadow:#ff006611">
        <div class="proj-title">◈ PROJECT THREE</div>
        <div class="proj-desc">Open source contribution or personal tool you're proud of.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:#ff6eb4;border-color:#ff006644">C++</span>
          <span class="proj-tag" style="color:#00f7ff;border-color:#00f7ff44">DSA</span>
        </div>
      </div>
      <div class="project-card" style="--proj-color:linear-gradient(90deg,#00ff88,transparent);--proj-border:#00ff4433;--proj-shadow:#00ff4411">
        <div class="proj-title">◈ PROJECT FOUR</div>
        <div class="proj-desc">A hackathon project, research work, or campus initiative.</div>
        <div class="proj-tags">
          <span class="proj-tag" style="color:#00ff88;border-color:#00ff4444">Go</span>
          <span class="proj-tag" style="color:#bf80ff;border-color:#7b00ff44">Docker</span>
        </div>
      </div>
    </div>
  </div>

  <!-- QUOTE -->
  <div class="section" style="animation-delay:0.8s">
    <div class="neon-separator">
      <div class="nsep-line"></div>
      <div class="nsep-diamond"></div>
      <div class="nsep-line-r"></div>
    </div>
    <div class="quote-block">
      "First, solve the problem. Then, write the code."<br>
      <span style="color:#1e3050;font-size:9px;font-style:normal;letter-spacing:2px">— JOHN JOHNSON</span>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section" style="animation-delay:0.95s">
    <div class="section-header">
      <span class="section-icon">◉</span>
      <span class="section-title">Connect.net</span>
      <div class="section-line"></div>
    </div>

    <div class="connect-row">
      <a class="connect-btn btn-cyan" href="#">⬡ LinkedIn</a>
      <a class="connect-btn btn-purple" href="#">⬢ Portfolio</a>
      <a class="connect-btn btn-pink" href="#">◈ Twitter</a>
      <a class="connect-btn btn-green" href="#">▸ Email</a>
    </div>
  </div>

  <div class="footer-ascii">
    ─────────────────────────────────────────────────────────────────<br>
    MADE WITH ❤ &nbsp;|&nbsp; COEP TECHNOLOGICAL UNIVERSITY &nbsp;|&nbsp; PUNE, INDIA
  </div>
</div>

<script>
const canvas = document.getElementById('starfield');
const ctx = canvas.getContext('2d');
let stars = [];
let W, H;

function resize() {
  W = canvas.width = canvas.offsetWidth || 640;
  H = canvas.height = document.getElementById('github-profile').scrollHeight || 1200;
}

function initStars() {
  stars = [];
  const count = Math.floor((W * H) / 4000);
  for (let i = 0; i < count; i++) {
    stars.push({
      x: Math.random() * W,
      y: Math.random() * H,
      r: Math.random() * 1.2,
      o: Math.random() * 0.6 + 0.1,
      speed: Math.random() * 0.2 + 0.05,
      phase: Math.random() * Math.PI * 2,
      color: ['#ffffff','#00f7ff','#bf80ff','#ff6eb4'][Math.floor(Math.random()*4)]
    });
  }
}

let t = 0;
function draw() {
  ctx.clearRect(0, 0, W, H);
  t += 0.01;
  stars.forEach(s => {
    const tw = s.o * (0.6 + 0.4 * Math.sin(t * s.speed + s.phase));
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fillStyle = s.color;
    ctx.globalAlpha = tw;
    ctx.fill();
    ctx.globalAlpha = 1;
  });
  requestAnimationFrame(draw);
}

resize();
initStars();
draw();

// Activity bars
const abars = document.getElementById('activity-bars');
const bdata = [28,45,32,60,75,42,90,55,38,80,65,70,88,50,40,95,62,44,73,85,58,30,68,77,35,82,48,91,53,66,72,87,45,63,78,55,41,89,60,74,49,83,57,38,92,66,71,48,84,61,44,79,56,39,94,69,75,52,88,42,67,80,58,33,96,71,78,54,91,47,74,83,62,45,98,76,81,59,44,97,69,88,63,40,95,74,82,60,47,100];

bdata.slice(0, 52).forEach((h, i) => {
  const bar = document.createElement('div');
  bar.className = 'bar-col';
  bar.style.height = (h * 0.44) + 'px';
  bar.style.animationDelay = (i * 0.015) + 's';
  const hue = h > 70 ? '#00f7ff' : h > 40 ? '#7b00ff' : '#1a2040';
  bar.style.background = hue;
  abars.appendChild(bar);
});
</script>
