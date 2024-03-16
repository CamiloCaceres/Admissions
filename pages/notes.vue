<script setup lang="ts">
const selectedTrimester = ref()
const courseCode = ref('MITA21')


const formData = reactive({
  courseName: '',
  campus: '',
  intake: '',
  certifiedPassport: false,
  visaExpiryDate: '',
  ct: '',
  scholarship: '',
  gte: '',
  oshc: '',
  condition: ''
})

</script>

<template>
  <UCard>

    <h2 class="text-xl font-semibold">Academic notes</h2>
    <div class="flex space-x-5">
      <div class="flex space-x-5"> <span>Trimester: </span>
        <UInput v-model="selectedTrimester" />
      </div>
      <div class="flex space-x-5"><span>Course</span>
        <UInput v-model="courseCode" /> 
      </div>
    </div>


    <span>Completed</span> <input type="text" name="YEARS" id=""> <span>Years of</span> <input type="text"
      name="COURSE_COMPLETED" id="">
    <span>at </span> <input type="text" name="COLLEGUE">
  </UCard>
  <UCard>
    <template>
  <div>
    <div>
      <label for="courseName">Course Name:</label>
      <UInput id="courseName" v-model="formData.courseName" type="text" />
    </div>
    <div>
      <label for="campus">Campus:</label>
      <UInput id="campus" v-model="formData.campus" type="text" />
    </div>
    <div>
      <label for="intake">Intake:</label>
      <UInput id="intake" v-model="formData.intake" type="text" />
    </div>

    <div>
      <label for="certifiedPassport">Certified Passport:</label>
      <UInput id="certifiedPassport" v-model="formData.certifiedPassport" type="checkbox" />
    </div>
    <div>
      <label for="visaExpiryDate">Visa/Expiry Date:</label>
      <UInput id="visaExpiryDate" v-model="formData.visaExpiryDate" type="date" />
    </div>
    <div>
      <label for="ct">CT:</label>
      <UInput id="ct" v-model="formData.ct" type="text" />
    </div>
    <div>
      <label for="scholarship">Scholarship:</label>
      <UInput id="scholarship" v-model="formData.scholarship" type="text" />
    </div>
    <div>
      <label for="gte">GTE:</label>
      <UInput id="gte" v-model="formData.gte" type="text" />
    </div>
    <div>
      <label for="oshc">OSHC:</label>
      <UInput id="oshc" v-model="formData.oshc" type="text" />
    </div>
    <div>
      <label for="condition">Condition:</label>
      <UInput id="condition" v-model="formData.condition" type="text" />
    </div>
  </div>
</template>
  </UCard>

</template>