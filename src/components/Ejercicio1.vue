<template>
<h2 class="fw-bold text-uppercase text-primary" >Suma de matrices</h2>
<div class="container">
  <div>


    <div class="border-start border-end  border-3 p-4">
        <table>
            
            <tr><td colspan="2">Matriz A</td></tr>
            <tr><td><input class="form-control" type="number" v-model="A11"></td><td><input class="form-control" type="number" v-model="A12"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="A21"></td><td><input class="form-control" type="number" v-model="A22"></td></tr>
        </table>

    </div >
    <br/>

    <div class="border-start border-end  border-3 p-4">
        <table>
            <tr><td colspan="2">Matriz B</td></tr>
            <tr><td><input class="form-control" type="number" v-model="B11"></td><td><input class="form-control" type="number" v-model="B12"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="B21"></td><td><input class="form-control" type="number" v-model="B22"></td></tr>
        </table>

    </div >
<br/>
     <div  v-if="MatrizC[0][0]!=null" class="border-start border-end  border-3 p-4">
        <table>
            <tr><td colspan="2">Matriz C</td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizC[0][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizC[0][1]"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizC[1][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizC[1][1]"></td></tr>
        </table>
 


    </div>
    <input id="c-button" class="btn btn-info w-100 text-light "
              style="border-radius: 10px; margin: 10px" type="button" value="Calcular" @click="calculate">
  
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


<style>
.container{
     display: flex;
   justify-content: center;
}

#c-button{
    width: 20vw !important;

}

</style>