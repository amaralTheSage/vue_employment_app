<script setup>
defineProps({
  title: {
    type: String,
  },
  subtitle: {
    type: String,
  },
  buttonText: {
    type: String,
  },
  colorScheme: {
    type: String,
    default: 'for-developers',
  },
})
</script>

<template>
  <div
    class="m-4 shadow-lg rounded-md [&>*]:my-2 p-3 bg-slate-100"
    :class="{ 'bg-green-200': colorScheme === 'for-employers' }"
  >
    <h3 class="text-xl font-bold">{{ title }}</h3>
    <p class="text-lg">{{ subtitle }}</p>
    <div class="w-fit ml-auto">
      <button
        class="bg-black text-white mt-2 p-2 px-3 rounded-md"
        :class="{ 'bg-green-600': colorScheme === 'for-employers' }"
      >
        {{ buttonText }}
      </button>
    </div>
  </div>
</template>
