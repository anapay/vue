<template>
  <div id="app">
    <Visitantes :cliente="cliente1" :showIdade="true" />
    <Visitantes :cliente="cliente2" :showIdade="false" />
    <Visitantes :cliente="cliente3" :showIdade="true" />
  </div>
</template>

<script>
import Visitantes from "./components/Visitantes";
export default {
  name: "App",
  data() {
    return {
      cliente1: {
        nome: "Cliente1",
        email: "Cliente1@gmail.com",
        idade: 23
      },
      cliente2: {
        nome: "Cliente2",
        email: "Cliente2@gmail.com",
        idade: 26
      },
      cliente3: {
        nome: "Cliente3",
        email: "Cliente3@gmail.com",
        idade: 24
      }
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
