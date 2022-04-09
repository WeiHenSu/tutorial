<script>
let id=0
export default ({
    data() {
        return{
            todo:'',
            todolist:[
                {id:id++, text:'learn css'},
                {id:id++, text:'learn js'},
                {id:id++, text:'learn vue'}
            ]


        }
    },
    methods:{
      addtodo(){
        this.todolist.push({id:id++,text:this.todo})
        this.todo=''
      },
      removetodo(todos){
        this.todolist = this.todolist.filter((t) => t !== todos)
      }
        
    }
})
</script>

<template>
   <input v-model="todo" @keyup.enter="addtodo">
   <button @click="addtodo">add todo</button>
   <ul>
      <li v-for="todos in todolist" :key="todos.id"> 
        {{todos.text}}
        <button @click="removetodo(todos)">X</button>
      </li>
   </ul> 
</template>
