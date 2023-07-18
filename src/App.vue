<template>
  <div>

    <img alt="Vue logo" src="./assets/logo.png">
    <h1>New project</h1>
    <ClienteCrud/>
    <ProdutoCrud/>
  </div>
</template>

<script>

import ClienteCrud from './components/ClienteCrud.vue';
import ProdutoCrud from './components/ProdutoCrud.vue'

export default {
  name: 'App',
  components:{
    ClienteCrud,
    ProdutoCrud
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
