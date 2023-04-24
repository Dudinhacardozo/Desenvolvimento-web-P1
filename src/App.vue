<script setup>
import { ref } from 'vue'

const nome = ref("")
const Email = ref("")
const senha = ref("")
const confirmarsenha = ref("")
const endereço = ref("")
const Cidade = ref("")
const DatadeNascimento = ref("")
const estado = ref("")
const idade = ref("")
const biografia = ref("")
const hobbies = ref("")
const lingprog = ref("")
const erro = ref("")
const exibir = ref(false)
function confirmacao (){
  if(senha.value != confirmarsenha.value){
    alert('A senha não confere')
    console.log(exibir.value)

    exibir.value = false
  } else{
    console.log("Certo")

    exibir.value = true
  }
}
</script>
<template>
  <form class="layout"
  @submit.prevent="">
    <h2> Preencha o formulário abaixo</h2>

    <div class="form-row">
      <div class="cor col-md-4 mb-3">
        <label for="validationDefault01">Nome:</label>
        <input type="text" v-model="nome" class="form-control" id="validationDefault01" placeholder="Nome" size="20"
          required>
      </div>
    </div>

    <div class="cor form-group col-md-6">
      <label for="inputEmail4">Email:</label>
      <input type="email" v-model="Email" class="form-control" id="inputEmail4" placeholder="Email" size="20" required>
    </div>

    <div class=" cor form-group mx-sm-3 mb-2">
      <label for="inputPassword2" class="sr-only">Senha</label>
      <input type="password" v-model="senha" class="form-control" id="inputPassword2" placeholder="Senha:" size="20"
        maxlength="20" minlength="3" required>

      <p>Confirmar senha: </p>
      <input type="password" v-model="confirmarsenha" name="senha2" placeholder="Confirmar Senha" size="20" maxlength="20"
        minlength="3" required>
    </div>

    <div class="cor form-group">
      <label for="inputAddress">Endereço:</label>
      <input type="text" v-model="endereço" class="form-control" id="inputAddress" placeholder="Rua dos Bobos, nº 0"
        size="20" required>
    </div>

    <div class="form-row">
      <div class="cor form-group col-md-6">
        <label for="inputCity">Cidade:</label>
        <input type="text" v-model="Cidade" class="form-control" id="inputCity" size="20" required>
      </div>

      <div class="cor">
        <label for="inputEmail4">Data de Nascimento:</label>
        <input id="date" v-model="DatadeNascimento" type="date" size="20">
      </div>

      <div class=" cor form-group col-md-4">
        <label for="inputEstado">Estado:</label>
        <select id="inputEstado" v-model="estado" class="form-control">
          <option selected>Escolher...</option>
          <option>Acre (AC)</option>
          <option>Alagoas (AL)</option>
          <option>Amapá (AP)</option>
          <option>Amazonas (AM)</option>
          <option>Bahia (BA)</option>
          <option>Ceará (CE)</option>
          <option>Distrito Federal (DF)</option>
          <option>Espírito Santo (ES)</option>
          <option>Goiás (GO)</option>
          <option>Maranhão (MA)</option>
          <option>Mato Grosso (MT)</option>
          <option>Mato Grosso do Sul (MS)</option>
          <option>Minas Gerais (MG)</option>
          <option>Pará (PA)</option>
          <option>Paraíba (PB)</option>
          <option>Paraná (PR)</option>
          <option>Pernambuco (PE)</option>
          <option>Piauí (PI)</option>
          <option>Rio de Janeiro (RJ)</option>
          <option>Rio Grande do Norte (RN)</option>
          <option>Rio Grande do Sul (RS)</option>
          <option>Rondônia (RO)</option>
          <option>Roraima (RR)</option>
          <option>Santa Catarina (SC)</option>
          <option>São Paulo (SP)</option>
          <option>Sergipe (SE)</option>
          <option>Tocantins (TO)</option>
        </select>
      </div>
    </div>

    <div class="cor">
      <p>
        <label for="age">Idade:</label>
        <input id="age" v-model="idade" type="number" name="age" min="18" max="60">
      </p>
    </div>

    <div class=" cor biografia">
      <h4>Insira uma Biografia:</h4>
      <textarea v-model="biografia" v-on:keypress="enviar = false"></textarea>
    </div>

    <div class=" cor hobies">
      <h4>Insira seus Hobbies:</h4>
      <textarea v-model="hobbies" v-on:keypress="enviar = false"></textarea>
    </div>

    <div class=" cor ling_prog">
      <h4>Diga quais são as suas linguagens de programação:</h4>
      <textarea v-model="lingprog" v-on:keypress="enviar = false"></textarea>
    </div>

    <div>
      <input type="submit" @click="confirmacao" value="Enviar Formulário">
    </div>

  </form>

  <div v-if="exibir">
    Nome: {{ nome }}
    Email: {{ Email }}
    senha: {{ senha }}
    confirmar senha: {{ confirmarsenha }}
    Endereço: {{ endereço }}
    Cidade:{{ Cidade }}
    Data de Nascimento:{{ DatadeNascimento }}
    Estado:{{ estado }}
    idade:{{ idade }}
    biografia:{{ biografia }}
    hobies:{{ hobbies }}  
    Línguagem programação:{{ lingprog }}

  </div>
</template>
<style scoped>
.layout {
  background-color: #FF69B4;
  border-radius: 5px;
  border-color: black;
  border-style: solid;
  color: white;
  padding: 10px;
}

.cor {
  color: black;
  font-family: Arial, Helvetica, sans-serif;

}

h2 {
  background-color: #FF1493;
  color: white;
  text-align: center
}
</style>