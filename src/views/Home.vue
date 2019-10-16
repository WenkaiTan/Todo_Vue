<template>
  <div id="app">
    <AddTodo v-on:add-todo="addtodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="delTodo"/>
  </div>
</template>

<script>
import Todos from '../components/Todos';
//import Header from '../Layout/Header';
import AddTodo from '../components/AddTodo';
//import uuid from 'uuid';
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
          todos: []
    }
  },
  methods:{
    delTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
      .catch(err => console.log(err));

    },
    addtodo(newTodo) {
      const {title, completed} = newTodo;
      axios.post('https://jsonplaceholder.typicode.com/todos',{
        title,
        completed
      })
      .then(res => this.todos = [...this.todos, res.data])
      .catch(err => console.log(err));
      
    }
  },
  created() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res => res.json())
    .then(data => this.todos = data)
  }
}
</script>

<style>

</style>
