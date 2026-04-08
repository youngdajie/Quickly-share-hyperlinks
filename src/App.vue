<!-- src/App.vue -->
<template>
  <div class="container">
    <div class="header">
      <h1>{{ config.title }}</h1>
      <div
        class="theme-toggle"
        :class="{ dark: isDark }"
        @click="toggleTheme"
        aria-label="切换主题"
      ></div>
    </div>
    <p>{{ config.subtitle }}</p>

    <div class="links">
      <a
        v-for="(link, index) in config.links"
        :key="index"
        :href="link.href"
        target="_blank"
        rel="noopener noreferrer"
        class="link"
      >
        <img
          :src="link.img"
          :alt="link.alt"
          class="link-image"
          loading="lazy"
        />
        <div class="link-content">
          <div class="link-title">{{ link.title }}</div>
          <div class="link-desc">{{ link.desc }}</div>
        </div>
      </a>
    </div>

    <div class="social-links">
      <a
        v-for="(social, index) in config.socialLinks"
        :key="index"
        :href="social.href"
        :title="social.label"
        target="_blank"
        rel="noopener noreferrer"
        class="social-link"
      >
        <i :class="'fa ' + social.icon"></i>
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { siteConfig } from './siteConfig.js';

const config = siteConfig;
const isDark = ref(false);

function toggleTheme() {
  isDark.value = !isDark.value;
  document.body.classList.toggle('dark-mode', isDark.value);
  localStorage.setItem('theme', isDark.value ? 'dark' : 'light');
}

onMounted(() => {
  // 初始化主题
  const savedTheme = localStorage.getItem('theme');
  const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;

  if (savedTheme === 'dark' || (!savedTheme && prefersDark)) {
    isDark.value = true;
    document.body.classList.add('dark-mode');
  }
});
</script>