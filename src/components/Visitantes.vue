<template>
  <div :class="{'cliente': !isPremium, 'cliente-premium':isPremium}">
    <h2>Ficha do Cliente:</h2>
    <h3>Nome: {{cliente.nome}}</h3>
    <hr />
    <p>email: {{cliente.email | processarEmail}}</p>
    <hr />
    <p v-if="showIdade === true">Idade: {{cliente.idade}}</p>
    <p v-else>O usuário escondeu a idade!</p>

    <button @click="mudarCor($event)">Mudar Cor!</button>
    <button @click="emitirEventoDelete">Deletar!</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isPremium: false
    };
  },
  props: {
    cliente: Object,
    showIdade: Boolean
  },
  methods: {
    mudarCor: function($event) {
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    emitirEventoDelete: function() {
      console.log("Emitindo do filho");
      this.$emit("meDelete", {
        idDoCliente: this.cliente.id,
        curso: "em promoção",
        promoção: true,
        component: this
      });
    },
    filters:{
      processarEmail: function(value) {
        return value.toUpperCase();
      }
    }
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

