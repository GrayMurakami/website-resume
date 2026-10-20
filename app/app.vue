
<template>
  <div class="page">
    <div class="titlebar">
      <span class="dot red"></span>
      <span class="dot yellow"></span>
      <span class="dot green"></span>
      <span class="titlebar-label">
        sergei@zuev:~/resume — zsh
      </span>
    </div>
    <ResumeHero />
    <div class="section-label">
      $ cat summary.md
    </div>
    <p class="summary">
      Five years of frontend development: from building UI in vanilla JavaScript for an early-stage LegalTech SaaS 
      to modernizing a legacy WordPress/PHP corporate portal with Vue 3 and TypeScript – 70 of 90 pages migrated so far, 
      without disrupting the live site. There's a particular satisfaction in dropping a Vue 3 component into a stack that's never seen one and watching it not break anything. 
      Alongside this, I'm on a client assignment at Hewlett Packard Enterprise, working in enterprise production environments under strict change management.
    </p>
    <p class="summary">
      Focused on growing as a Vue developer: going deeper into Vue 3 and Nuxt 4 rather than spreading across frameworks. 
      Looking for a product team with room to grow technically.  
    </p>
    <ResumeStats />
      <div class="rule"></div>
    <ResumeSkills />
      <div class="rule"></div>
    <ResumeProjects />
      <div class="rule"></div>
    <ResumeExperience />
      <div class="rule"></div>
    <ResumeEducation />
      <div class="rule"></div>
    <ResumeLanguages />
  </div>
</template>

<style scoped>
.page {
  max-width: 794px; /* A4 @ 96dpi */
  margin: 32px auto;
  padding: 44px 52px 48px 52px;
  background:
    radial-gradient(circle at 12% 6%, oklch(0.9 0.05 148 / 0.5), transparent 42%),
    radial-gradient(circle at 92% 88%, oklch(0.88 0.05 148 / 0.4), transparent 45%),
    repeating-linear-gradient(0deg, oklch(0 0 0 / 0.012) 0px, oklch(0 0 0 / 0.012) 1px, transparent 1px, transparent 28px),
    var(--paper);
  border-radius: 14px;
  box-shadow: 0 30px 60px -20px oklch(0.2 0.02 148 / 0.25);
}

.titlebar { 
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 22px;
}

.dot { width: 11px;
  height: 11px;
  border-radius: 50%;
}

.dot.red { 
  background: oklch(0.7 0.16 25);
}

.dot.yellow { 
  background: oklch(0.8 0.14 90);
}

.dot.green { 
  background: oklch(0.78 0.19 148);
}

.titlebar-label { 
  font-family: var(--mono);
  font-size: 12.5px;
  color: var(--text-muted);
  margin-left: 10px;
}
</style>