<template>
  <NavComponent text="Exemplo VueJS - StarWars"/> 
  <div class="container">
    <CardComponent/>
  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
  // import HelloWorld from './components/HelloWorld.vue'
  import CardComponent from './components/CardComponent.vue'
  import NavComponent from './components/NavComponent.vue';
  
  export default {
    name: 'App',
    components: {
      CardComponent,
      NavComponent
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
  .container{
    width: 100% !important;
    margin: 0 auto;
  }
</style>
