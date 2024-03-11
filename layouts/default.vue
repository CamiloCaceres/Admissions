<script setup lang="ts">
const links = [{
  label: 'Notes',
  icon: 'i-heroicons-pencil-square-solid',
  to: '/notes'
}, {
  label: 'Playground',
  icon: 'i-simple-icons-stackblitz',
  to: '/playground'
}, {
  label: 'Roadmap',
  icon: 'i-heroicons-map',
  to: '/roadmap'
}, {
  label: 'Pro',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '/pro'
}, {
  label: 'Releases',
  icon: 'i-heroicons-rocket-launch',
  to: 'https://github.com/nuxt/ui/releases',
  target: '_blank'
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
