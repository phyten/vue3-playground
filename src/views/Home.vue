<template>
  <div class="container">
    <MatrixContainer :users="users" :skills="skills">
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
