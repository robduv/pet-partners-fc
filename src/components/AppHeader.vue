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
        <div class="flex text-lg hover:underline">
          <a :href="href" @click="navigate">
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
        class="transition-colors hover:text-violet-500"
      >
        <i class="pi pi-facebook"></i>
      </a>
    </div>
  </div>
</template>
