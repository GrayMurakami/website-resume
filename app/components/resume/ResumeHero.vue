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
    btnTransform.value = `translate(${dx * MAGNET_STRENGTH * pull}px, ${dy * MAGNET_STRENGTH * pull}dx)`;
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
          Zuev Sergei
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
          href="/zuev-sergei-resume.pdf"
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

</style>