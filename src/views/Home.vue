<template>
  <div class="container">
    <MatrixContainer :users="users" :skills="skills">
      <!-- <template #user-header> </template>
           <template #skill-header> </template>
           <template #content> </template> -->
      <template #user-header>
        <div v-for="user in users" :key="user.id">
          {{ user.name }}
        </div>
      </template>
      <div v-for="skill in skills" :key="skill.id">
        {{ skill.name }}
      </div>
    </MatrixContainer>
  </div>
</template>

<script setup lang="ts">
import MatrixContainer from '@/components/MatrixContainer.vue';

interface User {
  id: number;
  name: string;
}

interface Skill {
  id: number;
  name: string;
}

const users: User[] = [
  { id: 1, name: 'Alice' },
  { id: 2, name: 'Bob' },
  { id: 3, name: 'Charlie' }
];

const skills: Skill[] = [
  { id: 1, name: 'JavaScript' },
  { id: 2, name: 'TypeScript' },
  { id: 3, name: 'Vue.js' }
];
</script>

<style lang="scss" scoped>
</style>
