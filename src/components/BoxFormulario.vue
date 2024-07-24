<script setup>
    import { reactive } from 'vue';
    
    const perfil = reactive({
        nome: '',
        email: '',
        senha: '',
        confirmarSenha: '',
        endereco: '',
        cidade: '',
        estado: '',
        hobbie: '',
        linguagemProgramacao: '',
        biografia: '',
        estados: [
            { sigla: 'AC', nome: 'Acre' },
            { sigla: 'AL', nome: 'Alagoas' },
            { sigla: 'AP', nome: 'Amapá' },
            { sigla: 'AM', nome: 'Amazonas' },
            { sigla: 'BA', nome: 'Bahia' },
            { sigla: 'CE', nome: 'Ceará' },
            { sigla: 'DF', nome: 'Distrito Federal' },
            { sigla: 'ES', nome: 'Espírito Santo' },
            { sigla: 'GO', nome: 'Goiás' },
            { sigla: 'MA', nome: 'Maranhão' },
            { sigla: 'MT', nome: 'Mato Grosso' },
            { sigla: 'MS', nome: 'Mato Grosso do Sul' },
            { sigla: 'MG', nome: 'Minas Gerais' },
            { sigla: 'PA', nome: 'Pará' },
            { sigla: 'PB', nome: 'Paraíba' },
            { sigla: 'PR', nome: 'Paraná' },
            { sigla: 'PE', nome: 'Pernambuco' },
            { sigla: 'PI', nome: 'Piauí' },
            { sigla: 'RJ', nome: 'Rio de Janeiro' },
            { sigla: 'RN', nome: 'Rio Grande do Norte' },
            { sigla: 'RS', nome: 'Rio Grande do Sul' },
            { sigla: 'RO', nome: 'Rondônia' },
            { sigla: 'RR', nome: 'Roraima' },
            { sigla: 'SC', nome: 'Santa Catarina' },
            { sigla: 'SP', nome: 'São Paulo' },
            { sigla: 'SE', nome: 'Sergipe' },
            { sigla: 'TO', nome: 'Tocantins' }
        ]
    });
    

</script>

<template>
    <div class="formulario">
      <h2>Cadastro</h2>

      <div class="form-group">
        <label for="">Nome:</label>
        <input class="form-control" type="text" v-model="perfil.nome" />
      </div>

      <div class="form-group">
        <label for="">Email:</label>
        <input class="form-control" type="text" v-model="perfil.email" />
      </div>

      <div class="form-group">
        <label for="">Senha:</label>
        <input class="form-control" type="password" v-model="perfil.senha" />
      </div>

      <div class="form-group">
        <label for="">Confirmação de senha:</label>
        <input class="form-control" type="password" v-model="perfil.confirmarSenha" />
      </div>

      <div class="form-group">
        <label for="">Endereço:</label>
        <input class="form-control" type="text" v-model="perfil.endereco" />
      </div>

      <div class="form-group">
        <label for="">Cidade:</label>
        <input class="form-control" type="text" v-model="perfil.cidade" />
      </div>

      <div class="form-group">
        <label for="estado">Estado:</label>
        <select class="form-control" name="estado" id="estado" v-model="perfil.estado">
          <option v-for="estado in perfil.estados" :key="estado.sigla" :value="estado.sigla"> {{ estado.nome }} </option>
        </select>
      </div>

      <div class="form-group">
        <label for="">Hobbie:</label>
        <input class="form-control" type="text" v-model="perfil.hobbie" />
      </div>

      <div>
        <label for="linguagemProgramacao">Linguagem de programação:</label>
        <input class="form-control" type="text" id="linguagemProgramacao" v-model="perfil.linguagemProgramacao" />
      </div>

      <div>
        <label for="biografia">Biografia:</label>
        <textarea
          class="form-control"
          name="biografia"
          id="biografia"
          cols="30"
          rows="10"
          v-model="perfil.biografia"
        ></textarea>
      </div>

      <div>
        <button type="button" class="btn btn-primary" @click="$emit('envio', {...perfil})"> Mostrar </button>
      </div>
    </div>

</template>

<style scoped>
    .formulario {
        width: 48%;
        border-radius: 10px;
        padding: 20px;
        margin: 0 0 5rem;
        background-color: rgb(179, 214, 243);
    }

    button {
        margin: 1rem 0;
    }
</style>