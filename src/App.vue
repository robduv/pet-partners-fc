<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Menubar from 'primevue/menubar'
import { ref } from 'vue'

const items = ref([
  { label: 'Home', icon: 'pi pi-home', route: '/' },
  { label: 'About', icon: 'pi pi-info', route: 'about' },
  { label: 'Contact', icon: 'pi pi-phone', route: 'contact' },
])
</script>

<template>
  <div class="card">
    <Menubar :model="items">
      <template #item="{ item, props }">
        <RouterLink v-slot="{ href, navigate }" :to="item.route" custom>
          <a v-ripple :href="href" v-bind="props.action" @click="navigate">
            <span :class="item.icon" />
            <span>{{ item.label }}</span>
          </a>
        </RouterLink>
      </template>
    </Menubar>
    <RouterView />
  </div>
</template>

<style scoped></style>
