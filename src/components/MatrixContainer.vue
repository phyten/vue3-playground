<template>
  <div class="matrix-container">
    <div>空タグ</div>
    <slot name="user-header"></slot>
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
interface Props {
  users: string;
  skills: string;
}

const props = defineProps<Props>();

const horizontalLength = props.users.length + 1;

console.log(props.users);
</script>

<style lang="scss" scoped>
.matrix-container {
  display: grid;
  grid-template-columns: repeat(v-bind(horizontalLength), 1fr);
  gap: 1rem;
}
</style>
