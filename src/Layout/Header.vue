<template>
    <header class="header">
        <h1>TodoList</h1>
        <div class='div'>
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>

    </header>

</template>
<script>
export default {
    name:'Header'
}
</script>>

<style scoped>
.header {
    background: black;
    text-align: center;
    color:white;
    padding:5px;
}


</style>