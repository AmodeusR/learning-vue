<template>
  <li>
    <h2>{{ title }}</h2>
    <p v-if="description">{{ description }}</p>
  </li>
</template>

<script setup lang="ts">
  import type { Task } from "./types";

  type TaskInfo = Omit<Task, "id">;

  const { title, description } = defineProps<TaskInfo>();

</script>

<style scoped>
  h2 {
    font-weight: bold;
    font-size: 2rem;
  }

  p {
    text-indent: 20px;
  }

  li {
    width: 100%;
    list-style: none;
    margin: 1rem 0;
    padding: .5rem 1rem;
    border: 1px solid #ccc4;
    border-radius: 4px;
    transition: 200ms border-color;
  }

  li:hover {
    border-color: #ccc8
  }
</style>
