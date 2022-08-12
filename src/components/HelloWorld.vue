<template>
<div>
  <div class="divpadre">


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

    </div>
 

  </div>
<div>
    <input type="button" value="Calcular" @click="calcular">

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

        B11:1,
        B12:0,
        B21:0,
        B22:1,

        MatrizA:null,
        MatrizB:null
      
     }
   },
    methods:{
      rowOperation(matriz, indexRows, values ){
        var tempMatriz= matriz.slice();
        for (let indexColumn = 0; indexColumn < matriz.length; indexColumn++) {
          matriz[indexRows[0]][indexColumn]= tempMatriz[indexRows[0]][indexColumn]*values[0]
          matriz[indexRows[1]][indexColumn]= tempMatriz[indexRows[1]][indexColumn]*values[1]
        }
        for (let indexColumn = 0; indexColumn < matriz.length; indexColumn++) {
          matriz[indexRows[0]][indexColumn]+= tempMatriz[indexRows[1]][indexColumn]
        }
      },
      rowOperationDivided(){},

      showArray(matriz){
        var strOutput=""
        for (let index = 0; index < this.MatrizA.length; index++) {
          for (let indexCol = 0; indexCol < this.MatrizA.length; indexCol++) {
            strOutput+=String(matriz[index][indexCol]) + "\t";
          }
          strOutput+="\n"
          
        }
        console.log(strOutput);
        return strOutput;
      },
   
      calcular(){
          this.MatrizA=[[this.A11,this.A12],[this.A21,this.A22]];
          this.MatrizB=[[this.B11,this.B12],[this.B21,this.B22]];

          var tmpMatriz=this.MatrizA.slice();
          console.log(tmpMatriz);
          for (let indexRow = 0; indexRow < this.MatrizA.length; indexRow++) {
            for (let indexColumn = 0; indexColumn < this.MatrizA.length; indexColumn++) {
              if(indexRow!= indexColumn){
                var signo= 1;
                if(indexRow!=this.MatrizA.length-1){
                  
                  if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==1 && Math.sign(this.MatrizA[indexRow+1][indexColumn])==1){
                    signo=-1
                  }else if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==-1 && Math.sign(this.MatrizA[indexRow+1][indexColumn])==-1){
                    signo=-1
                  }
                  this.rowOperation(this.MatrizA,[indexRow, indexRow+1], [this.MatrizA[indexRow+1][indexColumn]*signo,this.MatrizA[indexRow][indexColumn]])
                }else if(indexRow== this.MatrizA.length-1){
                  if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==1 && Math.sign(this.MatrizA[0][indexColumn])==1){
                    signo=-1
                  }else if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==-1 && Math.sign(this.MatrizA[0][indexColumn])==-1){
                    signo=-1
                  }
                  this.rowOperation(this.MatrizA,[indexRow, 0], [this.MatrizA[0][indexColumn]*signo, this.MatrizA[indexRow][indexColumn]])
                }
              }
            }              
          }

        this.showArray(this.MatrizA);
       }

    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.divpadre{
   display: flex;
   justify-content: center;
}
.divhijo{
    margin: 10px;
}
</style>
