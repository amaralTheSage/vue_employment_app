<script setup>
import logo from '@/assets/logo.svg'
import { useRoute } from 'vue-router'

const isActiveLink = (routePath) => {
  const route = useRoute()

  return routePath === route.path
}
</script>

<template>
  <header class="flex justify-between items-center p-4 md:px-16 shadow-sm">
    <RouterLink to="/">
      <img v-bind:src="logo" alt="logo" class="w-10" />
    </RouterLink>

    <nav class="[&>*]:mx-1">
      <RouterLink
        to="/"
        class="hover:bg-black hover:bg-opacity-75 rounded-md hover:text-white px-3 pb-[4.5px] pt-1 duration-100"
        :class="{ 'bg-black bg-opacity-75 hover:bg-opacity-100 text-white': isActiveLink('/') }"
        >Home</RouterLink
      >
      <RouterLink
        to="/jobs"
        class="hover:bg-black hover:bg-opacity-75 rounded-md hover:text-white px-3 pb-[4.5px] pt-1 duration-100"
        :class="{ 'bg-black bg-opacity-75 hover:bg-opacity-100 text-white': isActiveLink('/jobs') }"
        >Jobs</RouterLink
      >
      <RouterLink
        to="/jobs/add"
        class="hover:bg-black hover:bg-opacity-75 rounded-md hover:text-white px-3 pb-[4.5px] pt-1 duration-100"
        :class="{
          'bg-black bg-opacity-75 hover:bg-opacity-100 text-white': isActiveLink('/jobs/add'),
        }"
        >Add Jobs</RouterLink
      >
    </nav>
  </header>
</template>
