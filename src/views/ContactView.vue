<script setup>
import { ref } from "vue";

const status = ref("");

function submitMessage() {
  status.value = "Envoi en cours…";
}
</script>

<template>
  <div class="contact shell">
    <p class="eyebrow"><i></i> CONTACT</p>
    <div class="contact-grid">
      <div>
        <h1>Une opportunité<br />à <em>partager ?</em></h1>
        <p class="lead">
          Je recherche un stage d’août à octobre ainsi qu’une alternance en
          cybersécurité pour la rentrée 2027.
        </p>
        <div class="direct-details">
          <a href="tel:+33753271294">+33 7 53 27 12 94</a>
          <span>France · Île-de-France</span>
        </div>
      </div>

      <div>
        <form
          class="contact-form"
          action="https://formsubmit.co/njetchounzepadaniel@gmail.com"
          method="POST"
          @submit="submitMessage"
        >
          <input
            type="hidden"
            name="_subject"
            value="Nouveau message depuis le portfolio"
          />
          <input type="hidden" name="_template" value="table" />
          <input
            type="text"
            name="_honey"
            class="honeypot"
            tabindex="-1"
            autocomplete="off"
          />

          <label
            >Nom<input required type="text" name="nom" placeholder="Votre nom"
          /></label>
          <label
            >E-mail<input
              required
              type="email"
              name="email"
              placeholder="vous@entreprise.com"
          /></label>
          <label
            >Objet<input
              required
              type="text"
              name="objet"
              placeholder="Stage, alternance, opportunité…"
          /></label>
          <label
            >Message<textarea
              required
              name="message"
              rows="5"
              placeholder="Votre message"
            ></textarea>
          </label>
          <button type="submit">Envoyer le message <span>→</span></button>
          <p class="form-status" aria-live="polite">
            {{ status || "Votre message sera envoyé directement à Daniel." }}
          </p>
        </form>

        <div class="socials">
          <a
            href="https://www.linkedin.com/in/daniel-njetchou-nzepa-b465602b4"
            target="_blank"
            rel="noreferrer"
            >LinkedIn ↗</a
          >
          <a href="mailto:njetchounzepadaniel@gmail.com">Envoyer un e-mail ↗</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact {
  padding: 105px 0 135px;
  min-height: calc(100vh - 160px);
}
.eyebrow {
  color: var(--mint);
  font:
    500 10px "DM Mono",
    monospace;
  letter-spacing: 1.8px;
  margin: 0 0 25px;
}
.eyebrow i {
  display: inline-block;
  width: 7px;
  height: 7px;
  margin-right: 9px;
  background: var(--mint);
  border-radius: 50%;
}
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 100px;
}
h1 {
  font-size: clamp(46px, 5.4vw, 73px);
  letter-spacing: -3px;
  line-height: 1;
  margin: 0;
}
em {
  color: var(--mint);
  font-style: normal;
}
.lead {
  color: var(--muted);
  max-width: 480px;
  line-height: 1.8;
  font-size: 15px;
  margin: 28px 0;
}
.direct-details {
  border-top: 1px solid var(--line);
  width: min(100%, 380px);
  padding-top: 17px;
  display: flex;
  flex-direction: column;
  gap: 6px;
  font:
    12px "DM Mono",
    monospace;
}
.direct-details a {
  color: var(--text);
}
.direct-details a:hover {
  color: var(--mint);
}
.direct-details span {
  color: var(--muted);
}
.contact-form {
  padding: 27px;
  border: 1px solid var(--line);
  background: var(--panel);
  display: grid;
  gap: 15px;
}
.contact-form label {
  display: grid;
  gap: 7px;
  color: var(--muted);
  font:
    10px "DM Mono",
    monospace;
  letter-spacing: 1px;
}
.contact-form input,
.contact-form textarea {
  width: 100%;
  border: 1px solid var(--line);
  background: var(--ink);
  color: var(--text);
  padding: 12px;
  resize: vertical;
  font:
    13px Manrope,
    sans-serif;
}
.contact-form input:focus,
.contact-form textarea:focus {
  outline: 1px solid var(--mint);
  border-color: var(--mint);
}
.contact-form button {
  margin-top: 3px;
  min-height: 46px;
  border: 1px solid var(--mint);
  background: var(--mint);
  color: var(--ink);
  cursor: pointer;
  font-size: 12px;
  font-weight: 800;
  text-align: left;
  padding: 0 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-status {
  margin: 0;
  color: var(--muted);
  font-size: 10px;
  line-height: 1.5;
}
.honeypot {
  display: none;
}
.socials {
  display: flex;
  gap: 18px;
  margin-top: 18px;
  color: var(--muted);
  font-size: 11px;
}
.socials a:hover {
  color: var(--mint);
}
@media (max-width: 650px) {
  .contact {
    padding: 70px 0;
  }
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 50px;
  }
}
</style>
