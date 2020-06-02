<template>
  <div class="pesquisa">
      <h3>Pesquisar Veículo</h3>
      <label>Placa:</label>
      <input type="text" placeholder="Informe a placa" maxlength="8" v-model="placa"><br>
      <button @click="pesquisar">Pesquisar</button>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            placa: ""
        }
    },
    methods: {
        pesquisar: function(){
            this.$store.state.infracoesVeiculo = this.$store.state.multas.filter(multa => multa.PLACA == this.placa)
            this.$router.push("/infracoes") 
        }
    }
}
</script>

<style>
    .pesquisa{
        border: 1px solid gray;
        width: 195px;
        height: 150px;
        margin: 10px auto;
    }

    h3{
        color: darkred;
        text-align: center;
    }

    input{
        margin-left: 8px;
    }

    button{
        margin-left: 110px;
        margin-top: 10px;
    }

    label{
        color: gray;
    }
</style>