<script setup lang="ts">
import { format } from 'date-fns'

export interface CalendarEventLocation {
  name: string
  directionsUrl: string
}

export interface CalendarEventProps {
  icon: string
  color: string
  name: string
  date: Date
  location: CalendarEventLocation
  eventSiteUrl?: string
  signupFormUrl?: string
}

const event = defineProps<CalendarEventProps>()
</script>

<template>
  <div
    class="flex items-center gap-3 rounded-lg border border-surface-200 bg-surface-50 p-3 dark:border-surface-700 dark:bg-surface-800"
  >
    <i :class="['pi', event.icon, event.color, 'text-lg!']"></i>
    <div class="flex flex-col text-sm">
      <div class="text-base font-bold">
        <a v-if="event.eventSiteUrl" target="_blank" :href="event.eventSiteUrl">{{ event.name }}</a
        ><span v-else>{{ event.name }}</span>
      </div>
      <div class="flex flex-col">
        <span>{{ format(event.date, 'PPp') }}</span>
        <a target="_blank" :href="event.location.directionsUrl">{{ event.location.name }}</a>
        <a v-if="event.signupFormUrl" target="_blank" :href="event.signupFormUrl">Volunteer</a>
      </div>
    </div>
  </div>
</template>
