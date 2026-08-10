
<template>
  <div class="section-label">
    $ cat education.log
  </div>
  <div class="edu-item">
    <div>
      <div class="edu-title">
        Specialist Degree, Physics and Informatics
      </div>
      <div class="edu-org">
        Birsk Branch of Bashkir State University · Russia
      </div>
    </div>
    <div class="edu-date">
      5-year program
    </div>
  </div>
</template>

<style scoped>
.edu-item {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 12px;
  flex-wrap: wrap;
  margin-bottom: 8px;
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
