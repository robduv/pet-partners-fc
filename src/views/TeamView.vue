<script setup lang="ts">
import { ref } from 'vue'

const people = ref({
  key: '0',
  type: 'person',
  data: {
    image: '../../public/favicon.ico',
    name: 'River Rahe',
    title: 'CEO',
  },
  children: [
    {
      key: '0_0',
      type: 'person',
      data: {
        image: '../../public/favicon.ico',
        name: "Patti O'Keeffe",
        title: 'Evaluator',
      },
    },
    {
      key: '0_1',
      type: 'person',
      data: {
        image: '../../public/favicon.ico',
        name: 'Katy Rahe',
        title: 'Evaluator',
      },
    },
    {
      key: '0_2',
      type: 'person',
      data: {
        image: '../../public/favicon.ico',
        name: 'Jennifer Krasnow',
        title: 'Evaluator',
      },
    },
    {
      key: '0_3',
      type: 'person',
      data: {
        image: '../../public/favicon.ico',
        name: 'Rob Duval',
        title: 'Communications',
      },
    },
  ],
})
</script>

<template>
  <div
    class="flex flex-col gap-4 rounded-xl border border-surface-200 bg-surface-0 p-6 text-base text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
  >
    <div class="text-lg font-bold">Meet the Team</div>
    <OrganizationChart :value="people">
      <template #person="slotProps">
        <div class="flex flex-col">
          <div class="flex flex-col items-center">
            <img
              :alt="slotProps.node.data.name"
              :src="slotProps.node.data.image"
              class="mb-4 h-12 w-12"
            />
            <span class="mb-2 font-bold">{{ slotProps.node.data.name }}</span>
            <span>{{ slotProps.node.data.title }}</span>
          </div>
        </div>
      </template>
      <template #default="slotProps">
        <span>{{ slotProps.node.label }}</span>
      </template>
    </OrganizationChart>
  </div>
</template>
