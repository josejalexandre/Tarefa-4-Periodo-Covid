<template>
  <div id="infracoes">
      <div v-for="(infracao, index) in infracoes" :key="index">
          <label for="data">Data: </label>
          <input id="data" type="text" :value="infracao.DADOS_INFRACAO.DATAHORA"><br>
          <label for="placa">Placa:</label>
          <input id="placa" type="text" :value="infracao.PLACA"><br>
          <label for="placa">Local:</label>
          <input id="local" type="text" :value="infracao.LOCALIDADE"><br>
          <label for="placa">Tipo:</label>
          <input id="tipo" type="text" :value="infracao.DADOS_INFRACAO.TIPO"><br>
          <label for="placa">Valor:</label>
          <input id="valor" type="text" :value="infracao.DADOS_INFRACAO.VALOR"><br>
          <br><label id="mensagem" v-if="infracao.DADOS_INFRACAO.TIPO == 'VELOCIDADE'">Velocidade Máxima da Pista: <strong> {{ infracao.DADOS_INFRACAO.VEL_MAXIMA }}km/h </strong> </label><br>        
      </div>
      <button id="btnNova" @click="consultar">Nova Consulta</button>
  </div>
</template>

<script>
export default {
    computed: {
        infracoes: function(){
            return this.$store.state.infracoesVeiculo
        }
    },
    methods: {
        consultar: function(){
            this.$router.push("/")
        }
    }
}
</script>

<style>
    #infracoes {
        border: 1px solid gray;
        width: 275px;
        height: 180px;
        margin: 10px auto;
        padding: 10px 10px 10px 10px;
    }

    label {
        margin: 0 10px;
    }

    #local {
        margin-left: -2px;
    }

    #tipo {
        margin-left: 5px;
    }

    #mensagem {
        color: darkred;
    }

    #btnNova{
        margin: 20px 0 0 135px;
    }
</style>