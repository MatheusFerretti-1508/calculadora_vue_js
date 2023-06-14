<script setup>
    const props = defineProps([]);
</script>
<template>
    <div class="titulo-e-resumo-breve">
        <h1 class="titulo-e-resumo-breve__title">
            Calculadora Aritimética
        </h1>
        <p class="titulo-e-resumo-breve__txt">
            Nos campos encontrados abaixo, digite os números com os quais deseja trabalhar, depois escolha a operação
            desejada.
        </p>
    </div>
</template>
<style scoped>
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
</style>