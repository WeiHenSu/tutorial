<script>
let id = 0
export default{
  data() {
    return {
      newTodo:'',
      hide: false,
      todos:[
        {id: id++, text: 'Learn html',done: false},
        {id: id++, text: 'Learn css',done: false},
        {id: id++, text: 'Learn Js',done: false},
      ]
    }
  },
  computed:{
    filteredTodos() {
      return this.hide
        ? this.todos.filter((t) => !t.done) //剩還沒做完的
        : this.todos
    }
  },
  methods:{
    addTodo(){
      this.todos.push({id:id++, text:this.newTodo, done:false})
      this.newTodo=''
    },
    removeTodo(todo){
      this.todos = this.todos.filter((t) => t !== todo) 
    },
       
  }
}
</script>

<template>
  <input v-model="newTodo" @keyup.enter="addTodo">
  <button @click="addTodo">add Todo</button>
  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hide = !hide">
     {{ hide ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>


