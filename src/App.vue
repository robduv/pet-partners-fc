<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="bg-surface-50 dark:bg-surface-950 min-h-screen p-8 flex flex-col gap-6">
    <AppHeader />
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <RouterView />
    </div>
    <AppFooter />
  </div>
</template>
