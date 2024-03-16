<template>
    <div>
      <UPageGrid>
        <UPageGridItem v-for="item in items" :key="item.id">
          <UCard>
            <UCardHeader>
              <UHeading tag="h3" weight="semibold">{{ item.title }}</UHeading>
            </UCardHeader>
            <UCardBody>
              <UButton color="primary" @click="openModal(item)">View Checklist</UButton>
            </UCardBody>
          </UCard>
        </UPageGridItem>
      </UPageGrid>
  
      <UModal v-model="showModal" :title="selectedItem?.title" :footer="false">
        <UModalBody>
          <ul>
            <li v-for="(checkItem, index) in selectedItem?.checklist" :key="index" class="flex justify-between">
                <span>{{ checkItem.text }}</span>
              <UCheckbox v-model="checkItem.checked" />
            </li>
          </ul>
        </UModalBody>
      </UModal>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue'
  
  interface CheckItem {
    text: string
    checked: boolean
  }
  
  interface Item {
    id: number
    title: string
    checklist: CheckItem[]
  }
  
  const showModal = ref(false)
  const selectedItem = ref<Item | null>(null)
  
  const items: Item[] = [
    {
      id: 1,
      title: 'Task 1',
      checklist: [
        { text: 'Complete report', checked: false },
        { text: 'Submit expense report', checked: false },
        { text: 'Attend team meeting', checked: false },
      ],
    },
    {
      id: 2,
      title: 'Task 2',
      checklist: [
        { text: 'Review project plan', checked: false },
        { text: 'Update project timeline', checked: false },
        { text: 'Assign tasks to team members', checked: false },
      ],
    },
    {
      id: 3,
      title: 'Task 3',
      checklist: [
        { text: 'Prepare presentation', checked: false },
        { text: 'Schedule client meeting', checked: false },
        { text: 'Follow up with stakeholders', checked: false },
      ],
    },
  ]
  
  const openModal = (item: Item) => {
    selectedItem.value = item
    showModal.value = true
  }
  </script>