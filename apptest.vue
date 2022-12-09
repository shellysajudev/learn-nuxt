<template>
  <a href="#" @click="view('home')">Home</a>
  <a href="#" @click="view('counter')">Counter</a>
  <nuxt-page />
  <lazy-home-welcome v-if="page == 'home'" />
  <lazy-counter v-if="page == 'counter'" />
</template>

<script setup>
const page = ref('home');
function view(name) {
  page.value = name;
}
</script>