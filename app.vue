<template>
  <NuxtPage />

  <AuthOverlay v-if="$generalStore.isLoginOpen" />
</template>

<script setup>
const { $generalStore } = useNuxtApp();
</script>
