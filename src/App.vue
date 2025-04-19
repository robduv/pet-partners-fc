<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="flex min-h-screen flex-col gap-6 bg-surface-50 p-8 dark:bg-surface-950">
    <AppHeader />
    <div class="grid grid-cols-1 gap-6 md:grid-cols-2">
      <RouterView />
    </div>
    <AppFooter />
  </div>
</template>
