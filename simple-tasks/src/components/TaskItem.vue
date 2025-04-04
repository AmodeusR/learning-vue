<template>
  <li>
    <div>
      <h2>{{ title }}</h2>
      <p v-if="description">{{ description }}</p>
    </div>
    <button class="delete" @click="$emit('task-deletion', id)">Delete</button>
  </li>
</template>

<script setup lang="ts">
  import type { Task } from "./types";


  const { title, description, id } = defineProps<Task>();

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
    display: flex;
    justify-content: space-between;
    align-items: center;
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
  .delete {
    background: none;
    border: none;
    color: #ccc4;
    transition: color 150ms;
    padding: .5rem 0rem;
    font-weight: 700;
    font-size: .9rem;

    &:hover {
      color: crimson;
      cursor: pointer;
    }
  }
</style>
