<script setup>
import { ref } from 'vue'
const produtos = [
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
]
const novoProduto = ref('')
function adicionar() {
  produtos.value.push(novoProduto.value)
  novoProduto.value = ''
}
function remover(index) {
  produtos.value.splice(index, 1)
}
</script>

<template>
  <div class="produtos" v-for="produto in produtos" :key="produtos.id">
    <p>Id: {{ produto.id }}</p>
    <p>Nome: {{ produto.nome }}</p>
    <p>Preço: {{ produto.preco }}</p>
    <p>Quantidade: {{ produto.quantidade }}</p>
  </div>
  <div class="adicionar">
    <input type="text" v-model="novoProduto">
    <button @click="adicionar">Adicionar</button>
    <ul>
      <li v-for="item in produtos">{{ item }}</li>
    </ul>
  </div>
  <div class="remover">
    <ul>
      <li v-for="(item, index) in produtos">{{ item }} <button @click="remover(index)">Remover</button></li>
    </ul>
  </div>
</template>

<style scoped></style>
