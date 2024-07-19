<script setup>
  const props = defineProps(['produtos']);
</script>
<template>
    <h1>Meus produtos</h1>
    <table>
        <thead>
        <tr>
            <th>Nome</th>
            <th>Preço</th>
            <th>Ações</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="produto in produtos" :key="produto.id">
            <td>{{ produto.nome }}</td>
            <td>{{ produto.preco }}</td>
            <td><i class="mdi mdi-delete" @click="$emit('excluir', produto.id)"/></td>
        </tr>
        </tbody>  
    </table>
    <button @click="$emit('excluirTudo')">Excluir tudo</button>
</template>