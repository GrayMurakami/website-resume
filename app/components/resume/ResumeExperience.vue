
<template>
  <div class="section-label">
    $ cat experience.log
  </div>

  <div class="exp-item">
    <div class="exp-head">
      <div class="exp-title">
        Frontend Developer
      </div>
      <div class="exp-date">
        2023.04 — present
      </div>
    </div>
    <div class="exp-org">
      OWL Technology Co., Ltd. · Japan / Remote
    </div>
    <p>
      Development and maintenance of the company's corporate portal and external site.
    </p>
    <ul>
      <li>
        Built and maintained the corporate portal and external site with JavaScript / TypeScript, PHP and WordPress.
      </li>
      <li>
        Integrated Vue 3 components into the existing WordPress / PHP stack to modernize interfaces and improve UX.
      </li>
      <li>
        Implemented access control and page protection (AJAX, JSON, tokens, role-based access).
      </li>
      <li>
        Migrated the entire corporate portal to a new domain and host, including a from-scratch environment and database setup.
      </li>
    </ul>
    <div class="tag-row">
      <span class="tag">
        #vue3
      </span>
      <span class="tag">
        #javascript
      </span>
      <span class="tag">
        #typescript
      </span>
      <span class="tag">
        #php8
      </span>
      <span class="tag">
        #wordpress
      </span>
    </div>
  </div>

  <div class="exp-item">
    <div class="exp-head">
      <div class="exp-title">
        Enterprise Project — Hewlett-Packard Enterprise (HPE), Japan
      </div>
      <div class="exp-date">
        2024.11 — present
      </div>
    </div>
    <div class="exp-org">
      Concurrent with OWL Technology
    </div>
    <p>
      Working within a large international corporate environment: following strict process and documentation standards, coordinating with enterprise infrastructure, and collaborating across an international team.
    </p>
    <div class="tag-row">
      <span class="tag">
        #rhel
      </span>
      <span class="tag">
        #bash
      </span>
      <span class="tag">
        #sql
      </span>
      <span class="tag">
        #oracle
      </span>
      <span class="tag">
        #linux-administration
      </span>
    </div>
  </div>

  <div class="exp-item">
    <div class="exp-head">
      <div class="exp-title">
        Frontend Engineer
      </div>
      <div class="exp-date">
        2021.07 — 2023.04
      </div>
    </div>
    <div class="exp-org">
      Legl (UK) · Remote
    </div>
    <p>
      Frontend development for an early-stage legaltech SaaS product.
    </p>
    <ul>
      <li>
        Built the product frontend with HTML, CSS and JavaScript (ES6+).
      </li>
      <li>
        Implemented interactive elements: forms, modals, tabs, sliders.
      </li>
      <li>
        Refactored existing markup and CSS; improved page load speed and mobile responsiveness.
      </li>
    </ul>
    <div class="tag-row">
      <span class="tag">
        #html
      </span>
      <span class="tag">
        #css
      </span>
      <span class="tag">
        #javascript
      </span>
      <span class="tag">
        #responsive
      </span>
    </div>
  </div>
</template>

<style scoped>
.exp-item {
  margin-bottom: 40px;
  border-left: 2px solid var(--card-border);
  padding-left: 16px;
}

.exp-head {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  flex-wrap: wrap;
  gap: 4px 12px;
}

.exp-title {
  font-weight: 600;
  font-size: 15px;
  color: var(--text-strong);
}

.exp-date {
  font-family: var(--mono);
  font-size: 12px;
  color: var(--text-muted);
  white-space: nowrap;
}

.exp-org {
  color: var(--accent-strong);
  font-size: 13.5px;
  margin-bottom: 6px;
}

.exp-item p {
  margin: 0 0 6px 0;
  color: var(--text-body);
}

.exp-item ul {
  margin: 0 0 8px 0;
  padding-left: 18px;
  color: var(--text-body);
}
</style>
