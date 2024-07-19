<script setup>
import { reactive } from 'vue'
const produto = reactive({
    nome: '',
    preco: ''
})
function salvar() {
    if (produto.nome === '' || produto.preco === '') {
        alert('Preencha todos os campos');
        return;
    }
    emit('salvar', {...produto});
}
</script>
<template>
    <div class="add-product">
        <form @submit.prevent="salvar">
            <div>
                <label for="nome">Nome</label>
                <input type="text" id="nome" v-model="produto.nome" />
            </div>
            <div>
                <label for="preco">Preço</label>
                <input type="number" id="preco" v-model="produto.preco" />
            </div>
            <button type="submit">Adicionar</button>
        </form>
    </div>
</template>
<style scoped>
.add-product {
    margin-top: 20px;
}
.add-product form {
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.add-product form div {
    display: flex;
    flex-direction: column;
}
.add-product form div label {
    font-weight: bold;
}
.add-product form div input {
    padding: 5px;
    border: 1px solid #ccc;
}
.add-product form button {
    padding: 5px;
    border: none;
    background-color: #007bff;
    color: white;
    cursor: pointer;
}
</style>