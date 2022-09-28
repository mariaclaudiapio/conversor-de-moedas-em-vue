<template>
  <div class="container">
    <h1>Conversor de moedas</h1>
    <h2>Reais para Dólares</h2>
    <img class="imagem" src="./assets/money.svg" />
    <label for="quantidade-reais">Quantidade em reais:</label>
    <input id="quantidade-reais" type="number" 
      v-model="quantidadeReais" placeholder="digite valor no formato XX.XX"/>
    <label for="cotacao-dolar">Cotação do dólar:</label>
    <input id="cotacao-dolar" type="number" 
      v-model="cotacaoDolar" placeholder="digite valor no formato XX.XX"/>
    <div class="botao">
      <button class="botao__limpar">Limpar</button>
      <button class="botao__calcular" @click="calculo">Calcular</button>
    </div>
    <div class="resultado-calculo">
      <p>Com R${{ quantidadeReais }} é possível comprar <strong>U$${{ quantidadeDolares }}</strong>
      a R${{ cotacaoDolar }} cada.</p>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      quantidadeReais: null,
      cotacaoDolar: null,
      quantidadeDolares: null
    }
  },
  methods: {
    calculo: function() {
      this.quantidadeDolares = (this.quantidadeReais / this.cotacaoDolar).toFixed(2)
      console.log(this.quantidadeDolares)      
    }
  }
}
</script>

<style>
html {
  background-color: #00BFA6;
}

h1,
h2,
strong {
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
  width: 35vw;
  padding: .5em;
  margin: .5em;
  align-self: center;
}

input:active,
input:hover {
  box-shadow: 5px 5px 5px #00BFA6;
}

.botao {
  display: inline;
}

.botao__limpar:active,
.botao__calcular:active {
  background-color: #FFFFFF;
  border: solid 1px #00BFA6;
  color: #00BFA6;
}

.botao__limpar,
.botao__calcular {
  padding: .7em;
  margin: 1.5em 0 1em;
  background-color: #00BFA6; 
  color: #FFFFFF;
  font-size: 16px;
  border: none;
  border-radius: 5px;  
}

.botao__limpar {
  margin-right: 1em;
}

.resultado-calculo {
  width: 60vw;
  margin-bottom: 1.5em;
  align-self: center;
  font-size: 18px;
}
</style>
