<script setup lang="ts">
const certifications: readonly string[] = [
  'JLPT N1',
  'HTML5 Professional Level 1 & 2',
  'LPIC Level 1',
  'PHP8 Certification',
  'Oracle Master Bronze DBA',
  'LanguageCert ESOL B2',
];
</script>

<template>
  <div class="section-label">
    $ cat certifications.txt
  </div>

  <div class="tag-row certifications">
    <span
      v-for="cert in certifications"
      :key="cert"
      class="tag"
    >
      {{ cert }}
    </span>
  </div>
</template>

<style scoped>
.certifications {
  margin-bottom: 26px;
}
</style>