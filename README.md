<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Vishal Sanam — Backend Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0c0c0e;
    --surface: #141416;
    --surface2: #1c1c20;
    --border: rgba(255,255,255,0.07);
    --text: #e8e8ec;
    --muted: #6b6b78;
    --accent: #00d9ff;
    --accent2: #7c6aff;
    --green: #22c55e;
    --font-display: 'DM Serif Display', Georgia, serif;
    --font-mono: 'DM Mono', monospace;
    --font-body: 'DM Sans', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-body);
    font-size: 15px;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  a { color: inherit; text-decoration: none; }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 20px 40px;
    background: rgba(12,12,14,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
  }
  .nav-logo {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--accent);
    letter-spacing: 0.05em;
  }
  .nav-links {
    display: flex; gap: 32px; list-style: none;
  }
  .nav-links a {
    font-size: 13px;
    font-weight: 500;
    color: var(--muted);
    letter-spacing: 0.03em;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--text); }
  .nav-cta {
    font-family: var(--font-mono);
    font-size: 12px;
    padding: 8px 18px;
    border: 1px solid var(--accent);
    color: var(--accent);
    border-radius: 4px;
    transition: background 0.2s, color 0.2s;
    letter-spacing: 0.04em;
  }
  .nav-cta:hover { background: var(--accent); color: var(--bg); }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 40px 80px;
    max-width: 1100px;
    margin: 0 auto;
    position: relative;
  }
  .hero-inner { max-width: 680px; }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--green);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 28px;
  }
  .badge-dot {
    width: 6px; height: 6px; border-radius: 50%;
    background: var(--green);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }
  .hero h1 {
    font-family: var(--font-display);
    font-size: clamp(48px, 7vw, 82px);
    line-height: 1.05;
    letter-spacing: -0.01em;
    margin-bottom: 24px;
    color: #fff;
  }
  .hero h1 em {
    font-style: italic;
    color: var(--accent);
  }
  .hero-sub {
    font-size: 16px;
    color: var(--muted);
    line-height: 1.7;
    max-width: 520px;
    margin-bottom: 40px;
  }
  .hero-actions {
    display: flex; gap: 14px; flex-wrap: wrap;
  }
  .btn-primary {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 13px 26px;
    background: var(--accent);
    color: var(--bg);
    font-weight: 600;
    font-size: 13px;
    border-radius: 6px;
    letter-spacing: 0.02em;
    transition: opacity 0.2s, transform 0.15s;
  }
  .btn-primary:hover { opacity: 0.88; transform: translateY(-1px); }
  .btn-ghost {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 13px 26px;
    border: 1px solid var(--border);
    color: var(--text);
    font-size: 13px;
    border-radius: 6px;
    transition: border-color 0.2s, transform 0.15s;
  }
  .btn-ghost:hover { border-color: rgba(255,255,255,0.25); transform: translateY(-1px); }

  .hero-meta {
    margin-top: 56px;
    display: flex; gap: 40px; flex-wrap: wrap;
  }
  .meta-item { }
  .meta-value {
    font-family: var(--font-display);
    font-size: 36px;
    color: #fff;
    line-height: 1;
    margin-bottom: 4px;
  }
  .meta-label {
    font-size: 12px;
    color: var(--muted);
    letter-spacing: 0.04em;
  }
  .meta-sep {
    width: 1px; background: var(--border); align-self: stretch;
  }

  /* SECTIONS */
  section {
    padding: 80px 40px;
    max-width: 1100px;
    margin: 0 auto;
  }
  .section-label {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--accent);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 14px;
  }
  .section-title {
    font-family: var(--font-display);
    font-size: clamp(30px, 4vw, 44px);
    color: #fff;
    margin-bottom: 48px;
    line-height: 1.1;
  }

  /* ABOUT / CODE BLOCK */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    align-items: start;
  }
  .code-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
  }
  .code-header {
    display: flex; align-items: center; gap: 8px;
    padding: 12px 16px;
    border-bottom: 1px solid var(--border);
    background: var(--surface2);
  }
  .code-dot { width: 10px; height: 10px; border-radius: 50%; }
  .code-dot.red { background: #ff5f57; }
  .code-dot.yellow { background: #ffbd2e; }
  .code-dot.green { background: #28ca41; }
  .code-filename {
    font-family: var(--font-mono);
    font-size: 11px;
    color: var(--muted);
    margin-left: 6px;
  }
  .code-body {
    padding: 24px;
    font-family: var(--font-mono);
    font-size: 12.5px;
    line-height: 1.85;
    overflow-x: auto;
  }
  .c-keyword { color: #c792ea; }
  .c-var { color: var(--accent); }
  .c-string { color: #c3e88d; }
  .c-key { color: #82aaff; }
  .c-comment { color: #546e7a; font-style: italic; }
  .c-arr { color: #ffcb6b; }
  .c-punct { color: var(--muted); }

  .about-text {
    display: flex; flex-direction: column; gap: 20px;
  }
  .about-text p {
    font-size: 15px;
    color: #a0a0b0;
    line-height: 1.75;
  }
  .about-text strong { color: var(--text); font-weight: 500; }
  .about-location {
    display: flex; align-items: center; gap: 8px;
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
  }
  .about-location span { color: var(--accent); }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 16px;
  }
  .skill-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .skill-card:hover { border-color: rgba(255,255,255,0.15); transform: translateY(-2px); }
  .skill-card-title {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
  }
  .skill-tags {
    display: flex; flex-wrap: wrap; gap: 8px;
  }
  .tag {
    font-family: var(--font-mono);
    font-size: 11px;
    padding: 4px 10px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: var(--text);
    letter-spacing: 0.02em;
  }
  .tag.accent { border-color: rgba(0,217,255,0.3); color: var(--accent); }
  .tag.purple { border-color: rgba(124,106,255,0.3); color: var(--accent2); }

  /* PROJECT */
  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 36px;
    transition: border-color 0.2s;
  }
  .project-card:hover { border-color: rgba(0,217,255,0.2); }
  .project-header {
    display: flex; align-items: flex-start; justify-content: space-between;
    margin-bottom: 24px; gap: 20px; flex-wrap: wrap;
  }
  .project-title {
    font-family: var(--font-display);
    font-size: 26px;
    color: #fff;
    margin-bottom: 6px;
  }
  .project-subtitle {
    font-size: 13px;
    color: var(--muted);
  }
  .project-badges {
    display: flex; gap: 8px; flex-wrap: wrap;
  }
  .badge {
    font-family: var(--font-mono);
    font-size: 10px;
    padding: 4px 10px;
    border-radius: 4px;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    font-weight: 500;
  }
  .badge-green { background: rgba(34,197,94,0.12); color: var(--green); border: 1px solid rgba(34,197,94,0.2); }
  .badge-blue { background: rgba(0,217,255,0.08); color: var(--accent); border: 1px solid rgba(0,217,255,0.2); }
  .badge-purple { background: rgba(124,106,255,0.08); color: var(--accent2); border: 1px solid rgba(124,106,255,0.2); }

  .project-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 32px;
    margin-bottom: 28px;
  }
  .project-feature-list {
    list-style: none;
    display: flex; flex-direction: column; gap: 10px;
  }
  .project-feature-list li {
    display: flex; align-items: flex-start; gap: 10px;
    font-size: 14px;
    color: #9090a0;
    line-height: 1.5;
  }
  .project-feature-list li::before {
    content: '→';
    color: var(--accent);
    font-size: 12px;
    margin-top: 2px;
    flex-shrink: 0;
  }
  .project-feature-list li strong { color: var(--text); font-weight: 500; }

  .perf-stat {
    display: flex; align-items: center; gap: 12px;
    padding: 10px 0;
    border-bottom: 1px solid var(--border);
  }
  .perf-stat:last-child { border-bottom: none; }
  .perf-label { font-size: 13px; color: var(--muted); flex: 1; }
  .perf-value {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--green);
  }

  .project-stack {
    display: flex; flex-wrap: wrap; gap: 8px;
    margin-bottom: 24px;
  }
  .project-links { display: flex; gap: 12px; flex-wrap: wrap; }
  .link-btn {
    display: inline-flex; align-items: center; gap: 6px;
    font-family: var(--font-mono);
    font-size: 12px;
    padding: 9px 18px;
    border: 1px solid var(--border);
    border-radius: 5px;
    color: var(--muted);
    transition: color 0.2s, border-color 0.2s;
    letter-spacing: 0.04em;
  }
  .link-btn:hover { color: var(--text); border-color: rgba(255,255,255,0.2); }

  /* CONNECT */
  .connect-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    gap: 14px;
  }
  .connect-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 22px 24px;
    display: flex; align-items: center; gap: 14px;
    transition: border-color 0.2s, transform 0.2s;
  }
  .connect-card:hover { border-color: rgba(255,255,255,0.15); transform: translateY(-2px); }
  .connect-icon {
    width: 36px; height: 36px; border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 15px;
  }
  .connect-info {}
  .connect-name { font-size: 13px; font-weight: 500; color: var(--text); margin-bottom: 2px; }
  .connect-handle { font-family: var(--font-mono); font-size: 11px; color: var(--muted); }

  /* DIVIDER */
  .divider {
    height: 1px;
    background: var(--border);
    max-width: 1100px;
    margin: 0 auto;
  }

  /* FOOTER */
  footer {
    padding: 32px 40px;
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 16px;
  }
  .footer-logo {
    font-family: var(--font-mono);
    font-size: 12px;
    color: var(--muted);
  }
  .footer-text {
    font-size: 12px;
    color: var(--muted);
  }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 16px 20px; }
    .nav-links { display: none; }
    .hero { padding: 100px 20px 60px; }
    section { padding: 60px 20px; }
    .about-grid { grid-template-columns: 1fr; }
    .project-grid { grid-template-columns: 1fr; }
    .hero-meta { gap: 28px; }
    .meta-sep { display: none; }
    footer { padding: 24px 20px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">vs.dev</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#connect">Connect</a></li>
  </ul>
  <a href="mailto:vsanam783@gmail.com" class="nav-cta">Get in touch</a>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="hero-inner">
    <div class="hero-badge">
      <span class="badge-dot"></span>
      Available for hire
    </div>
    <h1>Backend<br/><em>Developer</em> &<br/>API Architect</h1>
    <p class="hero-sub">
      Building scalable, fault-tolerant backend systems with Node.js. Specializing in RESTful APIs, real-time WebSocket architectures, and AI/LLM integration.
    </p>
    <div class="hero-actions">
      <a href="#projects" class="btn-primary">View my work ↓</a>
      <a href="mailto:vsanam783@gmail.com" class="btn-ghost">vsanam783@gmail.com</a>
    </div>
    <div class="hero-meta">
      <div class="meta-item">
        <div class="meta-value">3+</div>
        <div class="meta-label">Years coding</div>
      </div>
      <div class="meta-sep"></div>
      <div class="meta-item">
        <div class="meta-value">10+</div>
        <div class="meta-label">APIs deployed</div>
      </div>
      <div class="meta-sep"></div>
      <div class="meta-item">
        <div class="meta-value">15+</div>
        <div class="meta-label">GitHub projects</div>
      </div>
    </div>
  </div>
</div>

<div class="divider"></div>

<!-- ABOUT -->
<section id="about">
  <div class="section-label">// about</div>
  <div class="section-title">Who I am</div>
  <div class="about-grid">
    <div class="code-block">
      <div class="code-header">
        <div class="code-dot red"></div>
        <div class="code-dot yellow"></div>
        <div class="code-dot green"></div>
        <span class="code-filename">vishal.config.ts</span>
      </div>
      <div class="code-body">
<span class="c-keyword">const</span> <span class="c-var">vishal</span> <span class="c-punct">= {</span><br/>
&nbsp;&nbsp;<span class="c-key">role</span><span class="c-punct">:</span> <span class="c-string">"Backend Developer"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;<span class="c-key">location</span><span class="c-punct">:</span> <span class="c-string">"Thane, Maharashtra 🇮🇳"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;<span class="c-key">education</span><span class="c-punct">:</span> <span class="c-string">"BCA 3rd Year"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;<br/>
&nbsp;&nbsp;<span class="c-key">stack</span><span class="c-punct">: [</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"Node.js"</span><span class="c-punct">,</span> <span class="c-string">"Express.js"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"MongoDB"</span><span class="c-punct">,</span> <span class="c-string">"Redis"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"Docker"</span><span class="c-punct">,</span> <span class="c-string">"RabbitMQ"</span><br/>
&nbsp;&nbsp;<span class="c-punct">],</span><br/>
&nbsp;&nbsp;<br/>
&nbsp;&nbsp;<span class="c-key">ai</span><span class="c-punct">: [</span><span class="c-string">"OpenAI"</span><span class="c-punct">,</span> <span class="c-string">"Groq"</span><span class="c-punct">,</span> <span class="c-string">"LangChain"</span><span class="c-punct">],</span><br/>
&nbsp;&nbsp;<br/>
&nbsp;&nbsp;<span class="c-key">openTo</span><span class="c-punct">: [</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"Full-time"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"Internships"</span><span class="c-punct">,</span><br/>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="c-string">"Freelance"</span><br/>
&nbsp;&nbsp;<span class="c-punct">]</span><br/>
<span class="c-punct">};</span>
      </div>
    </div>
    <div class="about-text">
      <div class="about-location">📍 <span>Thane, Maharashtra, India</span></div>
      <p>
        I'm a <strong>backend developer</strong> focused on building reliable, performant systems. Currently pursuing my BCA while working on real-world projects that span financial data aggregation, real-time communication, and AI-powered backends.
      </p>
      <p>
        My work revolves around <strong>scalable microservices</strong>, clean API design, and pushing the boundaries of what's possible with LLM integration. I care deeply about performance and fault tolerance — a system that gracefully handles failure is as important as one that's fast.
      </p>
      <p>
        Currently deepening my knowledge of <strong>Kubernetes</strong>, <strong>GraphQL</strong>, and large-scale system design.
      </p>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- SKILLS -->
<section id="skills">
  <div class="section-label">// skills</div>
  <div class="section-title">Tech stack</div>
  <div class="skills-grid">
    <div class="skill-card">
      <div class="skill-card-title">Backend</div>
      <div class="skill-tags">
        <span class="tag accent">Node.js</span>
        <span class="tag accent">Express.js</span>
        <span class="tag">JavaScript</span>
        <span class="tag">REST APIs</span>
        <span class="tag">Socket.io</span>
        <span class="tag">JWT</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-card-title">Databases</div>
      <div class="skill-tags">
        <span class="tag accent">MongoDB</span>
        <span class="tag accent">Redis</span>
        <span class="tag">Mongoose</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-card-title">AI & LLMs</div>
      <div class="skill-tags">
        <span class="tag purple">OpenAI</span>
        <span class="tag purple">Groq</span>
        <span class="tag purple">LangChain</span>
        <span class="tag">LLM Integration</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-card-title">DevOps & Tools</div>
      <div class="skill-tags">
        <span class="tag">Docker</span>
        <span class="tag">GitHub Actions</span>
        <span class="tag">RabbitMQ</span>
        <span class="tag">Git</span>
        <span class="tag">Linux</span>
        <span class="tag">Bash</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-card-title">Currently Learning</div>
      <div class="skill-tags">
        <span class="tag">Kubernetes</span>
        <span class="tag">GraphQL</span>
        <span class="tag">System Design</span>
      </div>
    </div>
    <div class="skill-card">
      <div class="skill-card-title">Concepts</div>
      <div class="skill-tags">
        <span class="tag">Microservices</span>
        <span class="tag">Event-driven</span>
        <span class="tag">Circuit Breakers</span>
        <span class="tag">Rate Limiting</span>
        <span class="tag">Caching</span>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-label">// projects</div>
  <div class="section-title">Featured work</div>
  <div class="project-card">
    <div class="project-header">
      <div>
        <div class="project-title">Global-Fi Ultra</div>
        <div class="project-subtitle">Financial Data Aggregator — Production Ready</div>
      </div>
      <div class="project-badges">
        <span class="badge badge-green">99% Uptime</span>
        <span class="badge badge-blue">Production</span>
        <span class="badge badge-purple">Fault-Tolerant</span>
      </div>
    </div>

    <div class="project-stack">
      <span class="tag">Node.js</span>
      <span class="tag">Express.js</span>
      <span class="tag">Socket.io</span>
      <span class="tag">MongoDB</span>
      <span class="tag">Redis</span>
      <span class="tag">Docker</span>
    </div>

    <div class="project-grid">
      <div>
        <ul class="project-feature-list">
          <li>Aggregates <strong>6+ external APIs</strong> with real-time WebSocket streaming</li>
          <li>Circuit breakers & exponential backoff for <strong>99% uptime</strong></li>
          <li><strong>Big.js</strong> arbitrary-precision decimal arithmetic — no floating-point errors</li>
          <li>Redis caching reduces external API calls by <strong>70%</strong></li>
        </ul>
      </div>
      <div>
        <div class="perf-stat">
          <span class="perf-label">Response latency</span>
          <span class="perf-value">800ms → 200ms</span>
        </div>
        <div class="perf-stat">
          <span class="perf-label">API call reduction</span>
          <span class="perf-value">−70% via Redis</span>
        </div>
        <div class="perf-stat">
          <span class="perf-label">Deployment</span>
          <span class="perf-value">Multi-stage Docker</span>
        </div>
        <div class="perf-stat">
          <span class="perf-label">Auth</span>
          <span class="perf-value">API key + rate limiting</span>
        </div>
      </div>
    </div>

    <div class="project-links">
      <a href="https://github.com/Web-dev-vishal/Global-Fi-Ultra" target="_blank" class="link-btn">
        ⎈ GitHub
      </a>
      <a href="https://global-fi-ultra.onrender.com/" target="_blank" class="link-btn">
        ↗ Live Demo
      </a>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- CONNECT -->
<section id="connect">
  <div class="section-label">// connect</div>
  <div class="section-title">Let's work together</div>
  <div class="connect-grid">
    <a href="mailto:vsanam783@gmail.com" class="connect-card">
      <div class="connect-icon" style="background:rgba(234,67,53,0.1);">📧</div>
      <div class="connect-info">
        <div class="connect-name">Email</div>
        <div class="connect-handle">vsanam783@gmail.com</div>
      </div>
    </a>
    <a href="https://www.linkedin.com/in/vishal-sanam" target="_blank" class="connect-card">
      <div class="connect-icon" style="background:rgba(10,102,194,0.1);">in</div>
      <div class="connect-info">
        <div class="connect-name">LinkedIn</div>
        <div class="connect-handle">vishal-sanam</div>
      </div>
    </a>
    <a href="https://github.com/Web-dev-vishal" target="_blank" class="connect-card">
      <div class="connect-icon" style="background:rgba(255,255,255,0.06);">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor" style="color:#ccc"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
      </div>
      <div class="connect-info">
        <div class="connect-name">GitHub</div>
        <div class="connect-handle">@Web-dev-vishal</div>
      </div>
    </a>
    <a href="https://discord.gg/9qfX7QHapM" target="_blank" class="connect-card">
      <div class="connect-icon" style="background:rgba(88,101,242,0.1);">💬</div>
      <div class="connect-info">
        <div class="connect-name">Discord</div>
        <div class="connect-handle">Join server</div>
      </div>
    </a>
    <a href="https://instagram.com/dev.vishall" target="_blank" class="connect-card">
      <div class="connect-icon" style="background:rgba(228,64,95,0.1);">📸</div>
      <div class="connect-info">
        <div class="connect-name">Instagram</div>
        <div class="connect-handle">@dev.vishall</div>
      </div>
    </a>
  </div>
</section>

<div class="divider"></div>

<footer>
  <div class="footer-logo">Vishal Sanam — Backend Developer</div>
  <div class="footer-text">Thane, Maharashtra · Open to opportunities</div>
</footer>

</body>
</html>
