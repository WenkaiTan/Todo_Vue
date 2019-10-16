<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>
<script>
import Header from './Layout/Header';
export default {
  name:'app',
  components: {
    Header
  }
}
</script>
<style>
.header a {
    color:white;
    text-decoration: none;
    padding:10px;
}

</style>
