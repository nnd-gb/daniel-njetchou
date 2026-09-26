<script setup>
import cvFile from "./CV_NJETCHOU_2026-2027";
</script>
<template>
  <div class="page shell">
    <p class="eyebrow"><i></i> PROFILE / 2026</p>
    <div class="intro">
      <h1>Un profil orienté<br /><em>défense.</em></h1>
      <p>
        Étudiant en 4e année à EFREI, campus Paris, je me spécialise
        progressivement dans les métiers de la cybersécurité et des opérations
        de sécurité.
      </p>
    </div>
    <div class="content">
      <aside>
        <p class="label">FORMATION</p>
        <h3>EFREI Paris</h3>
        <p>4e année — ingénierie informatique<br />Campus Paris</p>
        <a :href="cvFile" target="_blank" class="cv">Télécharger mon CV ↗</a>
      </aside>
      <div>
        <section>
          <p class="label">OBJECTIF</p>
          <h2>Détecter, analyser, répondre.</h2>
          <p class="body">
            Mon intérêt se porte particulièrement sur le SOC, l’analyse des
            événements de sécurité, les réseaux et l’automatisation de la
            réponse aux incidents.
          </p>
        </section>
        <section>
          <p class="label">EXPÉRIENCES & PROJETS</p>
          <div class="timeline">
            <article>
              <b>Configuration SIEM / XDR</b><span>Stage en entreprise</span>
              <p>
                Installation et configuration de Wazuh pour centraliser les
                journaux et améliorer la détection d’incidents.
              </p>
            </article>
            <article>
              <b>Infrastructure SOC</b><span>ITGStore</span>
              <p>
                Collaboration à l’intégration de Wazuh, Shuffle, Grafana et
                OpenVAS dans une approche de supervision sécurité.
              </p>
            </article>
          </div>
        </section>
        <section>
          <p class="label">CERTIFICATIONS & APPRENTISSAGE</p>
          <div class="tags">
            <span>CCNA 1 — Cisco</span><span>TryHackMe SOC Level 1</span
            ><span>Wireshark</span><span>Kali Linux</span>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>
<style scoped>
.page {
  padding: 92px 0 120px;
}
.eyebrow,
.label {
  color: var(--mint);
  font:
    500 10px "DM Mono",
    monospace;
  letter-spacing: 1.7px;
}
.eyebrow i {
  display: inline-block;
  width: 7px;
  height: 7px;
  margin-right: 9px;
  background: var(--mint);
  border-radius: 50%;
}
.intro {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 50px;
  align-items: end;
  padding: 15px 0 90px;
  border-bottom: 1px solid var(--line);
}
h1 {
  font-size: clamp(45px, 6vw, 76px);
  letter-spacing: -3px;
  line-height: 1;
  margin: 0;
}
em {
  color: var(--mint);
  font-style: normal;
}
.intro > p,
.body,
aside > p {
  color: var(--muted);
  font-size: 14px;
  line-height: 1.8;
  margin: 0;
}
.content {
  display: grid;
  grid-template-columns: 280px 1fr;
  gap: 85px;
  padding-top: 55px;
}
aside {
  border-right: 1px solid var(--line);
  padding-right: 34px;
}
aside h3 {
  font-size: 19px;
  margin: 15px 0 8px;
}
.cv {
  display: inline-block;
  border: 1px solid var(--mint);
  padding: 12px 14px;
  color: var(--mint);
  font-size: 11px;
  font-weight: 800;
  margin-top: 27px;
}
section {
  padding-bottom: 42px;
  margin-bottom: 42px;
  border-bottom: 1px solid var(--line);
}
section:last-child {
  border: 0;
}
.label {
  margin: 0 0 18px;
}
h2 {
  font-size: 29px;
  letter-spacing: -1px;
  margin: 0 0 15px;
}
.body {
  max-width: 600px;
}
.timeline {
  display: grid;
  gap: 15px;
}
.timeline article {
  padding: 20px;
  background: var(--panel);
  border-left: 2px solid var(--mint);
}
.timeline b {
  font-size: 14px;
  display: block;
}
.timeline span {
  display: block;
  color: var(--mint);
  font:
    10px "DM Mono",
    monospace;
  margin: 7px 0;
}
.timeline p {
  margin: 0;
  color: var(--muted);
  font-size: 12px;
  line-height: 1.65;
}
.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.tags span {
  border: 1px solid var(--line);
  padding: 9px 11px;
  color: #d5e7de;
  font:
    11px "DM Mono",
    monospace;
}
@media (max-width: 650px) {
  .page {
    padding: 65px 0;
  }
  .intro,
  .content {
    display: block;
  }
  .intro {
    padding-bottom: 50px;
  }
  .intro > p {
    margin-top: 25px;
  }
  .content {
    padding-top: 38px;
  }
  aside {
    border-right: 0;
    border-bottom: 1px solid var(--line);
    padding: 0 0 35px;
    margin-bottom: 38px;
  }
}
</style>
