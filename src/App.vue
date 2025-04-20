<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="flex min-h-screen flex-col gap-6 bg-surface-50 p-6 dark:bg-surface-950">
    <div
      class="mx-auto w-full max-w-7xl rounded-xl border border-surface-200 bg-surface-0 p-6 text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
    >
      <AppHeader />
    </div>
    <div class="mx-auto flex w-full max-w-7xl flex-1 flex-col gap-6">
      <RouterView />
    </div>
    <div
      class="mx-auto w-full max-w-7xl rounded-xl border border-surface-200 bg-surface-0 p-6 dark:border-surface-700 dark:bg-surface-900"
    >
      <AppFooter />
    </div>
  </div>
</template>
