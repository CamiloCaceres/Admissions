<script setup lang="ts">
const selectedTrimester = ref()
const courseCode = ref('MITA21')

</script>

<template>
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

</template>