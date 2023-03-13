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
import { ref} from 'vue'

const contador = ref(0)
const definir = ref()

const incrementarContador = () => contador.value++

function decrementarContador() {
  if (contador.value > 0) {
    contador.value--
  } else {
    alert('O contador não pode ser menor que zero.')
  }
}
const alterarValor = () => (contador.value = definir.value)

function salvar() {
  localStorage.setItem('contador', (contador.value))
}

contador.value = (localStorage.getItem('contador'))

</script>

<template>
  <div>
    <button @click="incrementarContador">+</button>
    <button @click="decrementarContador">-</button>
    <button @click="resetarContador">Resetar</button> <br />
    o contador é {{ contador }} <br />
    <input type="number" v-model="definir" placeholder="Definir valor do contador." />
    <button @click="alterarValor()">Enviar</button>

    <div class="verde" v-if="contador > 10">O valor e maior que 10</div>
    <div class="vermelho" v-else>O valor e menor que 10</div>
    <button @click="salvar">Salvar valor do contador</button>
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
}

.verde {
  color: green;
}

.vermelho {
  color: red;
}
</style>
