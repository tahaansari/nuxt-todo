<template>
  <div class="container">
    <div class="card p-4 mt-5">
      <ul class="list-group mb-4">
        <li class="list-group-item" v-for="(todo,index) in todos" :key="todo">
          <a href="#" @click="removeTodo(index)"> {{ todo }} </a>
        </li>
      </ul>
      <form @submit.prevent="formsubmit">
        <input placeholder="Enter your task" type="text" class="form-control mb-3" v-model="todo">
        <button class="btn btn-primary">Add Todo</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo:"",
      todos: ['morning','somework','lunch','shaam']
    }
  },
  mounted(){
    alert(this.$store.state.todos)
  },
  methods:{
    formsubmit(){
      if(this.todo){
        this.todos.push(this.todo);
        this.todo="";
      }
    },
    removeTodo(index){
      this.$delete(this.todos,index)
    }
  }
}
</script>

<style></style>