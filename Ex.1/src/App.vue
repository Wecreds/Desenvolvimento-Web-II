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

/* a */
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
