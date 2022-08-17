<template>
       

    <!--barra de menu-->
    <div class="fixed-top">
      <nav class="navbar navbar-expand-lg navbar-info bg-info">
        <div class="container-fluid">
          


        
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
           <button
              class="btn  btn-info w-100 text-light"
              @click="Home()"
              style="border-radius: 10px; margin: 10px"
            > Menu</button>
          </li>
          
              <li class="nav-item">
           <button
              class="btn  btn-info w-100 text-light"
              @click="Ejercicio1()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 1
 </button>

              </li>
  <li class="nav-item">
           <button
              class="btn btn-info w-100 text-light"
              @click="Ejercicio2()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 2
 </button>
              </li>
  <li class="nav-item">
               <button
              class="btn  btn-info w-100 text-light"
              @click="Ejercicio3()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 3
 </button>

              </li>

                <li class="nav-item">
               <button
              class="btn  btn-info w-100 text-light"
              @click="Ejercicio32()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 3.2
 </button>

              </li>


              <li class="nav-item">
                <button
              class="btn  btn-info w-100 text-light"
              @click="Ejercicio4()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 4
 </button>
              </li>
              <li class="nav-item">
                <button
              class="btn  btn-info w-100 text-light"
              @click="Ejercicio5()"
              style="border-radius: 10px; margin: 10px"
            >
              Ejercicio 5
 </button>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>

<div >
  <!-- Anterior -->
  
  <img alt="Vue logo" src="./assets/logo_si.png" style="width: 20vw">
<div id="portada">
<Portada/>
</div>

    
    
  <div  id="ejercicio1" style="display: none">
    <Ejercicio1 />
    <hr/>
  </div>
  
    <div id="ejercicio2" style="display: none">
    <Ejercicio2 />
    <hr/>
  </div>
    <div id="ejercicio3" style="display: none">
    <Ejercicio3 />
    <hr/>
  </div>
      <div id="ejercicio32" style="display: none">
    <Ejercicio3_2 />
    <hr/>
  </div>
    <div id="ejercicio4" style="display: none">
    <Ejercicio4 />
    <hr/>
  </div>
    <div id="ejercicio5" style="display: none">
    <Ejercicio5 />
    <hr/>
  </div>

</div>
  
</template>

<script>
import Ejercicio5 from './components/Ejercicio5.vue'
import Ejercicio4 from './components/Ejercicio4.vue'
import Ejercicio1 from './components/Ejercicio1.vue'
import Ejercicio2 from './components/Ejercicio2.vue'
import Ejercicio3 from './components/Ejercicio3.vue'
import Ejercicio3_2 from './components/Ejercicio3_2.vue'
import Portada from './components/Portada.vue'

export default {
  name: 'App',
  components: {
    Ejercicio4,
    Ejercicio1,
    Ejercicio5,
    Ejercicio2,
    Ejercicio3,
    Ejercicio3_2,
    Portada
}, methods: {
  Home(){
    document.getElementById("portada").style.display = "block";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
  },
  Ejercicio1() {
      document.getElementById("ejercicio1").style.display = "block";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
      document.getElementById("portada").style.display = "none";
    },
      Ejercicio2() {
      document.getElementById("ejercicio2").style.display = "block";
      document.getElementById("portada").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
      document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
    },
          Ejercicio32() {
      document.getElementById("ejercicio32").style.display = "block";
            document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
      document.getElementById("portada").style.display = "none";
    },
      Ejercicio3() {
      document.getElementById("ejercicio3").style.display = "block";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
      document.getElementById("portada").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
    },
      Ejercicio4() {
      document.getElementById("ejercicio4").style.display = "block";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("portada").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
      document.getElementById("ejercicio5").style.display = "none";
    },
      Ejercicio5() {
      document.getElementById("ejercicio5").style.display = "block";
      document.getElementById("ejercicio2").style.display = "none";
      document.getElementById("ejercicio3").style.display = "none";
      document.getElementById("ejercicio4").style.display = "none";
      document.getElementById("ejercicio32").style.display = "none";
      document.getElementById("ejercicio1").style.display = "none";
      document.getElementById("portada").style.display = "none";
    }
},
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

.c-button{
    width: 20vw !important;

}
</style>
