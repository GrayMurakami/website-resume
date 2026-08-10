<template>
  <div class="section-label">
    $ ls skills/
  </div>
  <div class="skills-grid">
    <div class="col-frontend">
      <div class="skills-title">
        frontend/
      </div>
      <div class="tag-row">
        <span class="tag">
          Vue 3 (Composition API)
        </span>
        <span class="tag">
          Nuxt 4
        </span>
        <span class="tag">
          JavaScript ES6+
        </span>
        <span class="tag">
          TypeScript
        </span>
        <span class="tag">
          SPA
        </span>
        <span class="tag">
          Pinia
        </span>
        <span class="tag">
          HTML5 / CSS3
        </span>
        <span class="tag">
          Responsive layout
        </span>
        <span class="tag">
          Component architecture
        </span>
        <span class="tag">
          Forms &amp; validation
        </span>
      </div>
    </div>

    <div class="col-tools">
      <div class="skills-title">
        tools/
      </div>
      <div class="tag-row">
        <span class="tag">
          Git / GitHub
        </span>
        <span class="tag">
          npm
        </span>
        <span class="tag">
          Vite
        </span>
        <span class="tag">
          REST API
        </span>
        <span class="tag">
          Supabase
        </span>
        <span class="tag">
          Netlify
        </span>
        <span class="tag">
          WordPress / PHP
        </span>
        <span class="tag">
          AJAX / JSON
        </span>
        <span class="tag">
          Role-based access
        </span>
      </div>
    </div>

    <div class="col-backend">
      <div class="skills-title">
        backend &amp; infra/
      </div>
      <div class="tag-row">
        <span class="tag">
          PHP 8
        </span>
        <span class="tag">
          MySQL
        </span>
        <span class="tag">
          Oracle
        </span>
        <span class="tag">
          Linux administration
        </span>
        <span class="tag">
          AWS (infra/ops)
        </span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills-grid {
  display: grid;
  grid-template-columns: 1fr 1.25fr;
  grid-template-areas: "frontend tools" "frontend backend";
  gap: 18px 24px;
  margin-bottom: 26px;
}

.col-frontend { 
  grid-area: frontend; 
}

.col-tools { 
  grid-area: tools; 
}

.col-backend { 
  grid-area: backend; 
  align-self: start; 
}

.skills-title {
  font-weight: 600;
  margin-bottom: 8px;
  color: var(--text-strong);
}
</style>