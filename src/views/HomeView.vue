<script setup>
import HeroComponent from '@/components/HeroComponent.vue'
import HomeCards from '@/components/HomeCards.vue'
import JobsListing from '@/components/JobsListing.vue'
</script>

<template>
  <HeroComponent />
  <section class="md:flex justify-center my-4">
    <HomeCards
      title="For Developers"
      subtitle="Browse our Vue jobs and start your career today"
      button-text="Browse Jobs"
    />
    <HomeCards
      title="For Employers"
      subtitle="List your job to find the perfect developer for the role"
      button-text="Add Jobs"
      color-scheme="for-employers"
    />
  </section>
  <JobsListing :limit="3" :show-button="true" />
</template>
