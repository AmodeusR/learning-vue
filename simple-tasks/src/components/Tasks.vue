<script setup lang="ts">
  import TaskItem from "./TaskItem.vue";
  import type { Task } from "./types";

  const { tasks, deleteTask } = defineProps<{ tasks: Task[], deleteTask: ((id: string) => void)}>();

</script>

<template>
  <ul>
    <TaskItem v-for="task in [...tasks].reverse()" :key="task.id" :id="task.id" :title="task.title" :description="task.description" @task-deletion="deleteTask" />
  </ul>
</template>

<style>
  ul {
    width: 100%;
    padding: 0;
  }
</style>
