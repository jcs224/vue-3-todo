<template>
  <div>
    <h1>Todos</h1>
    <Counter :todos="todos" />
    <ul>
      <li v-for="(todo, index) in todos" :key="todo">{{ todo }} <button @click="removeTodo(index)">X</button></li>
    </ul>
    <input type="text" v-model="newTodo">
    <button @click="addTodo">submit</button>
  </div>
</template>

<script>
import Counter from './components/Counter.vue'
import { reactive, ref } from 'vue'
import { todos } from './state'

export default {
  components: {
    Counter
  },

  setup() {
    let newTodo = ref('')

    function addTodo() {
      todos.push(newTodo.value)
      newTodo.value = ''
    }

    function removeTodo(todoIndex) {
      todos.splice(todoIndex, 1)
    }

    return {
      todos,
      newTodo,
      addTodo,
      removeTodo,
    }
  }
}
</script>
