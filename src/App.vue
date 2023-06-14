<script setup>
import { reactive } from 'vue';
import Resumo from './components/Resumo.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

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
      case (estado.valores.valor1 == '0' || estado.valores.valor2 == '0'):
        return 0
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

  if (estado.valores.valor1 == 0 || estado.valores.valor2 == 0) {

  }
</script>

<template>
  <div class="container">
    <Resumo />
    <Formulario :estado="estado" />
    <Resultado :operacao="operacao" :troca-filtros="trocaFiltros()" />
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
</style>
