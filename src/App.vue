<script setup>
import { ref } from "vue";
import ProductList from '@/components/ProductList.vue'
import ProductAdd from '@/components/ProductAdd.vue'

const produtos = ref([
  { id: 1, nome: 'produto A', preco: 199.99 },
  { id: 2, nome: 'produto B', preco: 299.99 },
  { id: 3, nome: 'produto C', preco: 399.99 },
  { id: 4, nome: 'produto D', preco: 190.99 },
  { id: 5, nome: 'produto E', preco: 290.99 },
  { id: 6, nome: 'produto F', preco: 390.99 },
])

const proxID = ref(6)

function excluirProduto(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1);
}

function adicionarProduto(produto) {
  produto.id = proxID.value
  produtos.value.push(produto)
  proxID.value++
}
</script>

<template>
  <h1>Meus produtos</h1>
  <ProductAdd @salvar="adicionarProduto" />
  <ProductList :produtos="produtos" @excluir='excluirProduto' />

</template>

<style scoped></style>
