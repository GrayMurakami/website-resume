<script setup lang="ts">
import { ref, onMounted } from 'vue'

interface Stat {
  label: string;
  target: number;
  suffix: string;
  display: string;
}

const stats = ref<Stat[]>([
  { 
    label: 'Professional frontend experience',
    target: 5,
    suffix: ' years',
    display: '0'
  },
  {
    label: '💻 Lines of code shipped',
    target: 222007,
    suffix: '+',
    display: '0'
  },
  {
    label: '☕ Coffee cups onboarded',
    target: 8007,
    suffix: '+',
    display: '0'
  },
]);

function animateCount(stat: Stat) {
  const duration = 1400;
  const start = performance.now();

  function tick(now: number) {
    const progress = Math.min((now - start) / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 3);
    const value = Math.floor(eased * stat.target);

    stat.display = value.toLocaleString('en-US') + stat.suffix;

    if (progress < 1) requestAnimationFrame(tick);
    else stat.display = stat.target.toLocaleString('en-US') + stat.suffix;
  }
  requestAnimationFrame(tick);
}

onMounted(() => {
  stats.value.forEach(animateCount);
});
</script>

<template>
  <div class="stats">
    <div
      v-for="stat in stats"
      :key="stat.label"
      class="stat-card"
    >
      <div class="stat-num">
        {{ stat.display }}
      </div>
      <div class="stat-label">
        {{ stat.label }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 14px;
  margin-top: 22px;
  margin-bottom: 26px;
}

.stat-card {
  border: 1px solid var(--card-border);
  border-radius: 8px;
  padding: 13px 22px;
  background: var(--card);
}

.stat-num {
  font-family: var(--mono);
  font-size: 22px;
  font-weight: 700;
  color: var(--accent-strong);
  font-variant-numeric: tabular-nums;
}

.stat-label {
  font-size: 11.5px;
  color: var(--text-muted);
  margin-top: 2px;
}

@media (max-width: 480px) {
  .stats {
    grid-template-columns: 1fr;
  }
}
</style>
