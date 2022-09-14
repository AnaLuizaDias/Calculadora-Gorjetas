<script>
export default {
  data() {
    return {
      pessoas: "",
      conta: "",
      gorjeta: "",
    };
  },
  methods: {
    calcular() {
      const pessoas = this.pessoas;
      const conta = this.conta;
      const gorjeta = this.gorjeta;

      let valor_gorjeta = 0;
      let resultado = {};

      valor_gorjeta = conta * (gorjeta / 100.0);
      resultado = (conta + valor_gorjeta) / pessoas;

      document.getElementById("resultado").innerHTML = resultado;
    },
  },
};
</script>

<template>
  <div class="conteudo">
    <h1>calculadora de gorjetas</h1>

    <label>
      <p>Qual o valor da conta?</p>
      <input type="number" v-model="conta" id="conta" />
    </label>

    <label>
      <p>Qual foi a qualidade do serviço?</p>
      <select v-model="gorjeta">
        <option value="30">30% Excepcional</option>
        <option value="25">25% Muito bom</option>
        <option value="20">20% Bom</option>
        <option value="15">15% Ok</option>
        <option value="10">10% Ruim</option>
        <option value="5">5% Péssimo</option>
      </select>
    </label>

    <label
      ><p>Quantas pessoas estão dividindo a conta?</p>
      <input type="number" v-model="pessoas" id="pessoas" />
    </label>
    <button type="button" @click="calcular">
      R$:
      <span id="resultado"></span>
    </button>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Raleway:wght@200&display=swap");

h1 {
  color: rgb(74, 45, 106);
  font-family: "Raleway", sans-serif;
  font-size: 50px;
}
button {
  background-color: rgb(74, 45, 106);
  border: rgb(74, 45, 106);
  color: white;
  height: 30px;
  width: 100px;
  border-radius: 10px;
  margin: 10px;
}
</style>
