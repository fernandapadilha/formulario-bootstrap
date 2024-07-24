<script setup>
import { ref } from 'vue'
import BoxFormulario from './components/BoxFormulario.vue'
import BoxResultado from './components/BoxResultado.vue'
const perfil = ref({ nome: 'eduardo' })

function enviarItem(item) {
  Object.assign(perfil.value, item)
}

/* const validacao = ref(false);

  function mostrarResultado() {
    if (nome.value == '' || email.value == '' || senha.value == '' || confirmarSenha.value == '' || 
    endereco.value == '' || cidade.value == '' || estado.value == '' || hobbie.value == '' || 
    linguagemProgramacao.value == '' || biografia.value == '') {
      alert('Preencha todos os campos');
    }
    else {
      
      if (nome.value.length < 5) alert('Preencha seu nome corretamente');
      else if (!email.value.includes('@')) alert('Preencha seu email corretamente');
      else if (senha.value.length < 4) alert('Senha fraca');
      else if (confirmarSenha.value != senha.value) alert('Campo "Confirmar senha" preenchido incorretamente');
      else validacao.value = true;

    }
  } */
</script>

<template>
  <div class="titulo">
    <h1>Formulário de Cadastro de Produtos</h1>
  </div>

  <BoxFormulario @envio="enviarItem" />
  <BoxResultado :perfil="perfil" />
</template>

<style scoped>
.titulo {
  text-align: center;
  padding: 3rem 0;
}
</style>
