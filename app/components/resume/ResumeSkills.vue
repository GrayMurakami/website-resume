<script setup lang="ts">
interface SkillGroup {
  title: string;
  skills: readonly string[];
}

const skillGroups: readonly SkillGroup[] = [
  {
    title: 'frontend/',
    skills: [
      'Vue 3 (Composition API, composables)',
      'TypeScript',
      'JavaScript (ES6+)',
      'Pinia',
      'Vue Router',
      'Nuxt 4',
      'HTML5/CSS3',
      'SCSS',
      'Component architecture',
      'Responsive layout',
      'Forms & validation',
      'i18n',
      'PWA',
    ],
  },
  {
    title: 'backend & data/',
    skills: [
      'PHP 8',
      'WordPress (plugins, REST API)',
      'MySQL',
      'PostgreSQL (Supabase, RLS)',
      'Oracle',
      'REST API design',
    ],
  },
  {
    title: 'testing & quality/',
    skills: ['Vitest', 'Vue Test Utils', 'ESLint', 'Prettier', 'Code review'],
  },
  {
    title: 'devops & tools/',
    skills: [
      'Git/GitHub',
      'GitHub Actions',
      'Netlify (CI/CD)',
      'Vite',
      'npm',
      'Linux (RHEL)',
      'Bash',
      'AWS (infra/ops)',
    ],
  },
  {
    title: 'performance/',
    skills: ['Core Web Vitals', 'Lighthouse', 'Image optimization'],
  },
  {
    title: 'collaboration/',
    skills: ['Figma', 'Backlog', 'Technical docs (JP/EN)'],
  },
  {
    title: 'ai/',
    skills: ['Claude (refactoring, code review, tests, docs)'],
  },
];
</script>

<template>
  <div class="section-label">
    $ ls skills/
  </div>

  <div class="skills-grid">
    <section
      v-for="group in skillGroups"
      :key="group.title"
      class="skill-group"
    >
      <h3 class="skills-title">
        {{ group.title }}
      </h3>
      <div class="tag-row">
        <span
          v-for="skill in group.skills"
          :key="skill"
          class="tag"
        >
          {{ skill }}
        </span>
      </div>
    </section>
  </div>
</template>

<style scoped>
.skills-grid {
  column-count: 2;
  column-gap: 32px;
  margin-bottom: 26px;

  @media (max-width: 600px) {
    column-count: 1;
  }
}

.skill-group {
  break-inside: avoid;
  margin-bottom: 20px;
}

.skills-title {
  margin: 0 0 8px;
  font-size: inherit;
  font-weight: 600;
  color: var(--text-strong);
}
</style>