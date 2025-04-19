<script setup lang="ts">
import { ref } from 'vue'

const events = ref([
  { id: 1, type: 'Team Evaluation', date: '2025-05-03' },
  { id: 2, type: 'Team Evaluation', date: '2025-06-07' },
])
</script>

<template>
  <div class="grid grid-cols-1 gap-4 md:grid-cols-2">
    <div
      class="flex flex-col gap-4 rounded-xl border border-surface-200 bg-surface-0 p-6 text-base text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
    >
      <div class="text-md text-base text-surface-600 dark:text-surface-400">
        <div class="text-lg font-bold">Welcome!</div>
        <span class="font-bold">Pet Partners of Fairfield County</span> is a group of active
        registered Pet Partners teams that reside in Fairfield County, CT. We support members, aim
        to improve physical and mental health, and foster the human-animal bond through visits,
        networking, and mentoring.
      </div>
    </div>
    <div
      class="flex flex-col gap-4 rounded-xl border border-surface-200 bg-surface-0 p-6 text-base text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
    >
      <div class="flex items-center justify-between">
        <span class="text-lg font-bold">Upcoming Events</span>
      </div>
      <div class="flex items-center justify-between">
        <span class="text-md">
          <ul>
            <li v-for="event in events" :key="event.id">
              <span class="font-bold">{{ event.date }}</span
              ><span>: {{ event.type }}</span>
            </li>
          </ul>
        </span>
      </div>
    </div>
  </div>
</template>
