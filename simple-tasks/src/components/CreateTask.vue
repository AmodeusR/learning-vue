<script setup lang="ts">
import { ref } from "vue";
import type { Task } from "./types";
import { nanoid } from "nanoid";

const emit = defineEmits(["task-creation"]);
const title = ref("");
const description = ref("");

const handleSubmit = () => {
  if (title.value.trim() === "") {
    alert("Title must exist");

    return 0;
  }
  const newTask: Task = {
    id: nanoid(),
    title: title.value,
    description: description.value
  }

  emit("task-creation", newTask);

  title.value = "";
  description.value = "";
};
</script>

<template>
  <form @submit.prevent="handleSubmit">
    <label>
      Title
      <input type="text" name="title" v-model="title" />
    </label>
    <label
      >Description
      <input type="text" name="description" v-model="description" />
    </label>
    <button type="submit">Create task</button>
  </form>
</template>

<style scoped>
  form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  label {
    display: flex;
    flex-direction: column;
    font-size: 1rem;
  }

  input {
    color: #ccc;
    padding: 1rem;
    background-color: var(--vt-c-black-soft);
    border: none;

    &:focus-within, &:focus {
      outline: 2px solid var(--vt-c-black-mute);
    }
  }

  button {
    font-size: 1.25rem;
    font-weight: 500;
    padding: 1rem;
    border-radius: .25rem;
    background-color: var(--vt-c-black-soft);
    border: 2px solid var(--vt-c-black-mute);
    color: #ccc;
    transition: background-color 100ms;

    &:hover {
      background-color: var(--vt-c-black-mute);
      cursor: pointer;
    }
  }
</style>
