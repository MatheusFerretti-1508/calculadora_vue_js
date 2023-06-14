<script setup>
const props = defineProps(['estado']);
</script>
<template>
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
</template>
<style scoped>
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
</style>