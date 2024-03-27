<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Oi VueJs!')
const mostrasResultado = ref(false)

const produto = reactive({
  nome: '',
  preco: 0,
  quantidade: 0,
  categorias: [],
})

</script>

<template>
  <h1>{{ titulo }}</h1>
  <div class="container">
    <div class="formulario">
      <h2>Formulário</h2>
      <input type="text" v-model="titulo" />
      <h3>Informar Dados do Produto</h3>
    </div>
    <div class="row">
      <label for="">Nome:</label>
      <input type="text" v-model="produto.nome" />
    </div>
    <div class="row">
      <label for="">Preço:</label>
      <input type="text" />
    </div>
    <div class="row">
      <label for="">Quantidade:</label>
      <input type="text" />
    </div>
    <div class="row">
      <label for="">Categorias:</label>
      <input type="text" />
    </div>
    <button @click="mostrasResultado = !mostrasResultado">Mostrar</button>
    <div v-if="mostrasResultado" class="resultado">
      <h2>Dados do produto</h2>
      <p>Nome: {{ produto.nome }}</p>
      <p>Preço: {{ produto.preco }}</p>
      <p>Quantidade: {{ produto.quantidade }}</p>
      <p>Categorias: {{ produto.categorias }}</p>
      <p>{{ mostrasResultado }}</p>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 1rem;
}

.formulario,
.resultado {
  width: 45vw;
  min-height: 70vh;
  border-radius: 20px;
  padding: 20px;
}

.formulario {
  background-color: violet;
}

.formulario .row {
  width: 80%;
  margin: 1 .3rem 0;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.resultado {
  background-color: burlywood;
}
</style>
