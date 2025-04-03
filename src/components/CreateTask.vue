<script setup lang="ts">
import { ref } from "vue";

const title = ref("");
const description = ref("");

const handleSubmit = () => {
  console.log(title.value);
  console.log(description.value);
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
  }

  input {
    color: #ccc;
    padding: 1rem;
    background-color: var(--vt-c-black-soft);
    border: none;
  }

  button {
    font-size: 1.25rem;
    font-weight: 500;
    padding: .5rem;
    border-radius: .25rem;
    background-color: var(--vt-c-black-soft);
    border: none;
    color: #ccc;
    transition: background-color 100ms;

    &:hover {
      background-color: var(--vt-c-black-mute);
      cursor: pointer;
    }
  }

</style>
