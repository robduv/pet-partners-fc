<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref } from 'vue'

const items = ref([
  { label: 'Pet Partners of Fairfield County', icon: 'pi pi-heart', route: '/' },
  { label: 'About', icon: 'pi pi-info', route: 'about' },
  { label: 'Contact', icon: 'pi pi-phone', route: 'contact' },
])
</script>

<template>
  <div
    class="bg-surface-0 dark:bg-surface-900 p-6 rounded-2xl max-w-7xl mx-auto border border-surface-200 dark:border-surface-700 w-full"
  >
    <Menubar :model="items" class>
      <template #item="{ item, props }">
        <RouterLink v-slot="{ href, navigate }" :to="item.route" custom>
          <a v-ripple :href="href" v-bind="props.action" @click="navigate">
            <span :class="item.icon" />
            <span>{{ item.label }}</span>
          </a>
        </RouterLink>
      </template>
    </Menubar>
  </div>
</template>
