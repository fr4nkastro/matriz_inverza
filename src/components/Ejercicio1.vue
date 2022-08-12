<template>
<h2>Suma de matrices</h2>
<div class="container">
  <div>


    <div class="divhijo">
        <table>
            <tr><td colspan="2">Matriz A</td></tr>
            <tr><td><input type="number" v-model="A11"></td><td><input type="number" v-model="A12"></td></tr>
            <tr><td><input type="number" v-model="A21"></td><td><input type="number" v-model="A22"></td></tr>
        </table>

    </div >

    <div class="divhijo">
        <table>
            <tr><td colspan="2">Matriz B</td></tr>
            <tr><td><input type="number" v-model="B11"></td><td><input type="number" v-model="B12"></td></tr>
            <tr><td><input type="number" v-model="B21"></td><td><input type="number" v-model="B22"></td></tr>
        </table>

    </div >

     <div class="divhijo">
        <table v-if="MatrizC[0][0]!=null">
            <tr><td colspan="2">Matriz C</td></tr>
            <tr><td><input type="number" v-model="this.MatrizC[0][0]"></td><td><input type="number" v-model="this.MatrizC[0][1]"></td></tr>
            <tr><td><input type="number" v-model="this.MatrizC[1][0]"></td><td><input type="number" v-model="this.MatrizC[1][1]"></td></tr>
        </table>

    </div>
 
<input type="button" value="Calcular" @click="calculate">
  </div>
<div>
    

</div>
</div>

 
</template>

<script>
export default {
  data(){
        return{
        A11:0,
        A12:0,
        A21:0,
        A22:0,

        B11:0,
        B12:0,
        B21:0,
        B22:0,

        
        MatrizA:[null][null] ,
        MatrizB:[null][null],
        MatrizC:[[null, null],[null, null]]
      
     }
   },
    methods:{
        calculate(){
            this.MatrizA=[[this.A11,this.A12],[this.A21,this.A22]];
            this.MatrizB=[[this.B11,this.B12],[this.B21,this.B22]];
            for (let index = 0; index < this.MatrizA.length; index++) {
                
                for (let index2 = 0; index2 < this.MatrizA.length; index2++) {
                    this.MatrizC[index][index2]= this.MatrizA[index][index2]+this.MatrizB[index][index2];
                }
            }
            
        }
    }
    
}
</script>
.container{
     display: flex;
   justify-content: center;
}
.divhijo{
    margin: 10px;
}
<style>

</style>