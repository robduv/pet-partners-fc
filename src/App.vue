<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div
    class="mx-auto flex min-h-screen w-full max-w-7xl flex-col gap-4 bg-surface-50 p-4 dark:bg-surface-950"
  >
    <div
      class="rounded-xl border border-surface-200 bg-surface-0 p-4 text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
    >
      <AppHeader />
    </div>
    <div class="flex flex-1 flex-col gap-6">
      <RouterView />
    </div>
    <div
      class="rounded-xl border border-surface-200 bg-surface-0 p-4 text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
    >
      <AppFooter />
    </div>
  </div>
</template>
