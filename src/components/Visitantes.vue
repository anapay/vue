<template>
  <div :class="{'cliente': !isPremium, 'cliente-premium':isPremium}">
    <h2>Ficha do Cliente:</h2>
    <h3>Nome: {{cliente.nome}}</h3>
    <hr />
    <p>email: {{cliente.email}}</p>
    <hr />
    <p v-if="showIdade === true">Idade: {{cliente.idade}}</p>
    <p v-else> O usuário escondeu a idade!</p>
   
  </div>
</template>

<script>
export default {
  data() {
    return { 
      isPremium: false
    }
  },
  props: {

    cliente: Object,
    showIdade: Boolean


  }
};
</script>

<style scoped>
.cliente {
  background-color: rgb(190, 140, 175);
  color: rgb(104, 60, 77);
  max-width: 600px;
  height: 250;
  padding: 14px;
  margin-top: 15px;
}
.cliente-premium {
  background-color: black;
  color: rgb(190, 189, 88);
  max-width: 600px;
  height: 250;
  padding: 14px;
  margin-top: 15px;

}
</style>

