<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta
    name="description"
    content="Portfolio de Dan, développeur full-stack spécialisé dans la création d'expériences web modernes."
  />
  <title>Dan — Développeur Full-Stack</title>
  <link rel="icon" type="image/png" href="logo.png" />
  <link rel="apple-touch-icon" href="logo.png" />

  <style>
    :root {
      --bg: #080b14;
      --bg-soft: #101522;
      --card: rgba(255, 255, 255, 0.06);
      --text: #f5f7ff;
      --muted: #9da7bd;
      --primary: #8b5cf6;
      --secondary: #22d3ee;
      --border: rgba(255, 255, 255, 0.1);
      --radius: 22px;
      --max-width: 1160px;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
        "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at 15% 10%, rgba(139, 92, 246, 0.16), transparent 30%),
        radial-gradient(circle at 85% 20%, rgba(34, 211, 238, 0.1), transparent 26%),
        var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(100% - 40px, var(--max-width));
      margin: auto;
    }

    .gradient-text {
      background: linear-gradient(100deg, var(--secondary), var(--primary));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    /* Navigation */
    header {
      position: fixed;
      z-index: 10;
      top: 0;
      width: 100%;
      backdrop-filter: blur(18px);
      background: rgba(8, 11, 20, 0.72);
      border-bottom: 1px solid rgba(255, 255, 255, 0.06);
    }

    nav {
      height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .logo {
      font-size: 1.35rem;
      font-weight: 900;
      letter-spacing: -0.05em;
    }

    .logo span {
      color: var(--secondary);
    }

    .nav-links {
      display: flex;
      gap: 28px;
      list-style: none;
      color: var(--muted);
      font-size: 0.93rem;
    }

    .nav-links a {
      transition: color 0.25s ease;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .menu-button {
      display: none;
      border: 0;
      background: transparent;
      color: var(--text);
      font-size: 1.5rem;
      cursor: pointer;
    }

    /* Hero */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 130px 0 80px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: center;
      gap: 70px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      padding: 8px 13px;
      border: 1px solid var(--border);
      border-radius: 999px;
      color: var(--muted);
      font-size: 0.82rem;
      margin-bottom: 23px;
      background: rgba(255, 255, 255, 0.025);
    }

    .status-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #34d399;
      box-shadow: 0 0 14px #34d399;
    }

    h1 {
      max-width: 720px;
      font-size: clamp(3.3rem, 8vw, 6.4rem);
      line-height: 0.98;
      letter-spacing: -0.08em;
      margin-bottom: 26px;
    }

    .hero-description {
      max-width: 610px;
      color: var(--muted);
      font-size: 1.12rem;
      margin-bottom: 35px;
    }

    .actions {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 13px 20px;
      border-radius: 12px;
      border: 1px solid var(--border);
      font-weight: 700;
      transition: transform 0.25s ease, background 0.25s ease;
    }

    .button:hover {
      transform: translateY(-3px);
    }

    .button-primary {
      color: white;
      border: none;
      background: linear-gradient(110deg, var(--primary), #6d5dfc);
      box-shadow: 0 12px 30px rgba(139, 92, 246, 0.25);
    }

    .button-secondary {
      color: var(--muted);
      background: var(--card);
    }

    .hero-card {
      position: relative;
      min-height: 400px;
      display: grid;
      place-items: center;
    }

    .orb {
      width: 280px;
      height: 280px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--secondary), var(--primary) 55%, #ed4899);
      filter: blur(1px);
      box-shadow:
        0 0 80px rgba(139, 92, 246, 0.35),
        0 0 150px rgba(34, 211, 238, 0.18);
      animation: float 5s ease-in-out infinite;
    }

    .code-window {
      position: absolute;
      width: min(100%, 360px);
      padding: 22px;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      background: rgba(12, 16, 29, 0.84);
      backdrop-filter: blur(16px);
      box-shadow: 0 25px 80px rgba(0, 0, 0, 0.35);
      transform: rotate(4deg);
    }

    .window-dots {
      display: flex;
      gap: 7px;
      margin-bottom: 22px;
    }

    .window-dots i {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: #ff6b6b;
    }

    .window-dots i:nth-child(2) {
      background: #ffd166;
    }

    .window-dots i:nth-child(3) {
      background: #06d6a0;
    }

    pre {
      color: #c4b5fd;
      font-size: 0.88rem;
      white-space: pre-wrap;
    }

    /* Sections */
    section {
      padding: 110px 0;
    }

    .section-heading {
      max-width: 650px;
      margin-bottom: 42px;
    }

    .section-label {
      color: var(--secondary);
      text-transform: uppercase;
      letter-spacing: 0.16em;
      font-size: 0.76rem;
      font-weight: 800;
      margin-bottom: 12px;
    }

    h2 {
      font-size: clamp(2.1rem, 5vw, 3.7rem);
      line-height: 1.05;
      letter-spacing: -0.06em;
    }

    .section-heading p {
      color: var(--muted);
      margin-top: 17px;
    }

    .about-grid,
    .contact-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 55px;
      align-items: start;
    }

    .about-text p {
      color: var(--muted);
      margin-bottom: 18px;
      font-size: 1.05rem;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin-top: 28px;
    }

    .stat {
      padding: 18px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
    }

    .stat strong {
      display: block;
      font-size: 1.65rem;
    }

    .stat span {
      color: var(--muted);
      font-size: 0.8rem;
    }

    .skills {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .skill {
      padding: 11px 15px;
      border-radius: 10px;
      background: var(--card);
      border: 1px solid var(--border);
      color: #d8dcf0;
    }

    /* Projects */
    .projects {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .project-card {
      overflow: hidden;
      border: 1px solid var(--border);
      border-radius: var(--radius);
      background: var(--card);
      transition: transform 0.3s ease, border-color 0.3s ease;
    }

    .project-card:hover {
      transform: translateY(-8px);
      border-color: rgba(139, 92, 246, 0.65);
    }

    .project-visual {
      height: 190px;
      display: grid;
      place-items: center;
      font-size: 3.3rem;
      background:
        linear-gradient(135deg, rgba(139, 92, 246, 0.55), transparent),
        #161d32;
    }

    .project-card:nth-child(2) .project-visual {
      background:
        linear-gradient(135deg, rgba(34, 211, 238, 0.45), transparent),
        #14232d;
    }

    .project-card:nth-child(3) .project-visual {
      background:
        linear-gradient(135deg, rgba(236, 72, 153, 0.45), transparent),
        #28172b;
    }

    .project-content {
      padding: 24px;
    }

    .project-content h3 {
      font-size: 1.25rem;
      margin-bottom: 8px;
    }

    .project-content p {
      color: var(--muted);
      font-size: 0.92rem;
      margin-bottom: 18px;
    }

    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .tag {
      color: var(--secondary);
      font-size: 0.76rem;
    }

    /* Contact */
    .contact-box {
      padding: 32px;
      border-radius: var(--radius);
      border: 1px solid var(--border);
      background: linear-gradient(135deg, rgba(139, 92, 246, 0.13), var(--card));
    }

    .contact-box p {
      color: var(--muted);
      margin: 14px 0 24px;
    }

    .contact-link {
      display: block;
      font-size: 1.12rem;
      color: var(--secondary);
      margin: 13px 0;
    }

    form {
      display: grid;
      gap: 14px;
    }

    input,
    textarea {
      width: 100%;
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 15px;
      color: var(--text);
      background: rgba(255, 255, 255, 0.045);
      font: inherit;
      outline: none;
    }

    input:focus,
    textarea:focus {
      border-color: var(--primary);
    }

    textarea {
      min-height: 140px;
      resize: vertical;
    }

    form .button {
      cursor: pointer;
      font: inherit;
    }

    footer {
      padding: 28px 0;
      border-top: 1px solid var(--border);
      color: var(--muted);
      font-size: 0.9rem;
    }

    /* Animation */
    .reveal {
      opacity: 0;
      transform: translateY(22px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0) scale(1);
      }
      50% {
        transform: translateY(-18px) scale(1.03);
      }
    }

    /* Responsive */
    @media (max-width: 850px) {
      .menu-button {
        display: block;
      }

      .nav-links {
        position: absolute;
        top: 76px;
        left: 20px;
        right: 20px;
        display: none;
        flex-direction: column;
        gap: 0;
        padding: 12px;
        border: 1px solid var(--border);
        border-radius: 16px;
        background: #101522;
      }

      .nav-links.open {
        display: flex;
      }

      .nav-links a {
        display: block;
        padding: 13px;
      }

      .hero-grid,
      .about-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .hero-card {
        min-height: 330px;
      }

      .projects {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 560px) {
      .container {
        width: min(100% - 28px, var(--max-width));
      }

      section {
        padding: 75px 0;
      }

      h1 {
        font-size: 3.35rem;
      }

      .projects,
      .stats {
        grid-template-columns: 1fr;
      }

      .orb {
        width: 220px;
        height: 220px;
      }

      .code-window {
        width: 92%;
      }
    }
  </style>
</head>

<body>
  <header>
    <nav class="container">
      <a class="logo" href="#accueil">dan<span>.</span>dev</a>

      <button class="menu-button" aria-label="Ouvrir le menu">☰</button>

      <ul class="nav-links">
        <li><a href="#accueil">Accueil</a></li>
        <li><a href="#apropos">À propos</a></li>
        <li><a href="#projets">Projets</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="hero" id="accueil">
      <div class="container hero-grid">
        <div class="reveal">
          <div class="eyebrow">
            <span class="status-dot"></span>
            Disponible pour de nouveaux projets
          </div>

          <h1>
            Je construis le web de
            <span class="gradient-text">demain.</span>
          </h1>

          <p class="hero-description">
            Je suis Dan, développeur full-stack. Je transforme des idées
            ambitieuses en produits numériques rapides, élégants et utiles.
          </p>

          <div class="actions">
            <a class="button button-primary" href="#projets">
              Voir mes projets →
            </a>
            <a class="button button-secondary" href="#contact">
              Me contacter
            </a>
          </div>
        </div>

        <div class="hero-card reveal">
          <div class="orb"></div>

          <div class="code-window">
            <div class="window-dots">
              <i></i><i></i><i></i>
            </div>

            <pre><code><span style="color:#67e8f9">const</span> developer = {
  name: <span style="color:#86efac">"Dan"</span>,
  role: <span style="color:#86efac">"Full-Stack"</span>,
  passion: <span style="color:#f9a8d4">true</span>,
  coffee: <span style="color:#f9a8d4">Infinity</span>
};</code></pre>
          </div>
        </div>
      </div>
    </section>

    <section id="apropos">
      <div class="container about-grid">
        <div class="section-heading reveal">
          <div class="section-label">01 — À propos</div>
          <h2>Du concept au produit.</h2>
        </div>

        <div class="about-text reveal">
          <p>
            J’aime résoudre des problèmes complexes avec des solutions simples.
            Mon approche combine développement, design et compréhension des
            besoins utilisateurs.
          </p>

          <p>
            De la première ligne de code au déploiement en production, je crée
            des applications fiables, accessibles et faciles à faire évoluer.
          </p>

          <div class="stats">
            <div class="stat">
              <strong>5+</strong>
              <span>années d'expérience</span>
            </div>
            <div class="stat">
              <strong>30+</strong>
              <span>projets réalisés</span>
            </div>
            <div class="stat">
              <strong>100%</strong>
              <span>curiosité technique</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="competences">
      <div class="container">
        <div class="section-heading reveal">
          <div class="section-label">02 — Compétences</div>
          <h2>Les outils que j'utilise.</h2>
          <p>
            Une stack moderne pour créer des expériences performantes et
            maintenables.
          </p>
        </div>

        <div class="skills reveal">
          <span class="skill">JavaScript</span>
          <span class="skill">TypeScript</span>
          <span class="skill">React</span>
          <span class="skill">Next.js</span>
          <span class="skill">Node.js</span>
          <span class="skill">Python</span>
          <span class="skill">PostgreSQL</span>
          <span class="skill">MongoDB</span>
          <span class="skill">Docker</span>
          <span class="skill">AWS</span>
          <span class="skill">Git</span>
          <span class="skill">Figma</span>
        </div>
      </div>
    </section>

    <section id="projets">
      <div class="container">
        <div class="section-heading reveal">
          <div class="section-label">03 — Projets sélectionnés</div>
          <h2>Quelques réalisations.</h2>
          <p>
            Une sélection de projets conçus avec attention et livrés avec
            exigence.
          </p>
        </div>

        <div class="projects">
          <article class="project-card reveal">
            <div class="project-visual">◈</div>
            <div class="project-content">
              <h3>Nova Finance</h3>
              <p>
                Tableau de bord financier permettant de suivre ses dépenses,
                revenus et objectifs en temps réel.
              </p>
              <div class="tags">
                <span class="tag">React</span>
                <span class="tag">· Node.js</span>
                <span class="tag">· PostgreSQL</span>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-visual">✦</div>
            <div class="project-content">
              <h3>FlowTask</h3>
              <p>
                Application collaborative de gestion de projets pour des
                équipes distribuées.
              </p>
              <div class="tags">
                <span class="tag">Next.js</span>
                <span class="tag">· TypeScript</span>
                <span class="tag">· Prisma</span>
              </div>
            </div>
          </article>

          <article class="project-card reveal">
            <div class="project-visual">⌁</div>
            <div class="project-content">
              <h3>Echo API</h3>
              <p>
                Plateforme API destinée aux développeurs, avec documentation
                interactive et authentification sécurisée.
              </p>
              <div class="tags">
                <span class="tag">Python</span>
                <span class="tag">· FastAPI</span>
                <span class="tag">· Docker</span>
              </div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container contact-grid">
        <div class="section-heading reveal">
          <div class="section-label">04 — Contact</div>
          <h2>Un projet en tête ?</h2>
          <p>
            Parlons de ton idée, de tes objectifs et de la meilleure façon de
            lui donner vie.
          </p>

<a class="contact-link" href="mailto:dkazadi926@gmail.com">
            dkazadi926@gmail.com
          </a>
          <a class="contact-link" href="https://github.com/diata926" target="_blank">
            GitHub ↗
          </a>
          <a class="contact-link" href="https://www.facebook.com/profile.php?id=61574067602589" target="_blank">
            facebook ↗
          </a>
        </div>

        <div class="contact-box reveal">
<form id="contact-form" action="https://formsubmit.co/dkazadi926@gmail.com" method="POST">
            <input type="text" name="name" placeholder="Ton nom" autocomplete="name" required />
            <input type="email" name="email" placeholder="Ton adresse email" autocomplete="email" required />
            <textarea name="message" placeholder="Parle-moi de ton projet..." required></textarea>
            <input type="hidden" name="_subject" value="Nouveau message depuis le portfolio Dan" />
            <input type="hidden" name="_template" value="table" />
            <input type="text" name="_honey" tabindex="-1" autocomplete="off" style="display:none" />
            <button class="button button-primary" type="submit">
              Envoyer le message →
            </button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      © <span id="year"></span> Dan. Conçu et développé avec passion.
    </div>
  </footer>

  <script>
    const menuButton = document.querySelector(".menu-button");
    const navLinks = document.querySelector(".nav-links");
    const form = document.querySelector("#contact-form");

    menuButton.addEventListener("click", () => {
      navLinks.classList.toggle("open");
    });

    document.querySelectorAll(".nav-links a").forEach((link) => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("open");
      });
    });

    

    document.querySelector("#year").textContent = new Date().getFullYear();

    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add("visible");
            observer.unobserve(entry.target);
          }
        });
      },
      { threshold: 0.12 }
    );

    document.querySelectorAll(".reveal").forEach((element) => {
      observer.observe(element);
    });
  </script>
</body>
</html>
