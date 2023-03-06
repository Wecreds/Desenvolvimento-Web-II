<!--  
<script> 

export default{
  data(){
    return {
      contador: 0
    }
  },

methods: {
    incrementarContador(){
      this.contador++
    },
    decrementarContador(){
      if (this.contador > 0){
        this.contador--
      } else {
        alert("O contador nao pode ser menor que zero")
      }
    },
    resetarContador(){
      this.contador = 0;
    }
  }
}

</script> 
-->

<script setup>
import { ref } from 'vue'

const contador = ref(0);

function incrementarContador(){
  contador.value++
}

function decrementarContador(){
  if(contador.value > 0){
    contador.value--
  }else {
    alert("O contador não pode ser menor que zero.")
  }
}

function resetarContador(){
  contador.value = 0;
}


</script>

<template>

<button @click="incrementarContador">+</button>
<button @click="decrementarContador">-</button>
<button @click="resetarContador">Resetar</button>
o contador é {{ contador }}

</template>
  
<style scoped>

button{
  font-weight: bold;
}

</style>
