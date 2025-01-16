<script setup>
import { onMounted, ref } from 'vue'
import JobListing from './JobListing.vue'
import axios from 'axios'

const jobs = ref([])

onMounted(async () => {
  try {
    // Api route set in vite.config.js
    const jobData = await axios.get('api/jobs')
    jobs.value = jobData.data
  } catch {
    console.error('Error fetching the jobs')
  }
})

defineProps({
  limit: { type: Number, default: 12 },
  showButton: { default: false, type: Boolean },
})
</script>

<template>
  <section class="bg-green-50 px-4 py-10 md:px-16">
    <div class="container-xl lg:container m-auto">
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">Browse Jobs</h2>
    </div>

    <ul class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <JobListing v-for="job in jobs.splice(0, limit || jobs.length)" :key="job.id" :job="job" />
    </ul>
  </section>

  <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">
    <RouterLink
      to="/jobs"
      class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700"
      >View All Jobs</RouterLink
    >
  </section>
</template>
