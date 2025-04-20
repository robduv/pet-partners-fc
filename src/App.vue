<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="flex min-h-screen flex-col gap-6 bg-surface-50 p-6 dark:bg-surface-950">
    <AppHeader />
    <div class="mx-auto flex w-full max-w-7xl flex-1 flex-col gap-6">
      <RouterView />
    </div>
    <AppFooter />
  </div>
</template>
