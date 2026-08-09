<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import emailIcon from '~/assets/icons/email.png';
import telegramIcon from '~/assets/icons/telegram.png';
import githubIcon from '~/assets/icons/github.png';
import linkedinIcon from '~/assets/icons/linkedin.png';

const dlBtn = ref<HTMLElement | null>(null);
const btnTransform = ref('translate(0, 0)');
const isPulsing = ref(true);

const MAGNET_RADIUS = 70;
const MAGNET_STRENGTH = 0.35;

function handleMouseMove(e: MouseEvent) {
  if (!dlBtn.value) return;

  const rect = dlBtn.value.getBoundingClientRect();
  const cx = rect.left + rect.width / 2;
  const cy = rect.top + rect.height / 2;
  const dx = e.clientX - cx;
  const dy = e.clientY - cy;
  const dist = Math.hypot(dx, dy);

  if (dist < MAGNET_RADIUS + rect.width / 2) {
    isPulsing.value = false;
    const pull = Math.max(0, 1 - dist / (MAGNET_RADIUS + rect.width));
    btnTransform.value = `translate(${dx * MAGNET_STRENGTH * pull}px, ${dy * MAGNET_STRENGTH * pull}px)`;
  } else {
    btnTransform.value = 'translate(0, 0)';
    isPulsing.value = true;
  }
}

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove);
});

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove);
});
</script>

<template>
  <div class="hero">
    <div class="hero-top">
      <div class="avatar-slot">
        photo
      </div>
      <div class="hero-main">
        <div class="prompt-label">
          $ whoami
        </div>
        <h1>
          Sergei Zuev
          <span class="cursor">
            _
          </span>
        </h1>
        <div class="role-line">
          &gt; Frontend Developer — Vue 3 / Nuxt 4
        </div>
        <div class="sub-line">
          JavaScript (ES6+) · TypeScript
        </div>
        <div class="sub-line">
          📍 Tokyo, Japan
        </div>
      </div>
    </div>

    <div class="hero-footer">
      <div class="contacts">
        <span>
          <img
            :src="emailIcon" 
            alt="" 
            class="contact-icon"
          />
            <a href="mailto:gray.frontend@gmail.com">
              gray.frontend@gmail.com
            </a>
        </span>
        <span>
          <img
            :src="telegramIcon" 
            alt="" 
            class="contact-icon"
          />
            <a 
              href="https://t.me/GraY_Murakami"
              target="_blank" 
              rel="noopener"
            >
              Telegram
            </a>
        </span>
        <span>
          <img 
            :src="githubIcon" 
            alt="" 
            class="contact-icon"
          />
            <a 
              href="https://github.com/GrayMurakami" 
              target="_blank" 
              rel="noopener"
            >
              Github.com
            </a>
        </span>
        <span>
          <img 
            :src="linkedinIcon" 
            alt="" 
            class="contact-icon"
          />
            <a 
              href="https://www.linkedin.com/in/sergei-zuev-4ab300286"
              target="_blank" 
              rel="noopener"
            >
              LinkedIn
            </a>
        </span>
      </div>
      <div class="dl-wrap">
        <a 
          ref="dlBtn"
          href="/sergei-zuev-resume.pdf"
          download
          class="dl-btn"
          :class="{ pulse: isPulsing }"
          :style="{ transform: btnTransform }"
        >
          ⬇️ Download PDF
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero {
  border: 1px solid var(--line);
  border-radius: 10px;
  padding: 28px 32px;
  background: oklch(1 0.004 90 / 0.65);
  margin-bottom: 26px;
}

.hero-top { 
  display: flex;
  flex-direction: row-reverse;
  align-items: flex-start;
  gap: 20px;
}

.avatar-slot {
  flex: none;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-top: 10px;
  margin-right: 14px;
  background: repeating-linear-gradient(135deg, oklch(0.93 0.02 148), oklch(0.93 0.02 148) 6px, oklch(0.88 0.03 148) 6px, oklch(0.88 0.03 148) 12px);
  border: 1px solid var(--card-border);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--mono);
  font-size: 9px;
  color: oklch(0.45 0.02 148);
  text-align: center;
  line-height: 1.3;
}

.hero-main { 
  flex: 1;
  min-width: 0;
}

.prompt-label { 
  font-family: var(--mono);
  color: var(--accent);
  font-size: 13px;
  margin-bottom: 10px;
}

h1 {
  font-family: var(--mono);
  font-size: 34px;
  font-weight: 700;
  margin: 0 0 6px 0;
  color: var(--text-strong);
  letter-spacing: -0.01em;
}

.cursor {
  color: var(--accent);
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  0%, 49% { 
    opacity: 1;
  }
  50%, 100% { 
    opacity: 0;
  }
}

.role-line { 
  font-family: var(--mono);
  font-size: 15px;
  font-weight: 500;
  color: var(--accent);
  margin-bottom: 10px;
}

.sub-line { 
  color: var(--text-muted);
  font-size: 13.5px;
}

.sub-line + .sub-line { 
  margin-top: 2px;
}

.hero-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 18px;
  padding-top: 16px;
  border-top: 1px dashed var(--line);
}

.contacts { 
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px 28px;
  font-size: 13.5px;
}

.contacts span { 
  color: var(--text-muted);
}

.contact-icon {
  width: 15px;
  height: 15px;
  object-fit: contain;
  vertical-align: -2px;
}

.dl-btn {
  position: relative;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--text-strong);
  color: oklch(0.98 0.004 90);
  font-family: var(--mono);
  font-size: 13px;
  font-weight: 600;
  padding: 12px 20px;
  border-radius: 999px;
  white-space: nowrap;
  cursor: pointer;
  border: none;
  text-decoration: none;
  transition: transform 0.15s ease-out;
}

.dl-btn.pulse {
  animation: pulse-glow 2.4s ease-in-out infinite;
}

@keyframes pulse-glow {
  0%, 100% { 
    box-shadow: 0 0 0 0 oklch(0.5 0.16 148 / 0.45);
  }
  50% { 
    box-shadow: 0 0 0 10px oklch(0.5 0.16 148 / 0);
  }
}

.dl-btn:active { 
  transform: scale(0.96);
}
</style>
