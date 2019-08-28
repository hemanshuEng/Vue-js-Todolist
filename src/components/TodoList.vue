<template>
  <div>
    <input type="text" class="todo-input" placeholder="What needs to be done" v-model="newTodo"
    @keyup.enter="addTodo" />
    <div v-for="todo in todos" :key="todo.id" class="toso-item">
      {{todo.title}}
    </div>
  </div>
</template>

<script>
export default {
  name: "todo-list",
  data() {
    return {
      newTodo:'',
      idForTodo:3,
      todos:[
        {
          'id':1,
          'title':'Finish Vue todoapp',
          'completed':false,
        },
        {
          'id':2,
          'title':'Create app with laravel',
          'completed':false,
        },
      ]
    };
  },
  methods:{
    addTodo(){
      this.todos.push({
        id:this.idForTodo,
        title:this.newTodo,
        completed:false,
      })
      this.newTodo =''
      this.idForTodo++ 
    }
  
}
}
</script>

<style lang="scss">
.todo-input {
  width: 100%;
  padding: 10px 18px;
  font-size: 18px;
  margin-top: 16px;
  &:focus {
    outline: none;
  }
}
</style>