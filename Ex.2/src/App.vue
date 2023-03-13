<script setup>

import { ref } from 'vue'

const nome = ref("João");
const idade = ref("25");
const novoNome = ref("");
const novoIdade = ref("");

function inverter(texto){
    return texto.split('').reverse().join('')
}

function saudacao(texto){
    return `Olá, ${texto}!`
}

function mudarNome(){
    if(novoNome.value === ""){
        alert("Você nao pode mudar para um nome vazio")
    } else {
    nome.value = novoNome.value
    novoNome.value = ""; 
    }
}

function mudarIdade(){
    idade.value = novoIdade.value
    novoIdade.value = "";
}
</script>

<template>

<div>
    <h1>Mostrando informações na tela</h1>
    <p>Nome: {{ nome }}</p>
    <p>Idade: {{ idade }}</p>
    <hr>
    <p>Para completar 50 anos faltam {{ 50 - idade }}</p>
    <p>O nome tem {{ nome.length }} caracteres.</p>
    <p>O nome invertido é {{ inverter(nome.toUpperCase()) }}</p>
    <hr>
    <p>Exemplo de saudação usando a função</p>
    <p>{{ saudacao(nome) }}</p>

    <input v-model="novoNome" type="text"> <br>
    <button @click="mudarNome">Clique aqui para mudar o nome.</button><br>

    <input v-model="novoIdade" type="number"><br>
    <button @click="mudarIdade">Clique aqui para mudar a idade.</button><br>
</div>    
</template>

<style scoped>

</style>
