
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
        Incrementally migrating a corporate portal (75 pages) and external site (15 pages) from WordPress PHP templates to Vue 3 without disrupting the live site, 
        progressively converting existing JavaScript to TypeScript: components embedded in WP templates, Vite bundles loaded via wp_enqueue_script, 
        server data passed as JSON in data attributes. 70 of 90 pages migrated to date.
      </li>
      <li>
        Replaced 10 duplicated PHP templates (forms, search, dashboard) with 3 reusable Vue components using composables and Pinia, 
        cutting new form delivery from 3 days to 1.
      </li>
      <li>
        Built admin-issued 24-hour access links to restricted pages with server-side expiry validation and notifications; 
        implemented server-side access control for 3 roles.
      </li>
      <li>
        Reduced LCP on the home and product pages from 3.2s to 2.5s (Lighthouse, mobile) via WebP, responsive srcset/sizes and hero image preloading.
      </li>
      <li>
        Migrated the portal and site to a new host and domain with zero downtime and zero data loss: parallel deployment, 
        database restore with table prefix change, 301 redirects, traffic cutover after verification.
      </li>
      <li>
        Backend: designed database schema for leave and medical check-up tracking; set up server cron jobs for new-user processing and automated data updates.
      </li>
    </ul>
    <div class="tag-row">
      <span class="tag">
        #vue3
      </span>
      <span class="tag">
        #typescript
      </span>
      <span class="tag">
        #javascript
      </span>
      <span class="tag">
        #pinia
      </span>
      <span class="tag">
        #vite
      </span>
      <span class="tag">
        #wordpress
      </span>
      <span class="tag">
        #php8
      </span>
      <span class="tag">
        #mysql
      </span>
    </div>
  </div>

  <div class="exp-item-sub">
    <div class="exp-head-sub">
      <p class="exp-title">
        <span class="exp-org-sub">
          Client assignment:
        </span>
          Hewlett Packard Enterprise
        <span class="exp-note">(dispatched, hybrid)</span>
      </p>
      <div class="exp-date">
        2024.11 — present
      </div>
    </div>
    <ul>
      <li>
        Security patching across production, DR and test environments (RHEL, Windows Server, AWS) 
        under strict change-management and documentation standards.
      </li>
      <li>
        Prepared change requests, procedure documents and status reports, and coordinated approvals 
        with Japanese and international team members in Japanese and English.
      </li>
    </ul>
    <div class="tag-row">
      <span class="tag">
        #rhel
      </span>
      <span class="tag">
        #windows server
      </span>
      <span class="tag">
        #aws
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
    </div>
  </div>

  <div class="exp-item">
    <div class="exp-head-sub">
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
        Built core UI components (forms, modals, tabs, sliders) from scratch in vanilla JavaScript, without an existing design system.
      </li>
      <li>
        Refactored legacy markup and CSS to improve mobile responsiveness.
      </li>
      <li>
        Contributed UI/UX ideas in team discussions.
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
        #javascript (vanilla)
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

.exp-item-sub {
  margin-bottom: 40px;
  padding-left: 26px;
}

.exp-head {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  flex-wrap: wrap;
  gap: 4px 12px;
}

.exp-head-sub {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  flex-wrap: wrap;
  gap: 4px 12px;
  margin-bottom: 10px;

  & .exp-title {
    margin: 0;
  }
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
  margin-bottom: 10px;
}

.exp-org-sub {
  color: var(--accent-strong);
  font-size: 13.5px;
  font-style: italic;
  font-weight: 400;
}

.exp-note {
  color: var(--text-muted);
  font-weight: 400;
}

.exp-date {
  font-family: var(--mono);
  font-size: 12px;
  color: var(--text-muted);
  white-space: nowrap;
  margin-left: auto;
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

.exp-item-sub ul {
  margin: 0 0 8px 0;
  padding-left: 18px;
  color: var(--text-body);
}
</style>