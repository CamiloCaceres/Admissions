<template>
    <div>
      <UHeading tag="h2" weight="bold" size="3xl" class="mb-4">Select Conditions</UHeading>
      <div>
        <div v-for="condition in conditions" :key="condition.id" class="flex items-center justify-between py-2">
          <UHeading tag="h3" size="md" weight="medium">{{ condition.name }}</UHeading>
          <UCheckbox v-model="condition.checked" class="ml-4" />
        </div>
      </div>
      <div class="mt-4">
        <UButton color="primary" @click="generateConditions">Generate Conditions</UButton>
      </div>
      <UModal v-model="showingConditions" title="Generated Conditions" :footer="false">
        <UModalBody>
          <div v-if="selectedConditions.length > 0">
            <p>This offer is conditional upon:</p>
            <ul>
              <li v-for="condition in selectedConditions" :key="condition.id">{{ condition.name }}</li>
            </ul>
            <UButton color="secondary" class="mt-4" @click="copyToClipboard">Copy to Clipboard</UButton>
          </div>
          <p v-else>No conditions selected.</p>
        </UModalBody>
      </UModal>
    </div>
  </template>
  
  <script setup lang="ts">
import { conditions, type Condition } from '@/utils/conditions';
  import { useClipboard } from '@vueuse/core'
  

  
  const { copy } = useClipboard()
  const showingConditions = ref(false)
  

  
  const selectedConditions = ref<Condition[]>([])
  
  const generateConditions = () => {
    selectedConditions.value = conditions.filter(condition => condition.checked)
    showingConditions.value = true
  }
  
  const copyToClipboard = () => {
    const conditionsList = selectedConditions.value.map(condition => condition.name).join(', ')
    const text = `This offer is conditional upon: ${conditionsList}`
    copy(text)
    alert('Conditions copied to clipboard!')
  }
  </script>