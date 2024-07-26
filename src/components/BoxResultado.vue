<script setup>
  defineProps(['perfil', 'validacao']);
</script>

<template>
  <section v-if="validacao" class="resultado">
    <h2>Resultado</h2>
    <p>Nome: {{ perfil.nome }}</p>
    <p>Email: {{ perfil.email }}</p>
    <p>Senha: {{ perfil.senha }}</p>
    <p>Estado: {{ perfil.estado }}</p>
    <p>Cidade: {{ perfil.cidade }}</p>
    <p>Endereço: {{ perfil.endereco }}</p>
    <p>Hobbies: {{ perfil.hobbie }}</p>
    <p>Linguagem de programação: {{ perfil.linguagemProgramacao }}</p>
    <p>Biografia: {{ perfil.biografia }}</p>
    <div>
      <button type="button" class="btn btn-primary" @click="validacao.value = !validacao.value"> Voltar </button>
    </div>
  </section>
</template>

<style scoped>
.resultado {
  width: 48%;
  border-radius: 10px;
  padding: 20px;
  margin: 0 0 5rem;
  background-color: #dac2eb;
}
</style>
