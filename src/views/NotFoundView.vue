<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <section class="flex flex-col gap-10 items-center py-16">
    <img src="@/assets/logo.svg" alt="" class="w-40" />
    <h1 class="text-3xl font-semibold">404 not found</h1>
    <h2 class="text-xl font-bold text-gray-600">The page likely doesn't exist</h2>

    <RouterLink to="/" class="bg-green-600 px-3 py-1 rounded-md text-white">Go back</RouterLink>
  </section>
</template>
