<script setup>
const props = defineProps(['operacao', 'trocaFiltros']);
</script>
<template>
    <div class="resultado">
        <p @change="evento => operacao.filtro">
            {{ trocaFiltros }}
        </p>
    </div>
</template>
<style scoped>
.resultado {
    margin-top: 48px;
    font-size: 36px;
    display: flex;
    justify-content: center;
}
</style>