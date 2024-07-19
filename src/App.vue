<script setup>
import { ref } from 'vue'
import ProductList from './components/ProductList.vue'
import ProductAdd from './components/ProductAdd.vue'
const produtos = ref([
  {id: 1, nome: 'Produto 1', preco: 9.99},
  {id: 2, nome: 'Produto 2', preco: 19.99},
  {id: 3, nome: 'Produto 3', preco: 29.99},
  {id: 4, nome: 'Produto 4', preco: 39.99},
  {id: 5, nome: 'Produto 5', preco: 49.99},
])
function excluirProduto(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id);
  produtos.value.splice(index, 1);
}
function excluirTudo() {
  produtos.value = [];
}
function adiconarProduto(produto) {
  produto.id = proxID.value;
  produtos.value.push(produto);
  proxID.value++;
}
</script>

<template>
<ProductAdd  @salvar="adiconarProduto" />
<h1>Meus produtos</h1>
<product-list :produtos="produtos" @excluir="excluirProduto" @excluirTudo="excluirTudo" />
</template>

<style scoped>
</style>
