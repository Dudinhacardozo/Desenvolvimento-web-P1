<script setup>
import { ref } from 'vue'
const email = ref('')
const senha = ref('')
const confirmaSenha = ref('')
const nome = ref('')
const nascimento = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref('')
const liguagensProg = ref('')
const biografia = ref('')
const enviar = ref(false)
const erro = ref('')

function confirmacao() {
  if (senha.value === confirmaSenha.value) {
    erro.value = "";
    return true;
  } else {
    erro.value = "A senha não confere!"
    return false
  }
}
</script>

<template>
  <div>
    <form class="formulario" @submit.prevent="enviar = confirmacao()">
      <h1>Faça seu login:</h1>
      <div class="nome">
        <h4>Nome Completo</h4>
        <input type="text" v-model="nome" v-on:keypress="enviar = false" placeholder="Nome " required>
      </div>
      <div class="email">
        <h4>Digite seu email</h4>
        <input type="email" v-model="email" v-on:keypress="enviar = false" placeholder="example@gmail" required>
      </div>
      <div class="senha">
        <h4>Crie sua senha</h4>
        <input type="password" v-model="senha" v-on:keypress="enviar = false" placeholder="senha" required>
      </div>
      <div class="confirmaSenha">
        <h4>Confirme sua senha</h4>
        <input type="password" v-model="confirmaSenha" v-on:keypress="enviar = false" placeholder="confirma senha"
          required>
      </div>
      <div class="nascimento">
        <h4>Sua data de nascimento</h4>
        <input type="date" v-model="nascimento" v-on:keypress="enviar = false" required>
      </div>
      <div class="cidade">
        <h4>Cidade</h4>
        <input type="text" v-model="cidade" v-on:keypress="enviar = false" placeholder="cidade" required>
      </div>
      <div class="estado">
        <h4>Estado</h4>
        <select v-model="estado" v-on:keypress="enviar = false" required>
          <option value="AC">Acre</option>
          <option value="AL">Alagoas</option>
          <option value="AP">Amapá</option>
          <option value="AM">Amazonas</option>
          <option value="BA">Bahia</option>
          <option value="CE">Ceará</option>
          <option value="ES">Espírito Santo</option>
          <option value="GO">Goiás</option>
          <option value="MA">Maranhão</option>
          <option value="MT">Mato Grosso</option>
          <option value="MS">Mato Grosso do Sul</option>
          <option value="MG">Minas Gerais</option>
          <option value="PA">Pará</option>
          <option value="PB">Paraíba</option>
          <option value="PR">Paraná</option>
          <option value="PE">Pernambuco</option>
          <option value="PI">Piauí</option>
          <option value="RJ">Rio de Janeiro</option>
          <option value="RN">Rio Grande do Norte</option>
          <option value="RS">Rio Grande do Sul</option>
          <option value="RO">Rondônia</option>
          <option value="RR">Roraima</option>
          <option value="SC">Santa Catarina</option>
          <option value="SP">São Paulo</option>
          <option value="SE">Sergipe</option>
          <option value="TO">Tocantins</option>
        </select>
      </div>
      <div class="hobbies">
        <h4>Informe seus Hobbies</h4>
      </div>
      <div class="lingprog">
      <h4>Informe sua linguagem de programação:</h4>
       <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
<label for="vehicle1">JavaScript</label>
<input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
<label for="vehicle2">Python</label>
<input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
<label for="vehicle3">Java</label> 
<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
<label for="vehicle1">PHP</label>
<input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
<label for="vehicle2"> C#</label>
<input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
<label for="vehicle3">C++</label>
 <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
<label for="vehicle1">TypeScript</label>
<input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
<label for="vehicle2">Ruby</label>
<input type="checkbox" id="vehicle3" name="vehicle3" value="Boat">
<label for="vehicle3">Swift</label>
</div>
      <div class="biografia">
        <h4>Escreva uma biografia</h4>
        <textarea name="Hobbies" v-model="biografia" cols="30" rows="5" v-on:keypress="enviar = false"></textarea>
      </div>
      <button type="submit">Enviar</button>
    </form>
    <p>{{ erro }}</p>
  </div>

  <div v-if="enviar" class="cadastro">
    <h1>Cadastro de perfil</h1>
    <p>Nome: {{ nome }}</p>
    <div class="email-atual">
      <p>Email: {{ email }}</p>
    </div>
    <div class="senha-atual">
      <p>Senha: {{ senha }}</p>
    </div>
    <div class="nascimento-atualizado">
      <p>Data de nascimento: {{ nascimento }}</p>
    </div>
    <div class="bairro-atual">
      <p>Bairro: {{ bairro }}</p>
    </div>
    <div class="numero-atual">
      <p>Número da casa: {{ numero }}</p>
    </div>
    <div class="complemento-atual">
      <p>Complemento: {{ complemento }}</p>
    </div>
    <div class="cidade-atual">
      <p>Cidade: {{ cidade }}</p>
    </div>
    <div class="estado-atual">
      <p>estado: {{ estado }}</p>
    </div>
    <div class="hobbies">
      <p>Hobbies: {{ hobbies }}</p>
    </div>
    <div class="linguagens">
      <p>Linguagens de programação: {{ liguagensProg }}</p>
    </div>
    <div class="bio">
      <p>Biografia: {{ biografia }}</p>
    </div>
  </div>
</template>

<style scoped>
.formulario {
  background-color:#B0C4DE	;
  border-radius: 30px;
  border-style: solid;
  padding: 10px;
}
</style>