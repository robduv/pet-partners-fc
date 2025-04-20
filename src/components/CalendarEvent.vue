<script setup lang="ts">
import { format } from 'date-fns'

export interface CalendarEventLocation {
  name: string
  directionsUrl: string
}

export interface CalendarEventProps {
  icon: string
  name: string
  color: string
  url?: string
  date: Date
  location: CalendarEventLocation
}

const event = defineProps<CalendarEventProps>()
</script>

<template>
  <div
    class="flex items-center gap-3 rounded-lg border border-surface-200 bg-surface-50 p-3 dark:border-surface-700 dark:bg-surface-800"
  >
    <i :class="['pi', event.icon, event.color, 'text-lg!']"></i>
    <div class="flex flex-col gap-1">
      <div class="text-base font-bold">
        <a v-if="event.url" target="_blank" :href="event.url">{{ event.name }}</a
        ><span v-else>{{ event.name }}</span>
      </div>
      <div class="text-sm text-surface-600 dark:text-surface-400">
        <div>{{ format(event.date, 'PPp') }}</div>
        <div>
          <a target="_blank" :href="event.location.directionsUrl"
            >{{ event.location.name }}<i class="pi pi-directions m-1"></i
          ></a>
        </div>
      </div>
    </div>
  </div>
</template>
