<script setup>
import ProjectCard from "../components/ProjectCard.vue";
import cvFile from "./CV_NJETCHOU_NZEPA_DANIEL_2026.pdf";
const projects = [
  {
    number: "01",
    type: "NETWORK SECURITY",
    icon: "⌘",
    title: "Infrastructure réseau sécurisée",
    description:
      "Architecture multi-sites conçue sur Cisco Packet Tracer, avec segmentation et services réseau résilients.",
    technologies: ["OSPF", "RIP", "EtherChannel", "DNS"],
    result: "6 sites interconnectés",
  },
  {
    number: "02",
    type: "SECURITY OPERATIONS",
    icon: "◉",
    title: "Infrastructure SOC",
    description:
      "Mise en place d’une chaîne de supervision, d’automatisation et de réponse aux incidents pour accélérer le traitement des alertes.",
    technologies: ["Wazuh", "Shuffle", "OpenVAS", "Grafana"],
    result: "Détection & réponse",
  },
  {
    number: "03",
    type: "WEB DEVELOPMENT",
    icon: "</>",
    title: "Plateforme web restaurant",
    description:
      "Application web complète, pensée de la base de données à l’interface, avec une architecture moderne et maintenable.",
    technologies: ["React.js", "Laravel", "PostgreSQL"],
    result: "Full-stack delivery",
  },
];
const skills = [
  "SIEM / XDR",
  "Analyse de logs",
  "Réseaux Cisco",
  "Vulnerability scanning",
  "Linux / Kali",
  "Wireshark",
  "SOC automation",
  "Proxmox",
];
</script>

<template>
  <div class="home">
    <section class="hero">
      <div class="shell hero-grid">
        <div class="hero-copy">
          <p class="eyebrow"><i></i> À LA RECHERCHE D’OPPORTUNITÉS</p>
          <h1>Sécuriser.<br /><em>Comprendre.</em><br />Protéger.</h1>
          <p class="intro">
            Étudiant en 4e année à EFREI, campus Paris, orienté cybersécurité.
            Je construis des environnements plus fiables, de l’infrastructure
            réseau à la détection d’incidents.
          </p>
          <div class="availability">
            <span><b>STAGE</b> Août — octobre</span
            ><span><b>ALTERNANCE</b> Rentrée 2027</span>
          </div>
          <div class="actions">
            <a href="#projects" class="button primary"
              >Explorer mes projets <span>↓</span></a
            ><a :href="cvFile" target="_blank" class="button ghost"
              >Consulter le CV ↗</a
            >
          </div>
        </div>
        <div class="signal-panel">
          <div class="panel-head">
            <span>SECURITY STATUS</span><b>● ACTIVE</b>
          </div>
          <div class="radar">
            <div class="radar-core"></div>
            <span class="radar-dot"></span>
          </div>
          <div class="telemetry">
            <p><span>FOCUS</span><strong>BLUE TEAM / SOC</strong></p>
            <p><span>LOCATION</span><strong>PARIS, FR</strong></p>
            <p><span>STATUS</span><strong>LEARNING · BUILDING</strong></p>
          </div>
        </div>
      </div>
    </section>
    <section class="proof shell">
      <div><strong>03</strong><span>projets présentés</span></div>
      <div><strong>04+</strong><span>outils cyber maîtrisés</span></div>
      <div><strong>2027</strong><span>alternance recherchée</span></div>
    </section>
    <section id="projects" class="projects shell">
      <div class="section-head">
        <div>
          <p class="eyebrow"><i></i> SELECTED WORK</p>
          <h2>Projets <em>cybersécurité</em></h2>
        </div>
        <p>
          Des réalisations concrètes centrées sur la visibilité, la résilience
          et la réponse aux incidents.
        </p>
      </div>
      <div class="projects-grid">
        <ProjectCard
          v-for="project in projects"
          :key="project.number"
          :project="project"
        />
      </div>
    </section>
    <section class="skills">
      <div class="shell skills-inner">
        <p class="eyebrow"><i></i> TOOLKIT</p>
        <div class="skills-layout">
          <h2>Technologies<br />et <em>pratiques.</em></h2>
          <div class="skill-list">
            <span v-for="skill in skills" :key="skill"
              >{{ skill }} <b>↗</b></span
            >
          </div>
        </div>
      </div>
    </section>
    <section class="cta shell">
      <p class="eyebrow"><i></i> LET'S CONNECT</p>
      <h2>Construisons quelque chose<br /><em>de plus sûr.</em></h2>
      <RouterLink to="/contact" class="button primary"
        >Me contacter <span>→</span></RouterLink
      >
    </section>
  </div>
</template>

<style scoped>
:global(.theme-dark) .hero {
  background:
    radial-gradient(
      circle at 81% 45%,
      rgba(132, 40, 49, 0.22),
      transparent 26%
    ),
    linear-gradient(120deg, #10090a, #1a0e10);
}
:global(.theme-dark) .signal-panel,
:global(.theme-dark) .project-card {
  background-color: #1a1012;
}
:global(.theme-dark) .skills {
  background: #130d0e;
}
:global(.theme-light) .hero {
  background:
    radial-gradient(circle at 81% 45%, rgba(154, 61, 69, 0.1), transparent 28%),
    #fafafa;
}
.hero {
  min-height: 650px;
  border-bottom: 1px solid var(--line);
}
.hero-grid {
  min-height: 650px;
  display: grid;
  grid-template-columns: 1.15fr 0.85fr;
  gap: 70px;
  align-items: center;
}
.eyebrow {
  color: var(--mint);
  font:
    500 10px "DM Mono",
    monospace;
  letter-spacing: 1.8px;
  margin: 0 0 22px;
}
.eyebrow i {
  display: inline-block;
  width: 7px;
  height: 7px;
  margin-right: 9px;
  background: var(--mint);
  border-radius: 50%;
  box-shadow: 0 0 12px var(--mint);
}
h1,
h2 {
  letter-spacing: -2.8px;
  font-size: clamp(48px, 6vw, 78px);
  line-height: 0.99;
  margin: 0;
}
em {
  color: var(--mint);
  font-style: normal;
}
.intro {
  max-width: 530px;
  color: var(--muted);
  font-size: 15px;
  line-height: 1.8;
  margin: 27px 0 22px;
}
.availability {
  display: flex;
  gap: 10px;
  margin-bottom: 28px;
  flex-wrap: wrap;
}
.availability span {
  border: 1px solid var(--line);
  color: var(--text);
  font:
    11px "DM Mono",
    monospace;
  padding: 9px 11px;
}
.availability b {
  color: var(--mint);
  font-weight: 500;
  margin-right: 8px;
}
.actions {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}
.button {
  min-height: 47px;
  padding: 0 19px;
  display: inline-flex;
  align-items: center;
  gap: 24px;
  border: 1px solid var(--mint);
  font-size: 12px;
  font-weight: 800;
}
.primary {
  color: var(--ink);
  background: var(--mint);
}
.primary:hover {
  filter: brightness(1.15);
}
.ghost {
  color: var(--text);
  border-color: var(--line);
}
.ghost:hover {
  border-color: var(--mint);
  color: var(--mint);
}
.signal-panel {
  width: min(100%, 370px);
  justify-self: end;
  border: 1px solid var(--line);
  background: var(--panel);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
}
.panel-head {
  display: flex;
  justify-content: space-between;
  padding: 16px;
  border-bottom: 1px solid var(--line);
  font:
    10px "DM Mono",
    monospace;
  letter-spacing: 1px;
  color: var(--muted);
}
.panel-head b {
  color: var(--mint);
  font-weight: 400;
}
.radar {
  margin: 30px auto;
  width: 200px;
  aspect-ratio: 1;
  border: 1px solid var(--line);
  border-radius: 50%;
  position: relative;
  background:
    repeating-radial-gradient(
      circle,
      transparent 0 32px,
      color-mix(in srgb, var(--mint) 13%, transparent) 33px 34px
    ),
    linear-gradient(
      90deg,
      transparent 49.5%,
      color-mix(in srgb, var(--mint) 18%, transparent) 50% 50.5%,
      transparent 51%
    ),
    linear-gradient(
      transparent 49.5%,
      color-mix(in srgb, var(--mint) 18%, transparent) 50% 50.5%,
      transparent 51%
    );
}
.radar:after {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: 50%;
  background: conic-gradient(
    from 320deg,
    transparent 0 70%,
    color-mix(in srgb, var(--mint) 22%, transparent) 82%,
    transparent 95%
  );
}
.radar-core {
  position: absolute;
  z-index: 1;
  top: calc(50% - 5px);
  left: calc(50% - 5px);
  width: 10px;
  height: 10px;
  background: var(--mint);
  border-radius: 50%;
  box-shadow: 0 0 15px var(--mint);
}
.radar-dot {
  position: absolute;
  z-index: 1;
  top: 37px;
  right: 48px;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--mint);
}
.telemetry {
  padding: 0 20px 16px;
}
.telemetry p {
  margin: 0;
  padding: 10px 0;
  border-top: 1px solid var(--line);
  display: flex;
  justify-content: space-between;
  font:
    10px "DM Mono",
    monospace;
}
.telemetry span {
  color: var(--muted);
}
.telemetry strong {
  font-weight: 400;
  color: var(--text);
}
.proof {
  min-height: 122px;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
.proof div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  border-right: 1px solid var(--line);
  padding-left: 28px;
}
.proof div:first-child {
  padding-left: 0;
}
.proof div:last-child {
  border: 0;
}
.proof strong {
  color: var(--mint);
  font-size: 28px;
  letter-spacing: -1px;
}
.proof span {
  color: var(--muted);
  font-size: 11px;
}
.projects {
  padding: 125px 0;
}
.section-head {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  gap: 40px;
  margin-bottom: 47px;
}
.section-head h2,
.skills h2,
.cta h2 {
  font-size: clamp(38px, 4vw, 55px);
}
.section-head > p {
  max-width: 340px;
  color: var(--muted);
  font-size: 13px;
  line-height: 1.7;
}
.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}
.skills {
  border-top: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
  background: var(--surface);
}
.skills-inner {
  padding: 100px 0;
}
.skills-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 100px;
  align-items: start;
}
.skill-list {
  display: grid;
  grid-template-columns: 1fr 1fr;
  border-top: 1px solid var(--line);
}
.skill-list span {
  color: var(--text);
  padding: 16px 6px;
  font-size: 12px;
  border-bottom: 1px solid var(--line);
}
.skill-list b {
  float: right;
  color: var(--mint);
  font-weight: 400;
}
.cta {
  padding: 105px 0;
}
.cta h2 {
  margin: 0 0 31px;
}
@media (max-width: 800px) {
  .hero-grid {
    grid-template-columns: 1fr;
    gap: 36px;
    padding: 86px 0;
  }
  .hero {
    min-height: auto;
  }
  .signal-panel {
    justify-self: start;
  }
  .projects-grid {
    grid-template-columns: 1fr 1fr;
  }
  .section-head,
  .skills-layout {
    gap: 30px;
  }
  .proof div {
    padding-left: 15px;
  }
}
@media (max-width: 560px) {
  .hero-grid {
    padding: 72px 0;
  }
  .signal-panel {
    width: 100%;
  }
  .proof {
    grid-template-columns: 1fr;
    padding: 18px 0;
  }
  .proof div,
  .proof div:first-child {
    padding: 12px 0;
    border-right: 0;
    border-bottom: 1px solid var(--line);
  }
  .proof div:last-child {
    border: 0;
  }
  .projects {
    padding: 75px 0;
  }
  .section-head,
  .skills-layout {
    display: block;
  }
  .section-head > p {
    margin-top: 24px;
  }
  .projects-grid {
    grid-template-columns: 1fr;
  }
  .skills-inner,
  .cta {
    padding: 70px 0;
  }
  .skills h2 {
    margin-bottom: 30px;
  }
  .skill-list {
    grid-template-columns: 1fr;
  }
}
</style>
