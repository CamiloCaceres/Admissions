<script setup lang="ts">

const selectedTrimester = ref()
const courseCode = ref('MITA21')


</script>

<template>
  <UContainer>
    <UCard class="mt-10">
      <template #header>
        <div class="flex justify-between">
          <h1>Welcome to Nuxt UI Starter</h1>
          <ColorScheme>
            <USelect v-model="$colorMode.preference" :options="['system', 'light', 'dark']" />
          </ColorScheme>
        </div>
      </template>


      <UButton icon="i-heroicons-book-open" to="https://ui.nuxt.com" target="_blank">Open Nuxt UI Documentation</UButton>
    </UCard>
    <UCard>
      <h2 class="text-xl font-semibold">Academic notes</h2>
      <div class="flex space-x-5">
        <div class="flex space-x-5"> <span>Trimester: </span>
          <UInput v-model="selectedTrimester" />
        </div>
        <div class="flex space-x-5"><span>Course</span> <UInput v-model="courseCode" /> </div>
      </div>


      <span>Completed</span> <input type="text" name="YEARS" id=""> <span>Years of</span> <input type="text"
        name="COURSE_COMPLETED" id="">
      <span>at </span> <input type="text" name="COLLEGUE">
  </UCard>
</UContainer></template>
