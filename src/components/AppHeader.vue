<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref } from 'vue'

const items = ref([
  { label: 'Home', icon: 'pi pi-home', route: '/' },
  { label: 'Team', icon: 'pi pi-users', route: 'team' },
  { label: 'Sign Up', icon: 'pi pi-user-plus', route: 'sign-up' },
  { label: 'Contact', icon: 'pi pi-envelope', route: 'contact' },
])
</script>

<template>
  <div
    class="mx-auto w-full max-w-7xl rounded-xl border border-surface-200 bg-surface-0 p-6 text-surface-600 dark:border-surface-700 dark:bg-surface-900 dark:text-surface-400"
  >
    <div class="flex items-center justify-between gap-2">
      <div class="flex items-center gap-2">
        <RouterLink to="/">
          <div class="flex items-center gap-2">
            <img class="h-8 w-8" src="../assets/logo.png" alt="Logo" />
            <span class="text-xl font-bold">Pet Partners of Fairfield County</span>
          </div>
        </RouterLink>
        <RouterLink
          v-for="item in items"
          :key="item.route"
          v-slot="{ href, navigate }"
          :to="item.route"
          custom
        >
          <div class="flex text-lg">
            <a v-ripple :href="href" @click="navigate">
              <span :class="item.icon" />
              <span class="m-1">{{ item.label }}</span>
            </a>
          </div>
        </RouterLink>
      </div>
      <div class="flex justify-end gap-2">
        <a
          href="https://www.facebook.com/groups/322425249919492"
          target="_blank"
          rel="noopener noreferrer"
          class="text-surface-600 transition-colors hover:text-primary dark:text-surface-400"
        >
          <i class="pi pi-facebook"></i>
        </a>
      </div>
    </div>
  </div>
</template>
