<template>
  <div class="bg-[#f8f8f8] h-screen">
    <NavbarMain />
    <div class="flex justify-between mx-auto w-full px-2 max-w-[1140px]">
      <slot />
    </div>
  </div>
</template>

<script setup>
const route = useRoute();
</script>
