<template>
  <div class="matrix-container">
    <div class="blank">空タグ</div>
    <slot name="user-header"></slot>

    <div class="skill-header">
      <slot name="skill-header"></slot>
    </div>

    <slot name="java"></slot>
    <slot name="type"></slot>
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

const horizontalLength = props.users.length + 1;
</script>

<style lang="scss" scoped>
.matrix-container {
  width: 100%;
  display: grid;
  grid-template-columns: 200px repeat(v-bind(horizontalLength), minmax(auto, max-content));
  gap: 1rem;

  > :not(:first-child) {
    max-width: 100px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
}

.blank {
  grid-column-start: 1;
}

.skill-header {
  display: contents;
}

::v-slotted(div) {
  border: 1px solid #000;
}

::v-slotted(.skill-header > div) {
  grid-column-start: 1;
}
</style>
