<script lang="ts" setup>
import HelloWorld from "./components/HelloWorld.vue";
import container from "./components/container.vue";
</script>

<template>
  <div class="bg bg-tl"></div>
  <div class="bg bg-tl2"></div>
  <container />
  <HelloWorld />
  <div class="bg bg-br"></div>
  <div class="mail">
    <a href="mailto:amazyko@foxmail.com" target="_blank">
      <svg
        fill="none"
        height="24"
        stroke="currentColor"
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        viewBox="0 0 24 24"
        width="24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <rect height="16" rx="2" ry="2" width="18" x="3" y="4"></rect>
        <polyline points="3,4 12,13 21,4"></polyline>
      </svg>
    </a>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
