[index (1).html](https://github.com/user-attachments/files/29020711/index.1.html)
-<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tyrone Brooks — UX/UI Designer</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;900&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0d0d0d;
      --surface: #141414;
      --surface2: #1a1a1a;
      --border: rgba(255,255,255,0.08);
      --gold: #f5c518;
      --text: #ffffff;
      --muted: rgba(255,255,255,0.45);
      --pill-bg: rgba(255,255,255,0.06);
      --pill-active: #ffffff;
      --radius-lg: 20px;
      --radius-pill: 999px;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Inter', sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 40px 20px 80px;
    }

    /* ── CARD SHELL ── */
    .card {
      width: 100%;
      max-width: 860px;
      border-radius: var(--radius-lg);
      overflow: hidden;
      background: var(--surface);
      border: 1px solid var(--border);
      box-shadow: 0 40px 120px rgba(0,0,0,0.7);
    }

    /* ── NAV BAR ── */
    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px 24px;
      background: rgba(0,0,0,0.3);
      backdrop-filter: blur(12px);
    }
    .status {
      display: flex;
      align-items: center;
      gap: 7px;
      font-size: 12px;
      font-weight: 500;
      color: var(--muted);
    }
    .status-dot {
      width: 8px; height: 8px;
      background: #4ade80;
      border-radius: 50%;
      box-shadow: 0 0 6px #4ade80;
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }
    .btn-gold {
      background: var(--gold);
      color: #000;
      font-size: 12px;
      font-weight: 700;
      border: none;
      border-radius: var(--radius-pill);
      padding: 8px 18px;
      cursor: pointer;
      letter-spacing: 0.02em;
      transition: opacity 0.2s;
    }
    .btn-gold:hover { opacity: 0.85; }

    /* ── HERO ── */
    .hero {
      position: relative;
      min-height: 360px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 40px 36px 36px;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at 70% 40%, rgba(180,80,20,0.55) 0%, rgba(100,30,5,0.3) 45%, transparent 70%),
                  linear-gradient(180deg, #1a0d00 0%, #0d0d0d 100%);
    }
    /* Silhouette figure */
    .hero-figure {
      position: absolute;
      right: 48px;
      bottom: 0;
      width: 220px;
      height: 300px;
      display: flex;
      align-items: flex-end;
      justify-content: center;
    }
    .figure-svg {
      width: 100%;
      height: 100%;
      opacity: 0.85;
    }
    .hero-content { position: relative; z-index: 2; }
    .hero-eyebrow {
      font-size: 13px;
      font-weight: 600;
      color: var(--gold);
      letter-spacing: 0.04em;
      margin-bottom: 8px;
    }
    .hero-name {
      font-size: clamp(48px, 7vw, 80px);
      font-weight: 900;
      line-height: 0.95;
      letter-spacing: -0.03em;
      margin-bottom: 24px;
    }
    .hero-contacts {
      display: flex;
      flex-wrap: wrap;
      gap: 10px 28px;
      margin-bottom: 28px;
    }
    .contact-item {
      display: flex;
      align-items: center;
      gap: 7px;
      font-size: 12px;
      color: var(--muted);
    }
    .contact-item svg { opacity: 0.6; flex-shrink: 0; }

    /* ── TAB BAR ── */
    .tab-bar {
      position: relative;
      z-index: 2;
      display: flex;
      gap: 4px;
      background: rgba(255,255,255,0.05);
      border: 1px solid var(--border);
      border-radius: var(--radius-pill);
      padding: 4px;
      width: fit-content;
    }
    .tab {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 12px;
      font-weight: 500;
      color: var(--muted);
      padding: 7px 16px;
      border-radius: var(--radius-pill);
      cursor: pointer;
      transition: all 0.2s;
      border: none;
      background: transparent;
    }
    .tab:hover { color: var(--text); }
    .tab.active {
      background: var(--text);
      color: #000;
      font-weight: 700;
    }
    .tab svg { width: 13px; height: 13px; }

    /* ── SECTIONS ── */
    .section { display: none; padding: 36px; }
    .section.active { display: block; }

    .section-title {
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 20px;
    }

    /* Summary */
    .summary-text {
      font-size: 15px;
      line-height: 1.75;
      color: rgba(255,255,255,0.75);
      max-width: 600px;
    }
    .summary-highlights {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 24px;
    }
    .highlight-chip {
      background: var(--pill-bg);
      border: 1px solid var(--border);
      border-radius: var(--radius-pill);
      padding: 6px 14px;
      font-size: 12px;
      color: rgba(255,255,255,0.7);
    }

    /* Experience */
    .exp-item { margin-bottom: 32px; }
    .exp-item:last-child { margin-bottom: 0; }
    .exp-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 12px;
      flex-wrap: wrap;
      margin-bottom: 4px;
    }
    .exp-company { font-size: 15px; font-weight: 700; }
    .exp-date { font-size: 12px; color: var(--muted); white-space: nowrap; }
    .exp-role { font-size: 13px; color: var(--gold); font-weight: 500; margin-bottom: 8px; }
    .exp-desc { font-size: 13px; line-height: 1.7; color: rgba(255,255,255,0.6); }
    .exp-achievement {
      margin-top: 6px;
      font-size: 12px;
      font-weight: 600;
      color: rgba(255,255,255,0.85);
    }
    .exp-achievement span { color: var(--gold); }
    .divider { height: 1px; background: var(--border); margin: 28px 0; }

    /* Skills */
    .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 32px; }
    @media (max-width: 560px) { .skills-grid { grid-template-columns: 1fr; } }

    .skill-group-title {
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--muted);
      margin-bottom: 16px;
    }
    .tool-icons {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      margin-bottom: 28px;
    }
    .tool-icon {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5px;
    }
    .tool-icon-circle {
      width: 44px; height: 44px;
      border-radius: 12px;
      border: 1px solid var(--border);
      background: var(--surface2);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 10px;
      font-weight: 700;
      color: var(--text);
    }
    .tool-icon span { font-size: 10px; color: var(--muted); }

    .lang-item { margin-bottom: 14px; }
    .lang-label {
      display: flex;
      justify-content: space-between;
      font-size: 12px;
      color: rgba(255,255,255,0.7);
      margin-bottom: 6px;
    }
    .lang-bar {
      height: 3px;
      background: var(--border);
      border-radius: 999px;
      overflow: hidden;
    }
    .lang-fill {
      height: 100%;
      background: var(--gold);
      border-radius: 999px;
      transition: width 0.8s ease;
    }

    .edu-item { margin-bottom: 16px; display: flex; gap: 10px; }
    .edu-dot {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: var(--gold);
      margin-top: 5px;
      flex-shrink: 0;
    }
    .edu-name { font-size: 13px; font-weight: 600; }
    .edu-sub { font-size: 11px; color: var(--gold); margin-top: 2px; }
    .edu-date { font-size: 11px; color: var(--muted); margin-top: 2px; }

    /* Links / Projects */
    .projects-grid { display: grid; gap: 20px; }
    .project-card {
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 24px;
      transition: border-color 0.2s;
    }
    .project-card:hover { border-color: rgba(245,197,24,0.3); }
    .project-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 8px;
    }
    .project-name { font-size: 20px; font-weight: 800; }
    .project-tag { font-size: 11px; color: var(--muted); margin-bottom: 12px; }
    .project-section-label {
      font-size: 11px;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: rgba(255,255,255,0.5);
      margin: 12px 0 4px;
    }
    .project-desc { font-size: 13px; line-height: 1.7; color: rgba(255,255,255,0.6); }
    .project-metric { font-size: 13px; color: rgba(255,255,255,0.7); line-height: 1.6; }
    .project-metric strong { color: var(--gold); }
    .arrow-btn {
      background: rgba(255,255,255,0.06);
      border: 1px solid var(--border);
      border-radius: 50%;
      width: 32px; height: 32px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      color: var(--muted);
      transition: all 0.2s;
      flex-shrink: 0;
    }
    .arrow-btn:hover { background: var(--gold); color: #000; border-color: var(--gold); }

    /* Links section */
    .links-list { display: flex; flex-direction: column; gap: 12px; }
    .link-item {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: var(--surface2);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 16px 20px;
      text-decoration: none;
      transition: border-color 0.2s;
    }
    .link-item:hover { border-color: rgba(245,197,24,0.3); }
    .link-name { font-size: 14px; font-weight: 600; color: var(--text); }
    .link-url { font-size: 12px; color: var(--muted); margin-top: 2px; }
    .link-icon { color: var(--muted); }
  </style>
</head>
<body>

<div class="card">

  <!-- NAV -->
  <div class="nav">
    <div class="status">
      <span class="status-dot"></span>
      Open to work
    </div>
    <button class="btn-gold" onclick="downloadCV()">Download CV</button>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-bg"></div>

    <!-- Silhouette SVG -->
    <div class="hero-figure">
      <svg class="figure-svg" viewBox="0 0 220 300" fill="none" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <radialGradient id="glow" cx="50%" cy="30%" r="60%">
            <stop offset="0%" stop-color="#c85a10" stop-opacity="0.8"/>
            <stop offset="100%" stop-color="#3a1000" stop-opacity="0"/>
          </radialGradient>
        </defs>
        <!-- ambient glow -->
        <ellipse cx="110" cy="80" rx="90" ry="120" fill="url(#glow)" opacity="0.6"/>
        <!-- body silhouette -->
        <path d="M80 300 L80 200 Q78 180 72 165 Q60 140 58 120 Q54 90 70 75 Q80 55 110 50 Q140 45 150 65 Q162 85 158 115 Q155 140 145 163 Q138 180 138 200 L140 300 Z" fill="#1a0900" opacity="0.9"/>
        <!-- head -->
        <ellipse cx="110" cy="45" rx="28" ry="32" fill="#1a0900" opacity="0.9"/>
        <!-- neck -->
        <rect x="98" y="70" width="24" height="20" rx="5" fill="#1a0900" opacity="0.9"/>
        <!-- shoulder slope left -->
        <path d="M80 160 Q55 155 42 175 L50 300 L80 300 Z" fill="#1a0900" opacity="0.85"/>
        <!-- shoulder slope right -->
        <path d="M140 160 Q165 155 178 175 L170 300 L140 300 Z" fill="#1a0900" opacity="0.85"/>
        <!-- t-shirt crease lines subtle -->
        <path d="M95 120 Q100 140 98 165" stroke="rgba(0,0,0,0.3)" stroke-width="1" fill="none"/>
        <path d="M120 118 Q118 140 120 163" stroke="rgba(0,0,0,0.3)" stroke-width="1" fill="none"/>
      </svg>
    </div>

    <div class="hero-content">
      <div class="hero-eyebrow">UX/UI Designer</div>
      <h1 class="hero-name">Tyrone<br>Brooks</h1>
      <div class="hero-contacts">
        <div class="contact-item">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
          tyrone.brooks@gmail.com
        </div>
        <div class="contact-item">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="2" width="20" height="20" rx="5"/><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
          linkedin.com/in/tyrone-brooks
        </div>
        <div class="contact-item">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.15 12a19.79 19.79 0 0 1-3-8.59A2 2 0 0 1 3.12 1.5h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L7.91 9a16 16 0 0 0 6.08 6.08l.96-.96a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 21.73 16.92z"/></svg>
          +1 404-555-9876
        </div>
        <div class="contact-item">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20 10c0 6-8 12-8 12S4 16 4 10a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
          Atlanta, US
        </div>
      </div>

      <!-- TABS -->
      <div class="tab-bar" role="tablist">
        <button class="tab active" onclick="showSection('home', this)" role="tab">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
          Home
        </button>
        <button class="tab" onclick="showSection('summary', this)" role="tab">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
          Summary
        </button>
        <button class="tab" onclick="showSection('experience', this)" role="tab">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
          Experience
        </button>
        <button class="tab" onclick="showSection('skills', this)" role="tab">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          Skills
        </button>
        <button class="tab" onclick="showSection('projects', this)" role="tab">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="m14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>
          Links
        </button>
      </div>
    </div>
  </div>

  <!-- ── HOME ── -->
  <div id="home" class="section active">
    <p class="section-title">About Me</p>
    <p class="summary-text">
      I'm a UX/UI Designer with 6+ years crafting digital experiences that people actually enjoy using. I specialize in turning complex problems into elegant, intuitive interfaces — from early-stage discovery through high-fidelity prototyping and developer handoff.
    </p>
    <div class="summary-highlights">
      <span class="highlight-chip">Product Design</span>
      <span class="highlight-chip">Design Systems</span>
      <span class="highlight-chip">User Research</span>
      <span class="highlight-chip">Prototyping</span>
      <span class="highlight-chip">Interaction Design</span>
      <span class="highlight-chip">Motion</span>
    </div>
  </div>

  <!-- ── SUMMARY ── -->
  <div id="summary" class="section">
    <p class="section-title">Professional Summary</p>
    <p class="summary-text">
      Senior UX/UI Designer with 6 years of experience building design systems and consumer-facing products at scale. Proven track record of increasing conversion and engagement through research-led design decisions. Comfortable working across the full product lifecycle — from 0-to-1 discovery to iterative improvement on mature products.
    </p>
    <br>
    <p class="summary-text">
      I thrive in cross-functional teams, collaborating closely with PMs, engineers, and researchers to ship work that is both beautiful and measurably effective.
    </p>
    <div class="summary-highlights" style="margin-top:28px;">
      <span class="highlight-chip">6+ Years Experience</span>
      <span class="highlight-chip">B2B & B2C</span>
      <span class="highlight-chip">Mobile-First</span>
      <span class="highlight-chip">Accessibility</span>
    </div>
  </div>

  <!-- ── EXPERIENCE ── -->
  <div id="experience" class="section">
    <p class="section-title">Work Experience</p>

    <div class="exp-item">
      <div class="exp-header">
        <div class="exp-company">Flowstate Inc.</div>
        <div class="exp-date">Jan 2022 – Present</div>
      </div>
      <div class="exp-role">Lead UX/UI Designer</div>
      <div class="exp-desc">Owned end-to-end design of the core web application, redesigning the online shopping experience for a mid-sized fashion brand. Focused on mobile-first design, seamless navigation, and interactive product displays with a robust filtering system.</div>
      <div class="exp-achievement">Improved conversion rates by <span>20% within three months</span> post-launch.</div>
    </div>

    <div class="divider"></div>

    <div class="exp-item">
      <div class="exp-header">
        <div class="exp-company">Luma Creative Studio</div>
        <div class="exp-date">Mar 2020 – Dec 2021</div>
      </div>
      <div class="exp-role">UX Designer</div>
      <div class="exp-desc">Led discovery workshops and usability testing for 8 client products. Delivered wireframes, prototypes, and design systems. Reduced design-to-dev handoff friction by establishing a shared component library in Figma.</div>
      <div class="exp-achievement">Client NPS improved from <span>42 to 71</span> over 18 months.</div>
    </div>

    <div class="divider"></div>

    <div class="exp-item">
      <div class="exp-header">
        <div class="exp-company">Orbital Health</div>
        <div class="exp-date">Jun 2018 – Feb 2020</div>
      </div>
      <div class="exp-role">UI Designer (Contract)</div>
      <div class="exp-desc">Designed patient-facing mobile app UI in collaboration with clinical teams. Balanced accessibility requirements (WCAG AA) with a warm, approachable visual language for a sensitive healthcare context.</div>
      <div class="exp-achievement">App reached <span>4.7★</span> on App Store within first quarter.</div>
    </div>
  </div>

  <!-- ── SKILLS ── -->
  <div id="skills" class="section">
    <div class="skills-grid">
      <div>
        <p class="section-title">Tools</p>
        <div class="skill-group-title">Design & Prototyping</div>
        <div class="tool-icons">
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:linear-gradient(135deg,#0acf83,#1abcfe,#a259ff,#f24e1e)">
              <svg width="20" height="20" viewBox="0 0 38 57" fill="white"><path d="M19 28.5a9.5 9.5 0 1 1 19 0 9.5 9.5 0 0 1-19 0z"/><path d="M0 47.5A9.5 9.5 0 0 1 9.5 38H19v9.5a9.5 9.5 0 0 1-19 0z"/><path d="M19 0v19h9.5a9.5 9.5 0 0 0 0-19H19z"/><path d="M0 9.5A9.5 9.5 0 0 0 9.5 19H19V0H9.5A9.5 9.5 0 0 0 0 9.5z"/><path d="M0 28.5A9.5 9.5 0 0 0 9.5 38H19V19H9.5A9.5 9.5 0 0 0 0 28.5z"/></svg>
            </div>
            <span>Figma</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#001e36">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="#31a8ff"><path d="M0 0h24v24H0z" fill="none"/><path d="M14.5 2.1L20 7.5V22H4V2h10.5zM13 3H5v18h14V8.5L13 3zm1 1.5L17.5 8H14V4.5z"/></svg>
            </div>
            <span>Ps</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#300;">
              <span style="color:#ff9a00;font-size:13px;font-weight:900;">Ai</span>
            </div>
            <span>Illustrator</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#1d1d1d">
              <span style="color:#fff;font-size:11px;font-weight:800;">Sk</span>
            </div>
            <span>Sketch</span>
          </div>
        </div>

        <div class="skill-group-title">3D & Motion</div>
        <div class="tool-icons">
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#1e1e2e">
              <span style="color:#e87b35;font-size:11px;font-weight:800;">Sp</span>
            </div>
            <span>Spline</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#1a1a2e">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="#e87d0d"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 14.5v-9l6 4.5-6 4.5z"/></svg>
            </div>
            <span>Blender</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#0f1117">
              <svg width="18" height="18" viewBox="0 0 24 24" fill="white"><polygon points="13,2 3,14 12,14 11,22 21,10 12,10"/></svg>
            </div>
            <span>Framer</span>
          </div>
          <div class="tool-icon">
            <div class="tool-icon-circle" style="background:#1a1a1a">
              <span style="color:#f5c518;font-size:9px;font-weight:800;">MJ</span>
            </div>
            <span>Midjourney</span>
          </div>
        </div>

        <p class="section-title" style="margin-top:8px;">Education & Certificates</p>
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div>
            <div class="edu-name">Savannah College of Art and Design (SCAD)</div>
            <div class="edu-sub">Bachelor of Fine Arts in User Experience Design</div>
            <div class="edu-date">2016</div>
          </div>
        </div>
        <div class="edu-item">
          <div class="edu-dot"></div>
          <div>
            <div class="edu-name">Google UX Design Certificate</div>
            <div class="edu-date">August 2022</div>
          </div>
        </div>
      </div>

      <div>
        <p class="section-title">Languages</p>
        <div class="lang-item">
          <div class="lang-label"><span>English</span><span>Native</span></div>
          <div class="lang-bar"><div class="lang-fill" style="width:100%"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-label"><span>Spanish</span><span>Intermediate</span></div>
          <div class="lang-bar"><div class="lang-fill" style="width:65%"></div></div>
        </div>
        <div class="lang-item">
          <div class="lang-label"><span>French</span><span>Basic</span></div>
          <div class="lang-bar"><div class="lang-fill" style="width:25%"></div></div>
        </div>

        <p class="section-title" style="margin-top:28px;">Soft Skills</p>
        <div class="summary-highlights" style="flex-direction:column; gap:8px;">
          <span class="highlight-chip" style="width:fit-content">Strategic Thinking</span>
          <span class="highlight-chip" style="width:fit-content">Cross-functional Collaboration</span>
          <span class="highlight-chip" style="width:fit-content">User Research & Testing</span>
          <span class="highlight-chip" style="width:fit-content">Stakeholder Presentations</span>
          <span class="highlight-chip" style="width:fit-content">Design Critique & Mentorship</span>
        </div>
      </div>
    </div>
  </div>

  <!-- ── PROJECTS / LINKS ── -->
  <div id="projects" class="section">
    <p class="section-title">Featured Projects</p>
    <div class="projects-grid">

      <div class="project-card">
        <div class="project-header">
          <div>
            <div class="project-name">Flowstate</div>
            <div class="project-tag">Web Application</div>
          </div>
          <div class="arrow-btn">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M7 17 17 7M7 7h10v10"/></svg>
          </div>
        </div>
        <div class="project-section-label">About The Project</div>
        <div class="project-desc">Redesigned the online shopping experience for a mid-sized fashion brand. Focused on creating an elegant, mobile-first design with seamless navigation and interactive product displays. Integrated a robust filtering system for faster product discovery.</div>
        <div class="project-section-label">Achievements</div>
        <div class="project-metric">Improved conversion rates by <strong>20% within three months</strong> post-launch.</div>
      </div>

      <div class="project-card">
        <div class="project-header">
          <div>
            <div class="project-name">Orbital Health</div>
            <div class="project-tag">Mobile App</div>
          </div>
          <div class="arrow-btn">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M7 17 17 7M7 7h10v10"/></svg>
          </div>
        </div>
        <div class="project-section-label">About The Project</div>
        <div class="project-desc">Patient-facing iOS and Android app designed for a telehealth provider. Balanced WCAG AA accessibility standards with a warm, calming aesthetic. Worked closely with clinical staff to validate flows.</div>
        <div class="project-section-label">Achievements</div>
        <div class="project-metric">Achieved <strong>4.7★ App Store rating</strong> within the first quarter of launch.</div>
      </div>

    </div>

    <p class="section-title" style="margin-top:36px;">Online Presence</p>
    <div class="links-list">
      <a class="link-item" href="#" onclick="return false;">
        <div>
          <div class="link-name">Portfolio</div>
          <div class="link-url">tyronebrooks.design</div>
        </div>
        <div class="link-icon">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
      </a>
      <a class="link-item" href="#" onclick="return false;">
        <div>
          <div class="link-name">LinkedIn</div>
          <div class="link-url">linkedin.com/in/tyrone-brooks</div>
        </div>
        <div class="link-icon">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
      </a>
      <a class="link-item" href="#" onclick="return false;">
        <div>
          <div class="link-name">Dribbble</div>
          <div class="link-url">dribbble.com/tyronebrooks</div>
        </div>
        <div class="link-icon">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17 17 7M7 7h10v10"/></svg>
        </div>
      </a>
    </div>
  </div>

</div><!-- /card -->

<script>
  function showSection(id, btn) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    btn.classList.add('active');
  }

  function downloadCV() {
    // In a real implementation this would trigger a PDF download
    alert('CV download would start here!');
  }

  // Animate language bars on tab switch
  document.querySelectorAll('.tab').forEach(tab => {
    tab.addEventListener('click', () => {
      setTimeout(() => {
        document.querySelectorAll('.lang-fill').forEach(bar => {
          const w = bar.style.width;
          bar.style.width = '0%';
          requestAnimationFrame(() => {
            setTimeout(() => bar.style.width = w, 50);
          });
        });
      }, 10);
    });
  });
</script>
</body>
</html>
