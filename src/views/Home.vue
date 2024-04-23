<template>
  <div class="container">
    <MatrixContainer :users="users" :skills="skills">
      <template #user-header>
        <div v-for="user in users" :key="user.id">
          {{ user.name }}
        </div>
      </template>
      <template #skill-header>
        <div v-for="skill in skills" :key="skill.id">
          {{ skill.name }}
        </div>
      </template>
      <template v-for="name in skillNames" :key="name" #[name]>
        <div>{{ name }}</div>
      </template>
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
  { id: 1, name: 'Aliceだよーーーーーん' },
  { id: 2, name: 'Bob' },
  { id: 3, name: 'Charlie' }
];

const skills: Skill[] = [
  { id: 1, name: 'java' },
  { id: 2, name: 'type' },
  { id: 3, name: 'vue' }
];

const elementLength = skills.length * users.length;

const skillNames = skills.map((skill) => skill.name);
</script>

<style lang="scss" scoped></style>
