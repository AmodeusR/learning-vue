<script setup lang="ts">
  import Tasks from "@/components/Tasks.vue";
  import CreateTask from "./components/CreateTask.vue";
</script>

<template>
  <div class="wrapper">
    <h1>Tasks</h1>

    <main>
      <CreateTask />
      <Tasks />
    </main>
  </div>
</template>

<style scoped>
  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  main {
    width: min(40rem, 100%);
  }
  h1 {
    font-size: 3rem;
  }
</style>
