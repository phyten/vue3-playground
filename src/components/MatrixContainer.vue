<template>
  <div class="matrix-container">
    <div class="blank">スキル</div>
    <div class="user-header">
      <div v-for="user in props.users" :key="user.id" class="user-header-item">{{ user.name }}</div>
    </div>
    <div class="content-wrapper">
      <div v-for="skill in props.skills" :key="skill.id" class="content-row">
        <div class="skill-header-item">
          {{ skill.name }}
        </div>
        <div v-for="user in props.users" :key="user.id" class="content-cell">
          <slot name="evaluation"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface User {
  id: number;
  name: string;
}

interface Skill {
  id: number;
  name: string;
}

interface Props {
  users: User[];
  skills: Skill[];
}

const props = defineProps<Props>();

const horizontalLength = props.users.length;
</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

.matrix-container {
  width: 90vw;
  display: grid;
  grid-template-columns: max-content repeat(v-bind(horizontalLength), max-content);
  gap: 0;
  height: 90vh;
  overflow: scroll;
}

.blank {
  grid-column-start: 1;
}

.user-header {
  display: contents;
}

.blank,
.user-header-item {
  padding: 0.1rem 1rem;
  background-color: #f0f0f0;
}

.user-header-item {
  min-width: 120px;
  text-align: center;
  /* overflow: hidden;
     text-overflow: ellipsis;
     white-space: nowrap; */
}

.content-wrapper {
  display: contents;
}

.content-row {
  display: contents;
}

.skill-header-item {
  grid-column-start: 1;
}

.content-cell {
}

::v-slotted(div) {
  border: 1px solid #000;
}

::v-slotted(.skill-header > div) {
  grid-column-start: 1;
}
</style>
