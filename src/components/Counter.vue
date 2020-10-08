<template>
  <h2 class="mb-2 text-gray-800 text-md">Number of todos: {{ numTodos }}</h2>
</template>

<script>
import { computed } from "vue";

export default {
  props: {
    todos: Array,
  },

  setup(props) {
    let numTodos = computed(() => props.todos.length);

    return {
      numTodos,
    };
  },
};
</script>