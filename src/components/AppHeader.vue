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
    class="mx-auto w-full max-w-7xl rounded-xl border border-surface-200 bg-surface-0 p-6 dark:border-surface-700 dark:bg-surface-900"
  >
    <div class="text text-surface-600 dark:text-surface-400">
      <div class="flex items-center justify-start gap-2">
        <div class="text-xl font-bold">
          <RouterLink to="/">
            <a v-ripple>
              <span>Pet Partners of Fairfield County</span>
            </a>
          </RouterLink>
        </div>
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
    </div>
  </div>
</template>
