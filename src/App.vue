<script setup>
import { ref } from 'vue'
const produtos = ref([
  {
    id: 1,
    nome: 'Camiseta',
    preco: 49.90,
    quantidade: 1

  },
  {
    id: 2,
    nome: 'Calça',
    preco: 99.90,
    quantidade: 1

  },
  {
    id: 3,
    nome: 'Meia',
    preco: 9.90,
    quantidade: 1
  },
  {
    id: 4,
    nome: 'Sapato',
    preco: 199.90,
    quantidade: 1

  },
  {
    id: 5,
    nome: 'Boné',
    preco: 29.90,
    quantidade: 1

  },
  {
    id: 6,
    nome: 'Óculos',
    preco: 99.90,
    quantidade: 1

  },
  {
    id: 7,
    nome: 'Relógio',
    preco: 299.90,
    quantidade: 1

  },
  {
    id: 8,
    nome: 'Bermuda',
    preco: 79.90,
    quantidade: 1

  },
  {
    id: 9,
    nome: 'Cueca',
    preco: 19.90,
    quantidade: 1

  },
  {
    id: 10,
    nome: 'Meia',
    preco: 9.90,
    quantidade: 1

  }
])
const novoProduto = ref('')
 
function incrementar(index) {
    listaCompras.value[index].quantidade++
  }
function adicionar() {
  produtos.value.push(novoProduto.value)
  novoProduto.value = ''
}
function remover(index) {
  produtos.value.splice(index, 1)
}
</script>

<template>
  <div class="listaProdutos">
    <div class="produtos" v-for="produto in produtos" :key="produtos.id">
      <p>Id: {{ produto.id }}</p>
      <p>Nome: {{ produto.nome }}</p>
      <p>Preço: {{ produto.preco }}</p>
      <p>Quantidade: {{ produto.quantidade }}</p>
      <div >
        <button class="botoes" @click="adicionar(index)">Adicionar</button>
        <button class="botoes" @click="incrementar(index)">+</button>
        <button class="botoes" @click="remover(index)">-</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.listaProdutos {
  display: grid;
  grid-template-columns: 1fr 1fr;
  width: 60%;
  margin: 0 auto;
  gap: 20px;
}
.produtos{
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: rgb(46, 45, 141);
  border-radius: 10px;
  color: aliceblue;
  background-image: linear-gradient(to right, rgb(15, 17, 129), black);
}
.botoes{
  border-radius: 10px;
  background-color: rgb(119, 28, 28);
  color: white;

}
</style>