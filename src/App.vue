<template>
  <div class="container">
    <h1>Conversor de moedas</h1>
    <h2>Reais para Dólares</h2>
    <img class="imagem" src="./assets/money.svg" />
    <label for="quantidade-reais">Quantidade em reais:</label>
    <input id="quantidade-reais" type="number" v-model="quantidadeReais" 
      v-bind:disabled="quantidadeDolares"
      placeholder="digite valor no formato XX.XX"/> 
    <label for="cotacao-dolar">Cotação do dólar:</label>
    <input id="cotacao-dolar" type="number" v-model="cotacaoDolar"
      v-bind:disabled="quantidadeDolares" 
      placeholder="digite valor no formato XX.XX"/>
    <div class="botao" v-if="!quantidadeDolares">
      <button class="botao__calcular" @click="calcular">Calcular</button>
      <button class="botao__limpar" @click="limpar">Limpar</button>
    </div>
    <div class="resultado-calculo" v-if="quantidadeDolares">
      <p>Com R${{ quantidadeReais }} é possível comprar <strong>U$${{ quantidadeDolares }}</strong>
      a R${{ cotacaoDolar }} cada.</p>
      <button class="botao__calcular-novamente" @click="limpar" label="Calcular Novamente">Calcular Novamente</button>
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
    calcular: function() {
      this.quantidadeDolares = (this.quantidadeReais / this.cotacaoDolar).toFixed(2)
      console.log(this.quantidadeDolares)      
    },
    limpar: function() {
      this.quantidadeReais = null,
      this.cotacaoDolar = null,
      this.quantidadeDolares = null
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
.botao__calcular,
.botao__calcular-novamente {
  padding: .7em;
  margin: 1.5em 0 1.5em;
  background-color: #00BFA6; 
  color: #FFFFFF;
  font-size: 16px;
  border: none;
  border-radius: 5px;  
}

.botao__calcular {
  margin-right: 1em;
}

.botao__calcular-novamente {
  width: 25vw;
}

.resultado-calculo {
  width: 60vw;
  margin-bottom: 1.5em;
  align-self: center;
  font-size: 18px;
}

@media (max-width: 800px) {
  .container {
    margin: 1rem;
  }

  .imagem {
  width: 30vw;
  }

  input {
    width: 60vw;
    padding: 1em;    
  }

  .botao__calcular-novamente {
    width: 50vw;
  }  
}
</style>
