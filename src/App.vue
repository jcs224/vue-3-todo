<template>
  <div>
    <h1>Todos</h1>
    <ul>
      <li v-for="todo in todos" :key="todo">{{ todo }}</li>
    </ul>
    <input type="text" v-model="newTodo">
    <button @click="addTodo">submit</button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  setup() {
    let todos = reactive([
      'cool beans',
    ])

    let newTodo = ref('')

    function addTodo() {
      todos.push(newTodo.value)
      newTodo.value = ''
    }

    return {
      todos,
      newTodo,
      addTodo
    }
  }
}
</script>
