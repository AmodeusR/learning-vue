<script setup lang="ts">
  import TaskItem from "./TaskItem.vue";
</script>

<template>
  <ul>
    <TaskItem title="Walk the dogs" description="Take the dogs for a walk" />
    <TaskItem title="Walk the dogs" description="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Et quae consectetur eum facere dolorem molestias velit sequi nobis culpa autem.
" />
  </ul>
</template>

<style>
  ul {
    width: 100%;
    padding: 0;
  }
</style>
