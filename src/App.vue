<template>
  <div id="app">
    <h1>Calculadora Aritmética Vue</h1>

    <div>
      <label for="numero1">Número 1:</label>
      <input v-model="numero1" type="number" id="numero1">
    </div>

    <div>
      <label for="operacao">Operação:</label>
      <select v-model="operacao" id="operacao">
        <option value="+">Adição</option>
        <option value="-">Subtração</option>
        <option value="*">Multiplicação</option>
        <option value="/">Divisão</option>
      </select>
    </div>

    <div>
      <label for="numero2">Número 2:</label>
      <input v-model="numero2" type="number" id="numero2">
    </div>

    <div>
      <h2>Resultado: {{ resultado }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
    };
  },
  computed: {
    resultado() {
      switch (this.operacao) {
        case '+':
          return this.numero1 + this.numero2;
        case '-':
          return this.numero1 - this.numero2;
        case '*':
          return this.numero1 * this.numero2;
        case '/':
          return this.numero1 / this.numero2;
        default:
          return 0;
      }
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}

label {
  margin-right: 10px;
}

input, select {
  margin-bottom: 10px;
  padding: 5px;
}
</style>
