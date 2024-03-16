<template>
    <div>
      <UCard>
        <UCardHeader>
          <UHeading tag="h2" weight="bold">Reminders</UHeading>
        </UCardHeader>
        <UCardBody>
          <div class="grid grid-cols-2 gap-4">
            <div>
              <UHeading tag="h3" size="lg" weight="semibold">Daily Reminders</UHeading>
              <ul class="list-disc pl-4">
                <li v-for="reminder in dailyReminders" :key="reminder.id">{{ reminder.text }}</li>
              </ul>
            </div>
            <div>
              <UHeading tag="h3" size="lg" weight="semibold">Weekly Reminders</UHeading>
              <ul class="list-disc pl-4">
                <li v-for="reminder in weeklyReminders" :key="reminder.id">{{ reminder.text }}</li>
              </ul>
            </div>
          </div>
        </UCardBody>
      </UCard>
    </div>
  </template>
  
  <script setup lang="ts">
  
  interface Reminder {
    id: number
    text: string
  }
  
  const dailyReminders: Reminder[] = [
    { id: 1, text: 'Check email for new tasks' },
    { id: 2, text: 'Review project timeline' },
    { id: 3, text: 'Follow up with team members' },
  ]
  
  const weeklyReminders: Reminder[] = [
    { id: 1, text: 'Prepare weekly report' },
    { id: 2, text: 'Schedule team meeting' },
    { id: 3, text: 'Review project progress' },
  ]
  </script>