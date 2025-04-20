<script setup lang="ts">
import { format } from 'date-fns'
import ActionButton from './ActionButton.vue'

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
        {{ event.name }}
      </div>
      <div class="flex flex-col">
        <span>{{ format(event.date, 'PPp') }}</span>
        <span>{{ event.location.name }}</span>
        <div class="flex gap-1">
          <ActionButton
            v-if="event.signupFormUrl"
            :url="event.signupFormUrl"
            label="Volunteer"
            icon="pi pi-user-plus"
          />
          <ActionButton
            :url="event.location.directionsUrl"
            label="Directions"
            icon="pi pi-directions"
          />
          <ActionButton
            v-if="event.eventSiteUrl"
            :url="event.eventSiteUrl"
            label="Info"
            icon="pi pi-info-circle"
          />
        </div>
      </div>
    </div>
  </div>
</template>
