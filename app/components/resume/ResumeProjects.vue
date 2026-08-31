
<template>
  <div class="section-label">
    $ ls projects/
  </div>

  <div class="projects">
    <a 
      class="project-card"
      href="https://ironman-bygray.netlify.app/"
      target="_blank"
      rel="noopener"
    >
      <div class="project-head">
        <span class="project-name">
          IronMan / IronWoman
        </span>
        <span class="badge live">
          Live project
        </span>
        <span class="project-arrow">
          &#128279;
        </span>
      </div>
      <p class="project-desc">
        A mobile-first workout tracker with fully custom training programs, live set/rep/weight logging,
        supersets, drag-and-drop reordering, a rest timer, and a workout journal with editable history.
        Auth and data are backed by Supabase with row-level security.
      </p>
      <div class="project-meta">
        Live demo · Vue 3 · JavaScript · Vite · Pinia · Supabase
      </div>
    </a>

    <a 
      class="project-card"
      href="https://taskflow-bygray.netlify.app/"
      target="_blank"
      rel="noopener"
    >
      <div class="project-head">
        <span class="project-name">
          TaskFlow
        </span>
        <span class="badge live">
          Live project
        </span>
        <span class="project-arrow">
          &#128279;
        </span>
      </div>
      <p class="project-desc">
        A task management app with a kanban board, drag-and-drop, subtasks, tags and search,
        and a persisted dark/light theme. Auth and data are backed by Supabase with row-level security.
      </p>
      <div class="project-meta">
        Live demo · Vue 3 · Vite · TypeScript · Pinia · Supabase
      </div>
    </a>

    <a 
      class="project-card"
      href="https://portfolio-bygray.netlify.app/"
      target="_blank"
      rel="noopener"
    >
      <div class="project-head">
        <span class="project-name">
          Portfolio 1.0
        </span>
        <span class="badge old">
          General · older
        </span>
        <span class="project-arrow">
          &#128279;
        </span>
      </div>
      <p class="project-desc">
        An earlier collection of personal Vue 3 / Nuxt 4 experiments - SPA builds,
        API integrations, and UI/UX practice pieces.
      </p>
      <div class="project-meta">
        Older · Vue 3 · Nuxt 4 · JavaScript
      </div>
    </a>
  </div>
</template>

<style scoped>
.projects {
  display: flex;
  flex-direction: column;
  gap: 12px;
  margin-bottom: 26px;
}

.project-card {
  display: block;
  border: 1px solid var(--line);
  border-radius: 8px;
  padding: 16px 18px;
  background: var(--card);
  text-decoration: none;
}

.project-card:hover {
  border-color: var(--card-border);
  text-decoration: none;
}

.project-head {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 8px;
}

.project-name {
  font-weight: 700;
  font-size: 15px;
  color: var(--text-strong);
}

.badge {
  font-family: var(--mono);
  font-size: 11px;
  border-radius: 999px;
  padding: 2px 9px;
}

.badge.live {
  color: var(--accent-strong);
  background: var(--accent-soft);
}

.badge.old {
  color: var(--text-muted);
  background: oklch(0.93 0.006 90);
}

.project-arrow {
  margin-left: auto;
  color: var(--text-muted);
  font-size: 13px;
}

.project-desc {
  color: var(--text-body);
  font-size: 13.5px;
  margin: 0 0 10px 0;
}

.project-meta {
  font-size: 12px;
  color: var(--text-muted);
}
</style>
