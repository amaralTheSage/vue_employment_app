<script setup>
defineProps({
  title: {
    type: String,
    default: 'Become a Vue Dev',
  },
  subtitle: {
    type: String,
    default: 'Find the Vue job that fits your skills and needs',
  },
})
</script>

<template>
  <section class="bg-green-400 text-white text-center py-[20vh]">
    <h1 class="text-4xl font-bold mb-2">
      {{ title }}
    </h1>
    <h2 class="text-xl font-semibold">{{ subtitle }}</h2>
  </section>
</template>
