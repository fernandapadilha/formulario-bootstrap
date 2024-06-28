<script setup>
  import { ref } from 'vue'

  const mostrarResultado = ref(false)

  const nome = ref('');
  const email = ref('');
  const senha = ref('');
  const confirmarSenha = ref('');
  const endereco = ref('');
  const cidade = ref('');
  const estado = ref('');
  const hobbie = ref('');
  const linguagemProgramacao = ref('');
  const biografia = ref('');
  /* const confirmacao = ref(false);

  function enviarFormulario() {
    if (validarFormulario()) {
      confirmacao.value = true;
    } 
  }

  function validarFormulario() {
    if (nome.value.length < 3) return false;
    if (!email.value.includes('@')) return false;
    if (senha.value != confirmarSenha.value) return false;
    
  } */

</script>

<template>
  <div class="titulo">
    <h1>Formulário de Cadastro de Produtos</h1>
  </div>
  

  <div class="container d-flex flex-row gap-3">
    <div class="formulario">
      <h2>Cadastro</h2>

      <div class="form-group">
        <label for="">Nome:</label>
        <input class="form-control" type="text" v-model="nome" />
      </div>

      <div class="form-group">
        <label for="">Email:</label>
        <input class="form-control" type="text" v-model="email" />
      </div>

      <div class="form-group">
        <label for="">Senha:</label>
        <input class="form-control" type="password" v-model="senha"/>
      </div>

      <div class="form-group">
        <label for="">Confirmação de senha:</label>
        <input class="form-control" type="password" v-model="confirmarSenha"/>
      </div>

      <div class="form-group">
        <label for="">Endereço:</label>
        <input class="form-control" type="text" v-model="endereco"/>
      </div>

      <div class="form-group">
        <label for="">Cidade:</label>
        <input class="form-control" type="text" v-model="cidade"/>
      </div>

      <div class="form-group">
        <label for="estado">Estado:</label>
        <select class="form-control" name="estado" id="estado" v-model.number.lazy="estado">
          <option value="ac">Acre (AC)</option>
          <option value="al">Alagoas (AL)</option>
          <option value="ap">Amapá (AP)</option>
          <option value="am">Amazônas (AM)</option>
          <option value="ba">Bahia (BA)</option>
          <option value="ce">Ceará (CE)</option>
          <option value="df">Distrito Federal (DF)</option>
          <option value="es">Espírito Santo (ES)</option>
          <option value="go">Goiás (GO)</option>
          <option value="ma">Maranhão (MA)</option>
          <option value="mg">Minas Gerais (MG)</option>
          <option value="ms">Mato Grosso do Sul (MS)</option>
          <option value="mt">Mato Grosso (MT)</option>   
          <option value="pa">Pará (PA)</option>
          <option value="pb">Paraíba (PB)</option>
          <option value="pe">Pernambuco (PE)</option>
          <option value="pr">Paraná (PR)</option>
          <option value="pi">Piauí (PI)</option>
          <option value="rj">Rio de Janeiro (RJ)</option>
          <option value="rn">Rio Grande do Norte (RN)</option>
          <option value="ro">Rondônia (RO)</option>
          <option value="rr">Roraima (RR)</option>
          <option value="rs">Rio Grande do Sul (RS)</option>
          <option value="sc">Santa Catarina (SC)</option>
          <option value="se">Sergipe (SE)</option>
          <option value="sp">São Paulo (SP)</option>
          <option value="to">Tocantins (TO)</option>
        </select>
      </div>
    
      <div class="form-group">
        <label for="">Hobbie:</label>
        <input class="form-control" type="text" v-model="hobbie"/>
      </div>
    
      <div>
        <label for="linguagemProgramacao">Linguagem de programação:</label>
        <input class="form-control" type="text" id="linguagemProgramacao" v-model.number.lazy="linguagemProgramacao">
      </div>

      <div>
        <label for="biografia">Biografia:</label>
        <textarea class="form-control" name="biografia" id="biografia" cols="30" rows="10" v-model.number.lazy="biografia"></textarea> 
      </div>
      
      <div>
        <button type="button" class="btn btn-primary" @click="mostrarResultado = !mostrarResultado" >Mostrar</button>
      </div>

    </div>

    <div v-if="mostrarResultado" class="resultado">
      <h2>Resultado</h2>
      <p>Nome: {{ nome }}</p>
      <p>Email: {{ email }}</p>
      <p>Senha: {{ senha }}</p>
      <p>Estado: {{ estado }}</p>
      <p>Cidade: {{ cidade }}</p>
      <p>Endereço: {{ endereco }}</p>
      <p>Hobbies: {{ hobbie }}</p>
      <p>Linguagem de programação: {{ linguagemProgramacao }}</p>
      <p>Biografia: {{ biografia }}</p>
    </div>
      
  </div>
  
</template>

<style scoped>

  .titulo {
    text-align: center;
    padding: 3rem 0;
  }

  .formulario, .resultado {
    width: 48%;
    border-radius: 10px;
    padding: 20px;
    margin: 0 0 5rem;
  }

  .formulario {
    background-color: rgb(179, 214, 243);
  }

  .resultado {
    background-color: #dac2eb;
  }

  button {
    margin: 1rem 0;
  }

</style>
