<template>
  <div class="container mx-auto py-2 px-4 lg:container lg:mx-auto">
    <h1 class="text-4xl font-serif text-blue-700">Todos</h1>
    <Counter :todos="todos" />
    <ul class="space-y-1">
      <li
        class="relative flex p-2 text-gray-00 shadow border rounded"
        v-for="(todo, index) in todos"
        :key="todo"
      >
        {{ todo }}
        <button
          class="right-0 top-0 absolute btn btn-red"
          @click="removeTodo(index)"
        >
          X
        </button>
      </li>
    </ul>
    <div class="flex mt-3">
      <input class="input" type="text" v-model="newTodo" />
      <button @click="addTodo" class="btn btn-blue">submit</button>
    </div>
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";
import { reactive, ref } from "vue";
import { todos } from "./state";

export default {
  components: {
    Counter,
  },

  setup() {
    let newTodo = ref("");

    function addTodo() {
      todos.push(newTodo.value);
      newTodo.value = "";
    }

    function removeTodo(todoIndex) {
      todos.splice(todoIndex, 1);
    }

    return {
      todos,
      newTodo,
      addTodo,
      removeTodo,
    };
  },
};
</script>
<style>
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
.btn-red {
  @apply bg-red-500 text-white;
}
.btn-red:hover {
  @apply bg-blue-700;
}
.input {
  @apply shadow appearance-none border rounded w-full py-2;
}
</style>