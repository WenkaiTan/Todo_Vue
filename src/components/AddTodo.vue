<template>
    <form @submit="addTodo">
        <input type='text' v-model="title" name='title' placeholder="Add to do..." class='input'/>
        <input type='submit' value="Submit" class='submit'>
    </form>
</template>

<script>
//import uuid from 'uuid';
export default {
    name:'AddTodo',
    data() {
        return {
            title:''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                title:this.title,
                completed:false
            }
             this.$emit('add-todo',newTodo);
            this.title ='';
        }
    }
}
</script>

<style scoped>
form {
    display:flex;
}
.input {
    flex:10;
    padding:10px;
}
.submit {
    flex:2;
    color:white;
    background:black;
    padding:5px;
}
</style>>