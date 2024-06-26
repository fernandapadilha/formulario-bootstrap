<script setup>
  import { reactive, ref } from 'vue'

  const titulo = ref('Oi VueJs!')
  const mostrarResultado = ref(false)

  const categorias = [
    {
      id: 1,
      nome: 'Eletrônicos'
    },
    {
      id: 2,
      nome: 'Vestuário'
    },
    {
      id: 3,
      nome: 'Brinquedos'
    },
    {
      id: 4,
      nome: 'Móveis'
    },
    {
      id: 5,
      nome: 'Alimentos'
    },
    {
      id: 6,
      nome: 'Bebidas'
    },
    {
      id: 7,
      nome: 'Informática'
    },
    {
      id: 8,
      nome: 'Papelaria'
    }
  ]

  const produto = reactive({
    nome: '',
    preco: 0,
    quantidade: 0,
    medida: '',
    categorias: []
  })

  function formatarPreco(preco) {
    return `R$ ${preco.toFixed(2).replace('.', ',')}`
  }

  function buscarNome(id) {
    return categorias.find(categoria => categoria.id === id).nome
  }

</script>

<template>
  <div>
    <h1>Formulário de Cadastro de Produtos</h1>
  </div>

  <h1>{{ titulo }}</h1>
  <div class="container d-flex flex-row gap-3">
    <div class="formulario">
      <h2>Cadastro do produto</h2>
      <div class="form-group">
        <label for="">Nome:</label>
        <input class="form-control" type="text" v-model="produto.nome" />
      </div>
      <div class="form-group">
        <label for="">Preço (em reais):</label>
        <input
          class="form-control"
          type="number"
          step="0.01"
          v-model="produto.preco"
        />
      </div>
      <div class="form-group">
        <label for="">Quantidade:</label>
        <input
          class="form-control"
          type="number"
          v-model="produto.quantidade"
        />
      </div>

      <fieldset class="border p-1">
        <legend class="float-none w-auto p-2">Unidade de medida</legend>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            value="unidade"
            v-model="produto.medida"
          />
          Unidades
        </div>
        <div class="form-check form-check-inline">
          <input
            class="form-check-input"
            type="radio"
            value="peso"
            v-model="produto.medida"
          />
          Peso
        </div>
      </fieldset>
      <fieldset class="border p-1">
        <legend class="float-none w-auto p-2">Categorias</legend>
        <div
          class="form-check"
          v-for="categoria in categorias"
          :key="categoria.id"
        >
          <input
            class="form-check-input"
            type="checkbox"
            :value="categoria.id"
            v-model="produto.categorias"
          />
          {{ categoria.nome }}
        </div>
      </fieldset>
      <button
        type="button"
        class="btn btn-primary"
        @click="mostrarResultado = !mostrarResultado"
      >
        Mostrar
      </button>
    </div>
    <div v-if="mostrarResultado" class="resultado">
      <h2>Dados do produto</h2>
      <p>Nome: {{ produto.nome }}</p>
      <p>Preço: {{ formatarPreco(produto.preco) }}</p>
      <p>Em estoque: {{ produto.quantidade }}</p>
      <p>Medida: {{ produto.medida }}</p>
      <p>Categorias: {{ produto.categorias }}</p>
      <h4>Categorias selecionadas:</h4>
      <p v-for="categoria_id in produto.categorias" :key="categoria_id">
        - {{ buscarNome(categoria_id) }}
      </p>
    </div>
  </div>
  <div class="altera-titulo">
    <label>Informe um novo título </label>
    <input class="form-control" type="text" v-model="titulo" />
  </div>
</template>

<style scoped>
  .formulario,
  .resultado {
    width: 48%;
    border-radius: 20px;
    padding: 20px
  }

  .formulario {
    background-color: #d29696
  }

  .resultado {
    background-color: #98e0aa;
  }

  .altera-titulo {
    background-color: #98e0aa;
    margin: 1rem 2rem;
    border-radius: 20px;
    padding: .75rem;
  }
</style>
