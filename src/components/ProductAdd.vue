<script setup>
import { reactive } from 'vue'
const produto = reactive({
    nome: '',
    preco: '',
})

function salvar() {
    if (produto.nome === '' || produto.preco === '') {
        alert(`Todos os campos são obrigatórios`);
        return
    }

}
</script>

<template>
    <div class="form-add">
        <h3>Adicionar Produto</h3>
        <form @submit.prevent="">
            <input type="text" placeholder="Nome">
            <input type="text" placeholder="Preço">
            <button type="submit">Salvar</button>
        </form>
    </div>
</template>

<style scoped></style>