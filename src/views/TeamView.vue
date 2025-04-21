<script setup lang="ts">
import type { TeamMemberProps } from '@/components/TeamMember.vue'

const teamMembers: TeamMemberProps[] = [
  {
    name: 'Jen Krasnow',
    role: 'Team Evaluator',
    imageUrl: '/rob.jpeg',
    bio: 'This is a test bio for Jen Krasnow. She is a team evaluator and pet therapy team with her dog Kako.',
  },
  {
    name: 'Katy Rahe',
    role: 'Team Evaluator',
    imageUrl: '/rob.jpeg',
    bio: 'This is a test bio for Katy Rahe. She is a team evaluator and pet therapy team with her dog River.',
  },
  {
    name: "Patti O'Keeffe",
    role: 'Team Evaluator',
    imageUrl: '/rob.jpeg',
    bio: "This is a test bio for Patti O'Keefee. She is a team evaluator.",
  },
  {
    name: 'Rob Duval',
    role: 'CTO',
    imageUrl: '/rob.jpeg',
    bio: 'This is a test bio for Rob Duval. He is the Chief Technology Officer and pet therapy team with his dog Sybil.',
  },
]
</script>

<template>
  <div
    class="flex flex-col gap-4 rounded-xl border border-slate-300 bg-white p-4 text-base text-slate-700"
  >
    <div class="text-lg font-bold">Meet the Team</div>
    <TeamMember
      class="m-2 ml-6"
      v-for="(member, index) in teamMembers"
      :key="index"
      :name="member.name"
      :role="member.role"
      :imageUrl="member.imageUrl"
      :bio="member.bio"
    >
    </TeamMember>
  </div>
</template>
