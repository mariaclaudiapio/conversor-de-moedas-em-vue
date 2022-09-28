<template>
  <div class="container">
    <h1>Conversor de moedas</h1>
    <h2>Reais para Dólares</h2>
    <img class="imagem" src="./assets/money.svg" />
    <label for="quantidade-reais">Quantidade em reais:</label>
    <input id="quantidade-reais" type="number" v-model="quantidadeReais" />
    <label for="cotacao-dolar">Cotação do dólar:</label>
    <input id="cotacao-dolar" type="number" />
    <div class="botao">
      <button class="botao__limpar">Limpar</button>
      <button class="botao__calcular">Calcular</button>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      quantidadeReais: null,
      cotacaoDolar: 0
    }
  }
}
</script>

<style>
html {
  background-color: #00BFA6;
}

h1,
h2 {
  color: #00BFA6;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.container {
  display: flex;
  flex-direction: column;
  justify-items: center;
  margin: 20vw;
  background-color: #FFFFFF;
  border-radius: 7px;  
}

.imagem {
  width: 20vw;
  align-self: center;
}

label {
  margin-top: 1em;
}

input {
  width: 50vw;
  padding: .5em;
  margin: .5em;
  align-self: center;
}

.botao {
  display: inline;
}

.botao__limpar,
.botao__calcular {
  padding: .5em;
  margin: 1em 0;
  background-color: #00BFA6; 
  color: #FFFFFF;
  border: none;
  border-radius: 5px;  
}

.botao__limpar {
  margin-right: 1em;
}
</style>
