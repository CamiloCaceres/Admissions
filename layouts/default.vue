<script setup lang="ts">
const links = [{
  label: 'Notes',
  icon: 'i-heroicons-pencil-square-solid',
  to: '/notes'
}, {
  label: 'Templates',
  icon: 'i-simple-icons-stackblitz',
  to: '/templates'
}, {
  label: 'Conditions',
  icon: 'i-heroicons-map',
  to: '/conditions'
}, {
  label: 'Step by Step',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro'
}, {
  label: 'Checklists',
  icon: 'i-heroicons-rocket-launch',
  to: '/checklist',
}]


</script>

<template>
  <UHeader>
    <template #logo>
      <h1><span class="text-orange-500 ">T</span>Wiki</h1>
    </template>
    <template #right>
      <UColorModeButton />
    </template>
  </UHeader>

  <UContainer>
    <UPage>
      <template #left>
        <UAside :links="links">

        </UAside>
      </template>

      <slot />
    </UPage>
  </UContainer>
</template>
