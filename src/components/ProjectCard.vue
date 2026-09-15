<script setup>
defineProps({ project: { type: Object, required: true } });
</script>

<template>
  <article class="project-card">
    <div class="card-top">
      <span class="project-index">{{ project.number }}</span
      ><span class="project-type">{{ project.type }}</span>
    </div>
    <div class="card-icon" aria-hidden="true">{{ project.icon }}</div>
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
    <ul>
      <li v-for="tech in project.technologies" :key="tech">{{ tech }}</li>
    </ul>
    <div class="card-footer">
      <span>{{ project.result }}</span
      ><span aria-hidden="true">↗</span>
    </div>
  </article>
</template>

<style scoped>
.project-card {
  min-height: 350px;
  padding: 28px;
  display: flex;
  flex-direction: column;
  border: 1px solid var(--line);
  background: linear-gradient(
    145deg,
    rgba(20, 50, 44, 0.78),
    rgba(10, 27, 24, 0.78)
  );
  transition:
    transform 0.25s,
    border-color 0.25s,
    background 0.25s;
}
.project-card:hover {
  transform: translateY(-6px);
  border-color: rgba(142, 240, 189, 0.58);
  background: #112e28;
}
.card-top,
.card-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.project-index,
.project-type {
  font:
    500 10px "DM Mono",
    monospace;
  letter-spacing: 1.4px;
  color: var(--mint);
}
.project-type {
  color: var(--muted);
}
.card-icon {
  color: var(--mint);
  font-size: 28px;
  margin: 35px 0 19px;
}
h3 {
  font-size: 19px;
  letter-spacing: -0.5px;
  margin: 0 0 12px;
}
p {
  color: var(--muted);
  line-height: 1.65;
  font-size: 13px;
  margin: 0;
}
ul {
  padding: 0;
  margin: 22px 0;
  display: flex;
  flex-wrap: wrap;
  gap: 7px;
  list-style: none;
}
li {
  border: 1px solid var(--line);
  padding: 5px 8px;
  font:
    10px "DM Mono",
    monospace;
  color: #c6ded5;
}
.card-footer {
  margin-top: auto;
  border-top: 1px solid var(--line);
  padding-top: 18px;
  color: var(--muted);
  font-size: 11px;
}
.card-footer span:last-child {
  color: var(--mint);
  font-size: 18px;
}
</style>
