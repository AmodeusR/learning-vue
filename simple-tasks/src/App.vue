<script setup lang="ts">
import Tasks from "@/components/Tasks.vue";
import CreateTask from "./components/CreateTask.vue";
import type { Task } from "./components/types";
import { useLocalStorage } from "@vueuse/core";



const tasks = useLocalStorage<Task[]>("tasks", []);

const createTask = (task: Task) => {
  tasks.value.push(task);
};

const deleteTask = (id: string) => {
  tasks.value = tasks.value.filter((task) => task.id !== id);
};
</script>

<template>
  <div class="wrapper">
    <h1>Tasks</h1>

    <main>
      <CreateTask @task-creation="createTask" />
      <Tasks :tasks="tasks" :deleteTask="deleteTask" />
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
