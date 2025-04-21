<script setup lang="ts">
export interface TeamMemberProps {
  name: string
  role: string
  imageUrl: string
  bio: string
}

const teamMember = defineProps<TeamMemberProps>()
</script>

<template>
  <div
    class="relative flex max-h-22 min-h-18 items-center gap-2 overflow-visible rounded-lg border border-slate-300 bg-slate-100 pl-4 text-slate-700"
  >
    <img
      :src="teamMember.imageUrl"
      alt="Team Member"
      class="absolute -left-6 h-26 w-26 rounded-full"
    />
    <div class="flex flex-col pr-2 pl-18">
      <div class="font-bold">{{ teamMember.name }}</div>
      <div class="text-sm italic">{{ teamMember.role }}</div>
      <span class="text-sm">{{ teamMember.bio }}</span>
    </div>
  </div>
</template>
