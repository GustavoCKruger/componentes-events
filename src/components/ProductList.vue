<script setup>
const props = defineProps(['produtos'])
</script>

<template>

    <table>
        <thead>
            <tr>
                <th>ID</th>
                <th>Nome</th>
                <th>Preço</th>
                <th>Ações</th>
            </tr>
        </thead>

        <body>
            <tr v-for="produto in produtos" :key="produto.id">
                <td>{{ produto.id }}</td>
                <td>{{ produto.nome }}</td>
                <td>{{ produto.preco }}</td>
                <td @click="$emit('excluir', produto.id)">X</td>
            </tr>
        </body>
    </table>
</template>

<style scoped></style>