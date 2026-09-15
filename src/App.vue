<script setup>
import { ref, watch } from "vue";
import { RouterLink, RouterView } from "vue-router";
import cvFile from "./views/CV_NJETCHOU_NZEPA_DANIEL_2026.pdf";

const isMenuOpen = ref(false);
const theme = ref(localStorage.getItem("portfolio-theme") || "dark");

watch(theme, (value) => localStorage.setItem("portfolio-theme", value));

function closeMenu() {
  isMenuOpen.value = false;
}
</script>

<template>
  <div id="app" :class="`theme-${theme}`">
    <header class="site-header">
      <nav class="nav shell" aria-label="Navigation principale">
        <RouterLink to="/" class="brand" @click="closeMenu">
          <span class="brand-mark">DN</span>
          <span><div class="special-name"> Daniel N. </div><small>CYBERSECURITY</small></span>
        </RouterLink>

        <div class="nav-actions">
          <button
            class="theme-toggle"
            type="button"
            :aria-label="
              theme === 'dark'
                ? 'Passer au thème clair'
                : 'Passer au thème sombre'
            "
            @click="theme = theme === 'dark' ? 'light' : 'dark'"
          >
            {{ theme === "dark" ? "☼ Clair" : "◐ Sombre" }}
          </button>
          <button
            class="menu-toggle"
            :aria-expanded="isMenuOpen"
            aria-label="Ouvrir le menu"
            @click="isMenuOpen = !isMenuOpen"
          >
            <span></span><span></span>
          </button>
        </div>

        <div class="nav-links" :class="{ open: isMenuOpen }">
          <RouterLink to="/" @click="closeMenu">Accueil</RouterLink>
          <RouterLink to="/about" @click="closeMenu">Profil</RouterLink>
          <RouterLink to="/contact" @click="closeMenu">Contact</RouterLink>
          <a :href="cvFile" download>Télécharger le CV</a>
        </div>
      </nav>
    </header>

    <main><RouterView /></main>

    <footer class="site-footer">
      <div class="shell footer-inner">
        <p>© 2026 Daniel Jordan Njet​chou Nzepa</p>
        <div>
          <a href="https://github.com/nnd-gb" target="_blank" rel="noreferrer"
            >GitHub ↗</a
          >
          <a
            href="https://tryhackme.com/p/daniel.gb"
            target="_blank"
            rel="noreferrer"
            >TryHackMe ↗</a
          >
          <a
            href="https://www.linkedin.com/in/daniel-njetchou-nzepa-b465602b4"
            target="_blank"
            rel="noreferrer"
            >LinkedIn ↗</a
          >
        </div>
      </div>
    </footer>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=DM+Mono:wght@400;500&family=Manrope:wght@400;500;600;700;800&display=swap");

.theme-dark {
  --ink: #090a0f;
  --surface: #101117;
  --panel: #171820;
  --line: rgba(235, 237, 245, 0.12);
  --muted: #a5a7b2;
  --text: #f4f3f5;
  --mint: #c86d72;
}

.theme-light {
  --ink: #fafafa;
  --surface: #ffffff;
  --panel: #f3f4f4;
  --line: rgba(18, 24, 25, 0.14);
  --muted: #63706f;
  --text: #172120;
  --mint: #9a3d45;
}

* {
  box-sizing: border-box;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  min-width: 320px;
  background: var(--ink);
  color: var(--text);
  font-family: Manrope, Arial, sans-serif;
}
a {
  color: inherit;
  text-decoration: none;
}
button {
  font: inherit;
}
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  background: var(--ink);
  transition:
    background 0.25s,
    color 0.25s;
}
main {
  flex: 1;
}
.shell {
  width: min(1160px, calc(100% - 48px));
  margin: 0 auto;
}
.site-header {
  position: sticky;
  top: 0;
  z-index: 20;
  border-bottom: 1px solid var(--line);
  background: color-mix(in srgb, var(--ink) 90%, transparent);
  backdrop-filter: blur(16px);
}
.nav {
  height: 78px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}
.brand {
  display: flex;
  align-items: center;
  gap: 11px;
  color: var(--text);
  font-weight: 800;
  font-size: 14px;
  letter-spacing: -0.4px;
}
.brand small {
  display: block;
  color: var(--mint);
  font:
    500 9px "DM Mono",
    monospace;
  letter-spacing: 1.8px;
  margin-top: 2px;
}
.brand-mark {
  width: 37px;
  height: 37px;
  display: grid;
  place-items: center;
  border: 1px solid var(--mint);
  color: var(--mint);
  font:
    500 12px "DM Mono",
    monospace;
}
.nav-actions {
  display: flex;
  align-items: center;
  gap: 8px;
}
.theme-toggle {
  border: 1px solid var(--line);
  background: transparent;
  color: var(--muted);
  padding: 8px 10px;
  font:
    500 10px "DM Mono",
    monospace;
  cursor: pointer;
}
.theme-toggle:hover {
  border-color: var(--mint);
  color: var(--mint);
}
.nav-links {
  display: flex;
  gap: 26px;
  align-items: center;
}
.nav-links a {
  color: var(--muted);
  font-size: 12px;
  font-weight: 700;
  transition: color 0.2s;
}
.nav-links a:hover,
.nav-links a.router-link-exact-active {
  color: var(--mint);
}
.menu-toggle {
  display: none;
  background: transparent;
  border: 0;
  padding: 8px;
}
.menu-toggle span {
  width: 22px;
  height: 1px;
  display: block;
  margin: 5px;
  background: var(--text);
}
.site-footer {
  border-top: 1px solid var(--line);
  color: var(--muted);
  font-size: 11px;
}
.footer-inner {
  min-height: 82px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}
.footer-inner p {
  margin: 0;
}
.footer-inner div {
  display: flex;
  gap: 18px;
}
.footer-inner a:hover {
  color: var(--mint);
}
@media (max-width: 760px) {
  .nav-links {
    gap: 14px;
  }
  .nav-links a:last-child {
    display: none;
  }
}
@media (max-width: 650px) {
  .shell {
    width: min(100% - 32px, 1160px);
  }
  .menu-toggle {
    display: block;
  }
  .nav-links {
    position: absolute;
    inset: 78px 0 auto;
    padding: 24px;
    background: var(--surface);
    border-bottom: 1px solid var(--line);
    display: none;
    flex-direction: column;
    align-items: flex-start;
    gap: 20px;
  }
  .nav-links.open {
    display: flex;
  }
  .nav-links a:last-child {
    display: block;
  }
  .footer-inner {
    padding: 20px 0;
    align-items: flex-start;
    flex-direction: column;
  }
  .footer-inner div {
    gap: 12px;
    flex-wrap: wrap;
  }
}
</style>
