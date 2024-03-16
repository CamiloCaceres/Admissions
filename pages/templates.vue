<template>
    <div>
      <UHeading tag="h2" weight="bold" size="3xl" class="mb-4">Browse Templates</UHeading>
      <UGrid class="gap-4">
        <UGridItem v-for="(template, index) in templates" :key="index" :colspan="{ base: 6, md: 4, lg: 3 }">
          <div class="flex flex-row items-center">
            <UHeading tag="h3" weight="semibold" size="xl" class="mb-2">{{ template.name }}</UHeading>
            <div class="flex space-x-2">
              <UButton color="primary" @click="showModal(template)">View Template</UButton>
              <UButton color="primary" @click="copyToClipboard(template.content)">Copy to Clipboard</UButton>
            </div>
          </div>
        </UGridItem>
      </UGrid>
  
      <UModal v-model="showingModal" :title="selectedTemplate?.name" :footer="false">
        <UModalBody>
          <pre class="bg-gray-100 p-4 rounded-md">{{ selectedTemplate?.content }}</pre>
          <span v-if="selectedTemplate">
            <UButton color="primary" @click="copyToClipboard(selectedTemplate.content)">Copy to Clipboard</UButton>
        </span>

        </UModalBody>
      </UModal>
    </div>
  </template>
  
  <script setup lang="ts">
  import { useClipboard } from '@vueuse/core'
  import { ref } from 'vue'
  
  interface Template {
    id: number
    name: string
    content: string
  }
  
  const { copy } = useClipboard()
  const showingModal = ref(false)
  const selectedTemplate = ref<Template | null>(null)
  
  const templates: Template[] = [
    {
      id: 1,
      name: 'Template 1',
      content: `
  # Template 1
  This is the content of Template 1.
  You can copy this template to the clipboard.
      `
    },
    {
      id: 2,
      name: 'Template 2',
      content: `
  # Template 2
  This is the content of Template 2.
  You can also copy this template to the clipboard.
      `
    },
    // Add more templates as needed
  ]
  
  const copyToClipboard = (content: string) => {
    copy(content)
    alert('Content copied to clipboard!')
  }
  
  const showModal = (template: Template) => {
    selectedTemplate.value = template
    showingModal.value = true
  }
  </script>