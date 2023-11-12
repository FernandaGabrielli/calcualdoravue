<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: '+',
    };
  },
  methods: {
    validarNumeros() {
      // Certifique-se de que num1 e num2 sejam sempre positivos
      this.num1 = Math.max(0, this.num1);
      this.num2 = Math.max(0, this.num2);
    },
    calcular() {
      switch (this.operator) {
        case '+':
          return this.num1 + this.num2;
        case '-':
        return this.num1 - this.num2; 
        case '*':
          return this.num1 * this.num2;
        case '/':
          return this.num2 !== 0 ? this.num1 / this.num2 : 'Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>

<template>
  <div>
    <header>
      <h1>Calculadora utilizando Vue.js</h1>
    </header>

    <div class="calculator-container">
      <label for="num1"></label>
      <input v-model="num1" type="number" id="num1" @input="validarNumeros">

      <label for="operator"></label>
      <select v-model="operator" id="operator">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>

      <label for="num2"></label>
      <input v-model="num2" type="number" id="num2" @input="validarNumeros">

      <p>{{ calcular() }}</p>
    </div>
  </div>
</template>

<style scoped>

body {
    font-family: 'Arial', sans-serif;
    background-color: rgb(19, 19, 19);
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }

  header {
    text-align: center;
    margin-bottom: 20px;
  }

  h1 {
    color: #333;
  }

  .calculator-container {
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    text-align: center;
  }

  label {
    display: block;
    margin-bottom: 8px;
    color: #555;
  }

  input,
  select {
    width: 100%;
    padding: 10px;
    margin-bottom: 16px;
    box-sizing: border-box;
    border: 1px solid #ddd;
    border-radius: 4px;
    outline: none;
  }

  select {
    appearance: none;
    text-align-last: center; 
  }

  p {
    font-size: 18px;
    font-weight: bold;
    color: #333;
  }
</style>
