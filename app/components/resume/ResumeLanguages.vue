<script setup lang="ts">
import { ref, onMounted } from 'vue'

interface LangRing {
  name: string;
  level: string;
  targetDeg: number;
  track: string;
  native: boolean;
  deg: number;
}

const langs = ref<LangRing[]>([
  {
    name: 'Russian',
    level: 'native',
    targetDeg: 360,
    track: 'transparent',
    native: true,
    deg: 0
  },
  {
    name: 'English',
    level: 'B2',
    targetDeg: 252,
    track: 'oklch(0.88 0.02 148)',
    native: false,
    deg: 0
  },
  {
    name: 'Japanese',
    level: 'JLPT N1',
    targetDeg: 360,
    track: 'transparent',
    native: false,
    deg: 0
  },
]);

function ringBackground(lang: LangRing): string {
  return `conic-gradient(oklch(0.5 0.16 148) ${lang.deg}deg, ${lang.track} ${lang.deg}deg)`;
}

function animateRing(lang: LangRing) {
  const duration = 1600;
  const start = performance.now();

  function tick(now: number) {
    const progress = Math.min((now - start) / duration, 1);
    const eased = 1 - Math.pow(1 - progress, 3);

    lang.deg = eased * lang.targetDeg;
    if (progress < 1) requestAnimationFrame(tick);
  }
  requestAnimationFrame(tick);
}

onMounted(() => {
  langs.value.forEach(animateRing);
});
</script>

<template>
  <div class="section-label">
    $ cat languages.json
  </div>
  <div class="langs">
    <div
      v-for="lang in langs" 
      :key="lang.name"
      class="lang-item"
    >
      <div
        class="lang-outer"
        :class="{ active: lang.native }"
        :style="{ background: ringBackground(lang) }"
      >
        <div class="lang-inner">
          <div class="lang-name">
            {{ lang.name }}
          </div>
          <div class="lang-level">
            {{ lang.level }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.langs {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin-bottom: 8px;
}

.lang-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.lang-outer {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  padding: 4px;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: center;
}

.lang-outer.native {
  box-shadow: 0 0 0 3px var(--paper), 0 0 0 4px oklch(0.35 0.12 148);
}

.lang-inner {
  width: 78px;
  height: 78px;
  border-radius: 50%;
  background: var(--paper);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.lang-name {
  font-family: var(--mono);
  font-weight: 700;
  font-size: 12.5px;
  color: var(--text-strong);
}

.lang-level {
  font-size: 10.5px;
  color: var(--text-muted);
}
</style>
