<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>

    <input type="text" v-model.number="operand1">
    <input type="text" v-model.number="operand2">

    <button @click="plus">+</button>
    <button @click="minus">-</button>
    <button @click="multiplication">*</button>
    <button @click="division">/</button>
    <button @click="degree">^</button>
    <button @click="integer">int</button>

    <h2>{{ result }}</h2>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data: () =>({
    operand1: 0,
    operand2: 0,
    result: 0
  }),
  methods: {
    plus () {
      let res = this.operand1 + this.operand2;
      this.result = this.operand1 + " + " + this.operand2 + " = " + res;
    },
    minus () {
      let res = this.operand1 - this.operand2;
      this.result = this.operand1 + " - " + this.operand2 + " = " + res;
    },
    multiplication () {
      let res = this.operand1 * this.operand2;
      this.result = this.operand1 + " * " + this.operand2 + " = " + res;
    },
    division () {
      let res = this.operand1 / this.operand2;
      this.result = this.operand1 + " / " + this.operand2 + " = " + res;
    },
    degree () {
      let res = Math.pow(this.operand1, this.operand2);
      this.result = this.operand1 + " ^ " + this.operand2 + " = " + res + " (Возведение в степень)";
    },
    integer () {
      let res = parseInt(this.operand1 / this.operand2);
      this.result = this.operand1 + " / " + this.operand2 + " = " + res + " (Целочисленное деление)";
    }
  },
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
