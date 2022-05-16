<template>
  <div class="home">
    <h1 class="titulo">Problema de Monty Hall</h1>
        <div class="form">
      <div v-if="!iniciado">
        <label for="quantidadePortas">Quantas portas gostaria de colocar em jogo? </label>
        <input type="text" name="quantidadePortas" id="quantidadePortas"
        v-model.number="quantidadePortas" size="2">
      </div>
      <div v-if="!iniciado">
        <label for="portaSelecionada">Qual a porta premiada?</label>
        <input type="text" name="portaSelecionada" id="portaSelecionada" size="2"
        v-model.number="portaSelecionada">
      </div>
      <div>
        <button type="button" v-if="!iniciado" @click="iniciado = true">Iniciar Desafio</button>
        <button type="button" v-if="iniciado" @click="iniciado = false">Reiniciar Desafio</button>
      </div>
    </div>
    <div class="portas" v-if="iniciado">
      <div v-for="i in quantidadePortas" :key="i">
    <Porta :numero="i" :temPremio="i == portaSelecionada" />

      </div>
    </div>
  </div>
</template>

<script>

import Porta from '../components/Porta.vue'
export default {
  components: {
    Porta
  },
    data(){
    return{
      iniciado: false,
      quantidadePortas: 3,
      portaSelecionada: null
    }
  }
}
</script>

<style scoped>
  .titulo{
    color: #ffffff;
    padding: 25px;

    border: 5px solid #ffffff;
    margin-bottom: 50px;
    text-align: center;
  }

  /* form */
  .form{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-bottom: 50px;
    color: white;
  }

  .form, .form input, .form button{
    margin-bottom: 20px;
    margin-left: 10px;
    font-size: 1.5rem;
  }

  .portas{
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
  }

</style>
