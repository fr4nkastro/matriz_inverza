<template>
<h2 class="fw-bold text-uppercase text-primary" >Potencia de matriz</h2>
<div class="container">
  <div>
   <span>Escalar</span> <input class="form-control" v-model="multiplo" type="number">
   <br/>
    <div class="border-start border-end  border-3 p-4">
        
        <table>
            <tr>
                <td colspan="3">Matriz A</td>
            </tr>
            <tr>
                
                <td><input class="form-control" type="number" v-model="A11"></td>
                <td><input class="form-control" type="number" v-model="A12"></td>
            </tr>
            <tr>
                <td><input class="form-control" type="number" v-model="A21"></td>
                <td><input class="form-control" type="number" v-model="A22"></td>
            </tr>
        </table>

    </div >
     <div class="border-start border-end  border-3 p-4">
        <table v-if="MatrizC[0][0]!=null">
            <tr><td colspan="2">Matriz C</td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizC[0][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizC[0][1]"></td></tr>
            <tr><td><input class="form-control" type="number" v-model="this.MatrizC[1][0]"></td><td><input class="form-control" type="number" v-model="this.MatrizC[1][1]"></td></tr>
        </table>

    </div>
 
<input type="button"  id="c-button" class="btn btn-info w-100 text-light"
              style="border-radius: 10px; margin: 10px "  value="Calcular" @click="calculate">
  </div>
<div>
    

</div>
</div>

 
</template>

<script>
export default {
  data(){
        return{
        multiplo :0,    

        A11:0,
        A12:0,
        A21:0,
        A22:0,

        B11:0,
        B12:0,
        B21:0,
        B22:0,

        potencia:1,
        MatrizA:[null][null] ,
        MatrizB:[null][null],
        MatrizC:[[null, null],[null, null]]
      
     }
   },
    methods:{
        calculate(){
            this.MatrizA=[[this.A11,this.A12],[this.A21,this.A22]];
            console.log(this.MatrizA);
            console.log(this.multiplo);
            for (let index = 0; index < this.MatrizA.length; index++) {
                
                for (let index2 = 0; index2 < this.MatrizA.length; index2++) {

                    for(let i = 0; i<this.multiplo;i++){
                        this.potencia = this.potencia * this.MatrizA[index][index2];
                    }
                    this.MatrizC[index][index2] = this.potencia;
                    this.potencia = 1;
                    //this.MatrizC[index][index2]= this.MatrizA[index][index2]*this.multiplo;

                }
            }
            
        }
    }
    
}
</script>

<style>
.container{
     display: flex;
   justify-content: center;
}

#c-button{
    width: 20vw !important;

}
</style>