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
    class="relative flex min-h-24 items-center gap-2 overflow-hidden rounded-lg border border-slate-300 bg-slate-100 text-slate-700"
  >
    <img :src="teamMember.imageUrl" alt="Team Member" class="absolute h-32 w-32" />
    <div class="flex flex-col pr-2 pl-34">
      <div class="font-bold">{{ teamMember.name }}</div>
      <div class="text-sm italic">{{ teamMember.role }}</div>
      <p class="text-sm">{{ teamMember.bio }}</p>
    </div>
  </div>
</template>
