<template>
  <img alt="Vue logo" src="./assets/logoG6.jpeg">
  <Ejercicio1/>
   <Ejercicio2/>
  <Ejercicio4/>
  <Ejercicio5/>
  <Ejercicio3/>
</template>

<script>
import Ejercicio5 from './components/Ejercicio5.vue'
import Ejercicio4 from './components/Ejercicio4.vue'
import Ejercicio1 from './components/Ejercicio1.vue'
import Ejercicio2 from './components/Ejercicio2.vue'
import Ejercicio3 from './components/Ejercicio3.vue'

export default {
  name: 'App',
  components: {
    Ejercicio4,
    Ejercicio1,
    Ejercicio5,
    Ejercicio2,
    Ejercicio3
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
