<template>
  <div class="calculator">
    <h1>Calculadora</h1>
    <div class="input-group">
      <label for="num1">Número 1:</label>
      <input type="number" id="num1" v-model="num1" @input="calculate">
    </div>
    <div class="input-group">
      <label for="num2">Número 2:</label>
      <input type="number" id="num2" v-model="num2" @input="calculate">
    </div>
    <div class="input-group">
      <label for="operation">Operação:</label>
      <select id="operation" v-model="operation" @change="calculate">
        <option value="add">Adição</option>
        <option value="subtract">Subtração</option>
        <option value="multiply">Multiplicação</option>
        <option value="divide">Divisão</option>
      </select>
    </div>
    <div class="result">
      Resultado: {{ result }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          this.result = Number(this.num1) + Number(this.num2);
          break;
        case 'subtract':
          this.result = Number(this.num1) - Number(this.num2);
          break;
        case 'multiply':
          this.result = Number(this.num1) * Number(this.num2);
          break;
        case 'divide':
          this.result = Number(this.num1) / Number(this.num2);
          break;
      }
    }
  }
};
</script>

<style>
  /* Estilo para a calculadora */
  .calculator {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    padding: 20px;
    background-color: #f2f2f2;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.2);
    width: 300px;
    margin: 50px auto;
    font-family: Arial, sans-serif;
  }

  .calculator label {
    display: block;
    margin-bottom: 10px;
    font-size: 16px;
    font-weight: bold;
  }

  .calculator input {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
    width: 100%;
    margin-bottom: 10px;
    box-sizing: border-box;
    font-size: 16px;
  }

  .calculator select {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
    width: 100%;
    margin-bottom: 10px;
    box-sizing: border-box;
    font-size: 16px;
  }

  .calculator button {
    background-color: #4CAF50;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 3px;
    cursor: pointer;
    font-size: 16px;
    margin-top: 10px;
  }

  .calculator button:hover {
    background-color: #3e8e41;
  }

  .calculator button:active {
    background-color: #235723;
  }

  .calculator .result {
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    margin-top: 10px;
  }
</style>

