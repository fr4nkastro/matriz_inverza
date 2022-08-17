<template>
<h2 class="fw-bold text-uppercase text-primary" >Transpuesta de matriz</h2>
<div class="container">
  <div>


    <div class="border-start border-end  border-3 p-4">
        <table>
            <tr><td colspan="2">Matriz A</td></tr>
            <tr><td><input class="form-control" type="number" v-model="A11"></td><td><input class="form-control" type="number" v-model="A12"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="A21"></td><td><input class="form-control" type="number" v-model="A22"></td></tr>
        </table>

    </div >
     <div class="border-start border-end  border-3 p-4">
        <table v-if="MatrizB[0][0]!=null">
            <tr><td colspan="2">Matriz B</td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizB[0][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizB[0][1]"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizB[1][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizB[1][1]"></td></tr>
        </table>

    </div>
 
<input type="button" id="c-button" class="btn btn-info w-100 text-light"
              style="border-radius: 10px; margin: 10px"  value="Calcular" @click="calculate">
  </div>
<div>
    

</div>
</div>

 
</template>

<script>
export default {
  data(){
        return{
        A11:1,
        A12:3,
        A21:2,
        A22:4,

        
        MatrizA:[null][null] ,
        MatrizB:[[null, null],[null, null]]
      
     }
   },
    methods:{
        calculate(){
            this.MatrizA=[[this.A11,this.A12],[this.A21,this.A22]];
            for (let index = 0; index < this.MatrizA.length; index++) {
                
                for (let index2 = 0; index2 < this.MatrizA.length; index2++) {
                    this.MatrizB[index2][index]=this.MatrizA[index][index2];
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
#c-button{
    width: 20vw !important;

}
</style>