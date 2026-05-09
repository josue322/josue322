<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Josue Lopez – GitHub Profile Preview</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #21262d;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --accent3: #f78166;
    --accent4: #d2a8ff;
    --text: #e6edf3;
    --muted: #8b949e;
    --card: #1c2128;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Grid noise texture overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      repeating-linear-gradient(0deg, transparent, transparent 39px, rgba(33,38,45,0.4) 39px, rgba(33,38,45,0.4) 40px),
      repeating-linear-gradient(90deg, transparent, transparent 39px, rgba(33,38,45,0.4) 39px, rgba(33,38,45,0.4) 40px);
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 3rem 1.5rem 5rem;
  }

  /* ── HERO ── */
  .hero {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
    margin-bottom: 3rem;
    animation: fadeUp 0.7s ease both;
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.4rem, 6vw, 4rem);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.04em;
    background: linear-gradient(135deg, #e6edf3 0%, #58a6ff 60%, #d2a8ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-handle {
    font-size: 1rem;
    color: var(--accent);
    letter-spacing: 0.08em;
    opacity: 0.85;
  }

  /* Typing SVG replacement */
  .typing-banner {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 0.6rem 1.2rem;
    font-size: 0.82rem;
    color: var(--accent2);
    overflow: hidden;
    white-space: nowrap;
    width: fit-content;
    max-width: 100%;
  }

  .typing-banner span {
    display: inline-block;
    border-right: 2px solid var(--accent2);
    animation: blink 0.8s step-end infinite, typing 4s steps(60) 0.5s both;
    overflow: hidden;
    max-width: 0;
  }

  @keyframes typing { to { max-width: 600px; } }
  @keyframes blink { 50% { border-color: transparent; } }

  .quote {
    font-size: 0.78rem;
    color: var(--muted);
    font-style: italic;
    border-left: 3px solid var(--accent);
    padding-left: 0.8rem;
    margin-top: 0.2rem;
  }

  /* ── BADGES ── */
  .badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    margin-bottom: 2.5rem;
    animation: fadeUp 0.7s 0.1s ease both;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 20px;
    padding: 0.3rem 0.75rem;
    font-size: 0.72rem;
    color: var(--text);
    text-decoration: none;
    transition: border-color 0.2s, transform 0.2s;
  }

  .badge:hover {
    border-color: var(--accent);
    transform: translateY(-2px);
  }

  .badge .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── ASCII BLOCK ── */
  .ascii-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.5rem;
    margin-bottom: 2.5rem;
    overflow-x: auto;
    animation: fadeUp 0.7s 0.2s ease both;
  }

  .ascii-art {
    font-size: clamp(0.28rem, 1.1vw, 0.48rem);
    line-height: 1.2;
    color: var(--accent);
    white-space: pre;
    display: block;
    margin-bottom: 1rem;
  }

  .profile-card {
    font-size: 0.75rem;
    line-height: 1.9;
    color: var(--text);
  }

  .profile-card .key { color: var(--accent4); }
  .profile-card .val { color: var(--accent2); }
  .profile-card .str { color: var(--accent3); }
  .profile-card .arr { color: var(--muted); }

  /* ── SECTION TITLE ── */
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.8rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── TECH TABLE ── */
  .tech-section {
    margin-bottom: 2.5rem;
    animation: fadeUp 0.7s 0.3s ease both;
  }

  .tech-grid {
    display: grid;
    gap: 0.8rem;
  }

  .tech-row {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 0.8rem 1rem;
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.6rem;
  }

  .tech-label {
    font-size: 0.7rem;
    color: var(--muted);
    min-width: 90px;
    flex-shrink: 0;
  }

  .tech-badges {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }

  .pill {
    display: inline-flex;
    align-items: center;
    gap: 0.3rem;
    padding: 0.25rem 0.65rem;
    border-radius: 6px;
    font-size: 0.68rem;
    font-weight: 600;
    letter-spacing: 0.02em;
  }

  /* ── STATS ── */
  .stats-section {
    margin-bottom: 2.5rem;
    animation: fadeUp 0.7s 0.4s ease both;
  }

  .stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1rem;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.2rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.2s;
  }

  .stat-card:hover { border-color: var(--accent); }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent4));
  }

  .stat-img {
    width: 100%;
    border-radius: 6px;
    display: block;
  }

  /* ── PINNED REPOS ── */
  .repos-section {
    margin-bottom: 2.5rem;
    animation: fadeUp 0.7s 0.5s ease both;
  }

  .repos-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1rem;
  }

  .repo-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1rem 1.2rem;
    text-decoration: none;
    color: var(--text);
    transition: border-color 0.2s, transform 0.2s;
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }

  .repo-card:hover {
    border-color: var(--accent);
    transform: translateY(-3px);
  }

  .repo-name {
    font-family: 'Syne', sans-serif;
    font-size: 0.9rem;
    font-weight: 700;
    color: var(--accent);
  }

  .repo-desc {
    font-size: 0.7rem;
    color: var(--muted);
    line-height: 1.5;
  }

  .repo-lang {
    display: flex;
    align-items: center;
    gap: 0.35rem;
    font-size: 0.68rem;
    color: var(--muted);
    margin-top: auto;
  }

  .lang-dot {
    width: 10px; height: 10px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  /* ── ACTIVITY GRAPH ── */
  .activity-section {
    margin-bottom: 2.5rem;
    animation: fadeUp 0.7s 0.6s ease both;
  }

  .activity-embed {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
  }

  .activity-embed img {
    width: 100%;
    display: block;
  }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    font-size: 0.65rem;
    color: var(--muted);
    margin-top: 3rem;
    animation: fadeUp 0.7s 0.7s ease both;
  }

  .footer a { color: var(--accent); text-decoration: none; }

  /* ── DIVIDER ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border), transparent);
    margin: 2rem 0;
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; height: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }
</style>
</head>
<body>
<div class="wrapper">

  <!-- ── HERO ── -->
  <header class="hero">
    <div class="hero-name">Josue Lopez</div>
    <div class="hero-handle">@josue322</div>
    <div class="typing-banner">
      <span>👋 ¡Hola! Soy desarrollador apasionado por construir soluciones reales · Open Source · Always Learning</span>
    </div>
    <p class="quote">"Si no puedes explicarlo de forma sencilla, es que no lo entiendes lo suficientemente bien." – Albert Einstein</p>
  </header>

  <!-- ── BADGES / REDES ── -->
  <div class="badges">
    <a class="badge" href="https://github.com/josue322" target="_blank">
      <span class="dot" style="background:#58a6ff"></span>GitHub
    </a>
    <a class="badge" href="https://github.com/josue322?tab=followers" target="_blank">
      <span class="dot" style="background:#3fb950"></span>Followers
    </a>
    <a class="badge" href="mailto:tuemail@gmail.com">
      <span class="dot" style="background:#f78166"></span>Gmail
    </a>
    <a class="badge" href="https://www.linkedin.com/in/josue322" target="_blank">
      <span class="dot" style="background:#0a66c2"></span>LinkedIn
    </a>
    <a class="badge" href="https://twitter.com/josue322" target="_blank">
      <span class="dot" style="background:#1d9bf0"></span>Twitter
    </a>
    <!-- Estadísticas dinámicas via shields.io -->
    <img src="https://img.shields.io/github/followers/josue322?label=Followers&style=flat-square&color=58a6ff&labelColor=161b22" alt="followers" style="height:28px;border-radius:20px;">
    <img src="https://img.shields.io/github/stars/josue322?label=Stars&style=flat-square&color=3fb950&labelColor=161b22" alt="stars" style="height:28px;border-radius:20px;">
  </div>

  <!-- ── ASCII + PROFILE DATA ── -->
  <div class="ascii-block">
    <code class="ascii-art">
     ██╗ ██████╗ ███████╗██╗   ██╗███████╗    ██╗      ██████╗ ██████╗ ███████╗███████╗
     ██║██╔═══██╗██╔════╝██║   ██║██╔════╝    ██║     ██╔═══██╗██╔══██╗██╔════╝╚════██║
     ██║██║   ██║███████╗██║   ██║█████╗      ██║     ██║   ██║██████╔╝█████╗      ██╔╝
██   ██║██║   ██║╚════██║██║   ██║██╔══╝      ██║     ██║   ██║██╔═══╝ ██╔══╝     ██╔╝ 
╚█████╔╝╚██████╔╝███████║╚██████╔╝███████╗    ███████╗╚██████╔╝██║     ███████╗   ██║  
 ╚════╝  ╚═════╝ ╚══════╝ ╚═════╝ ╚══════╝    ╚══════╝ ╚═════╝ ╚═╝     ╚══════╝   ╚═╝  
    </code>

    <div class="profile-card">
<span class="key">name</span>: <span class="str">"Josue Lopez"</span><br>
<span class="key">username</span>: <span class="str">"@josue322"</span><br>
<span class="key">github</span>: <span class="str">"https://github.com/josue322"</span><br>
<span class="key">currently_learning</span>: <span class="arr">["JavaScript", "Python", "React", "Node.js"]</span><br>
<span class="key">interests</span>: <span class="arr">["desarrollo web", "open source", "automatización", "bases de datos"]</span><br>
<span class="key">soft_skills</span>: <span class="arr">["atención al detalle", "trabajo en equipo", "autodidacta", "resolución de problemas"]</span><br>
<span class="key">2025_goals</span>: <span class="arr">["contribuir a proyectos OSS", "construir portfolio sólido", "conseguir rol como dev"]</span><br>
<span class="key">fun_fact</span>: <span class="str">"Siempre hay algo nuevo por aprender 🚀"</span>
    </div>
  </div>

  <!-- ── TECH STACK ── -->
  <section class="tech-section">
    <div class="section-title">🧰 Stack & Herramientas</div>
    <div class="tech-grid">

      <div class="tech-row">
        <span class="tech-label">💻 Lenguajes</span>
        <div class="tech-badges">
          <span class="pill" style="background:#1c3a1c;color:#3fb950;">JavaScript</span>
          <span class="pill" style="background:#1c2e3a;color:#58a6ff;">Python</span>
          <span class="pill" style="background:#3a1c1c;color:#f78166;">HTML5</span>
          <span class="pill" style="background:#2a1c3a;color:#d2a8ff;">CSS3</span>
          <span class="pill" style="background:#1c1c2e;color:#79c0ff;">SQL</span>
        </div>
      </div>

      <div class="tech-row">
        <span class="tech-label">⚙️ Frameworks</span>
        <div class="tech-badges">
          <span class="pill" style="background:#1c2e3a;color:#61dafb;">React</span>
          <span class="pill" style="background:#1c3a1c;color:#68a063;">Node.js</span>
          <span class="pill" style="background:#1c1c2e;color:#d2a8ff;">Express</span>
          <span class="pill" style="background:#2e2a1c;color:#f0db4f;">Vue</span>
        </div>
      </div>

      <div class="tech-row">
        <span class="tech-label">🛠️ Herramientas</span>
        <div class="tech-badges">
          <span class="pill" style="background:#2e1c1c;color:#f05032;">Git</span>
          <span class="pill" style="background:#1c1c1c;color:#e6edf3;">GitHub</span>
          <span class="pill" style="background:#1c2e3a;color:#007acc;">VS Code</span>
          <span class="pill" style="background:#1c3a1c;color:#3fb950;">MySQL</span>
          <span class="pill" style="background:#1c2e2e;color:#47a248;">MongoDB</span>
        </div>
      </div>

      <div class="tech-row">
        <span class="tech-label">📀 SO</span>
        <div class="tech-badges">
          <span class="pill" style="background:#1c1c2e;color:#0078d6;">Windows</span>
          <span class="pill" style="background:#2e1c1c;color:#f78166;">Linux</span>
        </div>
      </div>

    </div>
  </section>

  <div class="divider"></div>

  <!-- ── GITHUB STATS ── -->
  <section class="stats-section">
    <div class="section-title">📊 GitHub Stats</div>
    <div class="stats-grid">
      <div class="stat-card">
        <img
          class="stat-img"
          src="https://github-readme-stats.vercel.app/api?username=josue322&show_icons=true&theme=github_dark&hide_border=true&include_all_commits=true&count_private=true&bg_color=1c2128&title_color=58a6ff&icon_color=3fb950&text_color=e6edf3"
          alt="Josue Lopez GitHub Stats"
        >
      </div>
      <div class="stat-card">
        <img
          class="stat-img"
          src="https://github-readme-stats.vercel.app/api/top-langs/?username=josue322&layout=compact&theme=github_dark&hide_border=true&bg_color=1c2128&title_color=58a6ff&text_color=e6edf3"
          alt="Top Languages"
        >
      </div>
      <div class="stat-card" style="grid-column: 1 / -1;">
        <img
          class="stat-img"
          src="https://github-readme-streak-stats.herokuapp.com/?user=josue322&theme=github-dark-blue&hide_border=true&background=1c2128&stroke=21262d&ring=58a6ff&fire=f78166&currStreakLabel=58a6ff"
          alt="GitHub Streak"
        >
      </div>
    </div>
  </section>

  <!-- ── REPOS DESTACADOS ── -->
  <section class="repos-section">
    <div class="section-title">📌 Repositorios Destacados</div>
    <div class="repos-grid">
      <a class="repo-card" href="https://github.com/josue322" target="_blank">
        <span class="repo-name">📁 josue322</span>
        <span class="repo-desc">Mi perfil de GitHub — README personalizado con estadísticas y stack.</span>
        <span class="repo-lang"><span class="lang-dot" style="background:#f0db4f"></span>Markdown</span>
      </a>
      <a class="repo-card" href="https://github.com/josue322?tab=repositories" target="_blank">
        <span class="repo-name">🌐 Mis Proyectos</span>
        <span class="repo-desc">Colección de proyectos de desarrollo web, scripts y experimentos.</span>
        <span class="repo-lang"><span class="lang-dot" style="background:#f7df1e"></span>JavaScript</span>
      </a>
      <a class="repo-card" href="https://github.com/josue322?tab=repositories" target="_blank">
        <span class="repo-name">🐍 Scripts Python</span>
        <span class="repo-desc">Automatizaciones, herramientas CLI y scripts de utilidad en Python.</span>
        <span class="repo-lang"><span class="lang-dot" style="background:#3572A5"></span>Python</span>
      </a>
      <a class="repo-card" href="https://github.com/josue322?tab=repositories" target="_blank">
        <span class="repo-name">⚛️ React Apps</span>
        <span class="repo-desc">Aplicaciones frontend construidas con React y tecnologías modernas.</span>
        <span class="repo-lang"><span class="lang-dot" style="background:#61dafb"></span>React</span>
      </a>
    </div>
    <p style="font-size:0.65rem;color:var(--muted);margin-top:0.7rem;">
      * Actualiza los nombres/links de repos con tus proyectos reales en tu README.md
    </p>
  </section>

  <!-- ── ACTIVITY GRAPH ── -->
  <section class="activity-section">
    <div class="section-title">📈 Actividad</div>
    <div class="activity-embed">
      <img
        src="https://github-readme-activity-graph.vercel.app/graph?username=josue322&theme=react-dark&hide_border=true&bg_color=1c2128&color=58a6ff&line=3fb950&point=f78166"
        alt="GitHub Activity Graph"
      >
    </div>
  </section>

  <div class="divider"></div>

  <!-- ── TROFEOS ── -->
  <section style="margin-bottom:2.5rem; animation: fadeUp 0.7s 0.65s ease both;">
    <div class="section-title">🏆 Trofeos</div>
    <div style="background:var(--card);border:1px solid var(--border);border-radius:10px;overflow:hidden;">
      <img
        style="width:100%;display:block;"
        src="https://github-profile-trophy.vercel.app/?username=josue322&theme=algolia&no-frame=true&no-bg=true&margin-w=8&row=1"
        alt="GitHub Trophies"
      >
    </div>
  </section>

  <!-- ── FOOTER ── -->
  <footer class="footer">
    <p>Hecho con ❤️ por <a href="https://github.com/josue322">@josue322</a> · Josue Lopez</p>
    <p style="margin-top:0.3rem;">
      Inspirado en el template de
      <a href="https://github.com/durgeshsamariya/awesome-github-profile-readme-templates" target="_blank">awesome-github-profile-readme-templates</a>
    </p>
    <p style="margin-top:0.5rem;color:#3b4048;">
      ── Para usar en GitHub: convierte este HTML a Markdown con las URLs de imágenes de shields.io y github-readme-stats ──
    </p>
  </footer>

</div>
</body>
</html>
