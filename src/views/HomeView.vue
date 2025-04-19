<script setup lang="ts">
import { ref } from 'vue'

const events = ref([
  { id: 1, icon: 'pi-list-check', name: 'Team Evaluation', time: '2025-05-03' },
  { id: 2, icon: 'pi-list-check', name: 'Team Evaluation', time: '2025-06-07' },
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
      <div class="flex flex-col gap-3">
        <div
          v-for="(event, index) in events"
          :key="index"
          class="flex items-center gap-3 rounded-lg border border-surface-200 bg-surface-50 p-3 dark:border-surface-700 dark:bg-surface-800"
        >
          <i :class="['pi', event.icon, 'text-lg!']"></i>
          <div class="flex flex-col gap-1">
            <span class="text-sm font-medium">{{ event.name }}</span>
            <span class="text-xs text-surface-600 dark:text-surface-400">{{ event.time }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
