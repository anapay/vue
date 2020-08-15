<template>
  <div id="app">
    <div v-for="(cliente,index) in clientes" :key="cliente.id">
      <h3>{{ index +1 }}</h3>
      <Visitantes :cliente="cliente" />
      <hr />
      <h4>Edição:</h4>
      <input type="text" v-model="cliente.nome" />
      <input type="text" v-model="cliente.email" />
    </div>
  </div>
</template>

<script>
import Visitantes from "./components/Visitantes";
export default {
  name: "App",
  data() {
    return {
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
        },
        {
          id: 6,
          nome: "Cliente3",
          email: "Cliente3@gmail.com",
          idade: 24
        },
        {
          id: 9,
          nome: "Cliente4",
          email: "Cliente4@gmail.com",
          idade: 24
        }
      ]
    };
  },
  components: {
    Visitantes
  }
};
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
