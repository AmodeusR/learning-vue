<script setup lang="ts">
  import TaskItem from "./TaskItem.vue";
  import type { Task } from "./types";

  const { tasks } = defineProps<{ tasks: Task[]}>();
</script>

<template>
  <ul>
    <TaskItem v-for="task in [...tasks].reverse()" :key="task.id" :title="task.title" :description="task.description" />
  </ul>
</template>

<style>
  ul {
    width: 100%;
    padding: 0;
  }
</style>
