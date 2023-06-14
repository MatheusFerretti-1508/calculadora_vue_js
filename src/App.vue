<script setup>
import { reactive } from 'vue';
import Resumo from './components/Resumo.vue'

  const estado = reactive({
    filtros: 'somar',
    valores: {
      valor1: 0,
      valor2: 0,
    }
    
  })
  const trocaFiltros = () => {
    const { filtros } = estado;

    switch (filtros) {
      case 'Subtração':
        return subtrair();
      case 'Multiplicação':
        return multiplicar();
      case 'Divisão': 
        return dividir();
      case 'Adição': 
        return somar();
    }
  }

  const multiplicar = (valor1, valor2) => {
    valor1 = estado.valor1;
    valor2 = estado.valor2;
    return valor1 * valor2;
  }   
  const dividir = (valor1, valor2) => {
    valor1 = estado.valor1;
    valor2 = estado.valor2;
    return valor1 / valor2;
  }   
  const subtrair = (valor1, valor2) => {
    valor1 = estado.valor1;
    valor2 = estado.valor2;
    return valor1 - valor2;
  }   
  const somar = (valor1, valor2) => {
    valor1 = parseInt(estado.valor1)
    valor2 = parseInt(estado.valor2)
    return valor1 + valor2;
  }   
</script>

<template>
  <div class="container">
    <!-- <div class="titulo-e-resumo-breve">
      <h1 class="titulo-e-resumo-breve__title">
      Calculadora Aritimética
      </h1>
      <p class="titulo-e-resumo-breve__txt">
        Nos campos encontrados abaixo, digite os números com os quais deseja trabalhar, depois escolha a operação desejada.
      </p>
    </div> -->
    <Resumo />
    <form>
      <input @keyup="evento => estado.valor1 = evento.target.value" type="number" placeholder="Digite o primeiro número">
      <input @keyup="evento => estado.valor2 = evento.target.value" type="number" placeholder="Digite o segundo número">
      <select @change="evento => estado.filtros = evento.target.value">
        <option>Adição</option>
        <option>Subtração</option>
        <option>Multiplicação</option>
        <option>Divisão</option>
      </select>
    </form>
    <div class="resultado">
      <p @change="evento => operacao.filtro">
        {{ trocaFiltros() }}
      </p>
    </div>
  </div>
</template>

<style scoped>
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  .container {
    max-width: 900px;
    padding: 20px;
    margin: 160px auto;
    background-color: rgba(0, 0, 0, .1);
    border-radius: 20px;
  }

  .titulo-e-resumo-breve {
    display: block;
  }
  .titulo-e-resumo-breve__title {
    display: flex;
    justify-content: center;
    margin-bottom: 8px;
  }
  .titulo-e-resumo-breve__txt {
    display: flex;
    justify-content: center;
    margin-bottom: 16px;
  }
  form {
    max-width: 600px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
  }
  input {
    max-width: 186px;
    padding: 8px;
    border-radius: 8px;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  select {
    border-radius: 8px;
    border: none;
  }
  .resultado {
    margin-top: 48px;
    font-size: 36px;
    display: flex;
    justify-content: center;
  }
</style>
