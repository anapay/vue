<template>
  <div id="app">
    <h3>Cadastro: </h3>
    <input type="text" placeholder="nome" v-model="nomeField"> <br>
    <input type="text" placeholder="email" v-model="emailField"> <br>
    <input type="number" placeholder="idade" v-model="idadeField"> <br>
    <button @click="cadastrarUsuario"> Cadastrre-se! </button>
    <hr>
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h3>{{ index +1 }}</h3>
      <Visitantes :cliente="cliente" />
    </div>
  </div>
</template>

<script>
import Visitantes from "./components/Visitantes";
export default {
  name: "App",
  data() {
    return {
      nomeField: "",
      emailField: "",
      idadeField: 0,
      clientes: [
        {
          id: 1,
          nome: "Cliente1",
          email: "Cliente1@gmail.com",
          idade: 23
        },
        {
          id: 4,
          nome: "Cliente2",
          email: "Cliente2@gmail.com",
          idade: 26
        }
        
      ]
    };
  },
  components: {
    Visitantes,
  },
  methods: {
    cadastrarUsuario: function() {
      if(this.nomeField == "" || this.nomeField == " "  || this.nomeField.length < 3){
        console.log("Erro de validação.");
      }else {
        this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.idadeField, id: Date.now()})
      this.nomeField = "";
      this.emailField = "";
      this.idadeField = 0;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
