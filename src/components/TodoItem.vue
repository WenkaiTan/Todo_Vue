<template>
    <div class='div' v-bind:class="{'is-completed':todo.completed}" >
        <p>
            <input type='checkbox' v-on:change="markCompleted" />
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" 
            class='-del'>x</button>
            
        </p>
    </div>
</template>

<script>
export default {
    name:'TodoItem',
    props:['todo'],
    methods:{
        markCompleted() {
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
.div {
    background: #f4f4f4;
    border-bottom:2px dotted black;
    padding:5px;
}
.is-completed {
    text-decoration: line-through;
}
.-del {
    background-color:red;
    border-radius: 50px;
    color:white;
    float:right;
    padding: 6px;
}

</style>>