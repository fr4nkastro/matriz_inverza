<template>
<h2>Identidad | Nulidad de matriz</h2>
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
        <table v-if="MatrizB[0][0]!=null">
            <tr><td colspan="2">Matriz B</td></tr>
            <tr><td><input type="number" v-model="this.MatrizB[0][0]"></td><td><input type="number" v-model="this.MatrizB[0][1]"></td></tr>
            <tr><td><input type="number" v-model="this.MatrizB[1][0]"></td><td><input type="number" v-model="this.MatrizB[1][1]"></td></tr>
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
        A11:1,
        A12:3,
        A21:2,
        A22:4,

        
        MatrizA:null ,
        MatrizB:[[null, null],[null, null]]
      
     }
   },
    methods:{
        calculate(){
            this.MatrizA=[[this.A11,this.A12],[this.A21,this.A22]];
            for (let index = 0; index < this.MatrizA.length; index++) {

                for (let index2 = 0; index2 < this.MatrizA.length; index2++) {
                    //Verificar que su diagonal sean 1

                            this.MatrizB[index][index2]=0;

                    
                    if(index== index2){
                        if(this.MatrizA[index][index]!=1){
                            alert('Error: Su matriz no es identidad')
                            this.MatrizB=null;
                            break;
                        }
                    }else if(this.MatrizA[index][index2]!=0){
                            alert('Error: Su matriz no es identidad')
                            this.MatrizB=null;
                            break;
                        }
                        
                            
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