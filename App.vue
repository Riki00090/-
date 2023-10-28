<template>
  <div class="container">
  <NavComp/>
  <router-view></router-view>
  </div>
</template>

<script>
import NavComp from './components/Navigation.vue'

export default {
  name: 'App',
  components: {
    NavComp
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(219, 255, 165): 
  color: rgb(124, 223, 232);
}

.container {
background-color: rgba(126, 243, 175, 0.781);
display: black;
flex-direction: column;
align-intens: center;
height: 100%;
}
</style>
