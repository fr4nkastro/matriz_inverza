<template>
<h2>Inversa de matriz</h2>
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
        <table v-if="MatrizB!=null">
            <tr><td colspan="2">Matriz B</td></tr>
            <tr><td><input type="number" v-model="this.MatrizB[0][0]"></td><td><input type="number" v-model="this.MatrizB[0][1]"></td></tr>
            <tr><td><input type="number" v-model="this.MatrizB[1][0]"></td><td><input type="number" v-model="this.MatrizB[1][1]"></td></tr>
        </table>

    </div>
    <input type="button" value="Calcular" @click="calcular">
 

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

        B11:1,
        B12:0,
        B21:0,
        B22:1,

        MatrizA:[null][null] ,
        MatrizB:null
      
     }
   },
    methods:{
      rowOperation(matriz, matrizb, indexRows, values ){
        var tempMatriz= matriz.slice();
        var tempMatrizB= matrizb.slice();
        for (let indexColumn = 0; indexColumn < matriz.length; indexColumn++) {
          matriz[indexRows[0]][indexColumn]= tempMatriz[indexRows[0]][indexColumn]*values[0];
          matriz[indexRows[1]][indexColumn]= tempMatriz[indexRows[1]][indexColumn]*values[1];
          matrizb[indexRows[0]][indexColumn]= tempMatrizB[indexRows[0]][indexColumn]*values[0];
          matrizb[indexRows[1]][indexColumn]= tempMatrizB[indexRows[1]][indexColumn]*values[1];
        }
        for (let indexColumn = 0; indexColumn < matriz.length; indexColumn++) {
          matriz[indexRows[0]][indexColumn]+= tempMatriz[indexRows[1]][indexColumn];
          matrizb[indexRows[0]][indexColumn]+= tempMatrizB[indexRows[1]][indexColumn];
        }
      },
      rowOperationDivided(matriz, matrizb){
        for (let index = 0; index <  matriz.length; index++)  {
          var value = matriz[index][index]
          for (let index2 = 0; index2 < matriz.length; index2++) {
          
              matriz[index][index2]= matriz[index][index2]/value;
              matrizb[index][index2]= matrizb[index][index2]/value;
            
          }
        }
      },

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
                  this.rowOperation(this.MatrizA, this.MatrizB, [indexRow, indexRow+1], [this.MatrizA[indexRow+1][indexColumn]*signo,this.MatrizA[indexRow][indexColumn]])
                }else if(indexRow== this.MatrizA.length-1){
                  if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==1 && Math.sign(this.MatrizA[0][indexColumn])==1){
                    signo=-1
                  }else if(Math.sign(this.MatrizA[indexRow][indexColumn]) ==-1 && Math.sign(this.MatrizA[0][indexColumn])==-1){
                    signo=-1
                  }
                  this.rowOperation(this.MatrizA, this.MatrizB, [indexRow, 0], [this.MatrizA[0][indexColumn]*signo, this.MatrizA[indexRow][indexColumn]])
                }
              }
            }              
          }
          this.rowOperationDivided(this.MatrizA, this.MatrizB);

        this.showArray(this.MatrizA);
        console.log('');
        this.showArray(this.MatrizB);

       }

    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.container{
   display: flex;
   justify-content: center;
}
.divhijo{
    margin: 10px;
}
</style>
