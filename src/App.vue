<script setup lang="ts">
import { RouterView } from 'vue-router'
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="mx-auto flex min-h-screen w-full max-w-7xl flex-col gap-4 bg-slate-50 p-4">
    <div class="rounded-xl border border-slate-300 bg-white p-4 text-slate-700">
      <AppHeader />
    </div>
    <div class="flex flex-1 flex-col gap-6">
      <RouterView />
    </div>
    <div class="rounded-xl border border-slate-300 bg-white p-4 text-slate-700">
      <AppFooter />
    </div>
  </div>
</template>
