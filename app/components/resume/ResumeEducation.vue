<script setup lang="ts">
interface EducationItem {
  title: string;
  org: string;
  date: string;
}

const education: readonly EducationItem[] = [
  {
    title: 'Specialist Degree, Physics and Informatics',
    org: 'Birsk Branch of Bashkir State University · Russia',
    date: '2009–2014 · 5-year program',
  },
  {
    title: "Bachelor's Degree, Radiophysics and Electronics",
    org: 'Birsk Branch of Bashkir State University · Russia',
    date: '2012-2014',
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
</template>