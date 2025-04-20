<script setup lang="ts">
export interface ActionButtonProps {
  url: string
  label: string
  icon: string
}

const actionButtonProps = defineProps<ActionButtonProps>()
</script>

<template>
  <a
    target="_blank"
    :href="actionButtonProps.url"
    class="rounded-lg bg-violet-500 px-2.5 py-2.5 text-sm text-white hover:bg-violet-400"
    ><i :class="icon"></i> {{ actionButtonProps.label }}</a
  >
</template>
