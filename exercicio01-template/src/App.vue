<script setup>
    const nome = 'agatha'
    const idade = 15

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome}!`
    }

    import {ref} from 'vue'

const contador = ref(0);

function incrementar(){
  contador.value++
}

function decrementar(){
  if(contador.value > 0){
    contador.value--;
  }
}

function reiniciar(){
   contador.value = 0;
}
</script>

<template>
    <div class="info">
        <h1>Exemplo 1 - Mostrando informações na tela</h1>
        <p>Nome: {{ nome }} </p>
        <p>Idade: {{ idade }}  anos</p>
        <hr />
        <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos</p>
        <p>O nome tem {{ nome.length }}  caracteres</p>
        <p>O nome invertido é: {{ inverter(nome).toUpperCase() }} </p>
        <hr />
        <p> Exemplo de saudação usando função</p>
        <p> {{ saudacao() }}  </p>
    </div>
    <div class="contador">
      <h1>Contador</h1>
    <p> {{ contador }} </p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decrementar">Decrementar</button>
    <button @click="reiniciar">Reiniciar</button>
    <div :style="{backgroundColor : contador > 10 ? 'green' : 'red' }">

    <p  v-if = "contador > 10 "> valor maior que 10 </p>
    <p v-else >valor menor que 10 </p>
    </div>
    </div>
</template>

<style scoped>
.info,.contador {
  background-color: rgba(35,12,22,1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}

h1 {
  color: rgb(228, 219, 219);
  font-weight: bold;
  font-size: 1.5em;
}

button {
    margin: 10px;
    padding: 10px;
    border: 0;
    border-radius: 5px;
    background-color: lightblue;
    color: black;
    font-weight: bold;
    cursor: pointer;
  }

  button:hover {
    background-color: blue;
  }

  div {
    margin: 10px 0;
    padding: 10px;
    border-radius: 5px;
    color: rgb(233, 225, 225);
    font-weight: bold;
    background-color: rgba(35,12,22,1);
  }
</style>

