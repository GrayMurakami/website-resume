<script setup lang="ts">
interface EducationItem {
  title: string;
  org: string;
  date: string;
}

const education: readonly EducationItem[] = [
  {
    title: 'Specialist Degree, Physics and Informatics',
    org: 'Birsk Branch of Bashkir State University · Russia · 5-year program',
    date: '2009–2014',
  },
  {
    title: "Bachelor's Degree, Radiophysics and Electronics",
    org: 'Birsk Branch of Bashkir State University · Russia',
    date: '2012–2014',
  },
  {
    title: 'Japanese Language Program',
    org: 'Aoyama International Education Institute · Tokyo',
    date: '2018–2019',
  },
];
</script>

<template>
  <div class="section-label">
    $ cat education.log
  </div>
  <div class="edu-list">
    <div
      v-for="item in education"
      :key="item.title"
      class="edu-item"
    >
      <div>
        <div class="edu-title">
          {{ item.title }}
        </div>
        <div class="edu-org">
          {{ item.org }}
        </div>
      </div>
      <div class="edu-date">
        {{ item.date }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.edu-list {
  display: grid;
  gap: 16px;
  margin-bottom: 26px;
}

.edu-item {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 12px;
  flex-wrap: wrap;
}

.edu-title {
  font-weight: 600;
  font-size: 15px;
  color: var(--text-strong);
}

.edu-org {
  color: var(--accent-strong);
  font-size: 13.5px;
}

.edu-date {
  font-family: var(--mono);
  font-size: 12px;
  color: var(--text-muted);
  white-space: nowrap;
}
</style>