<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <div class="costs">
      <PaymentList :items="paymentsList" />
    </div>
  </div>
</template>

<script>
import PaymentList from './components/PaymentList.vue'
export default {
  name: 'App',
  components: {
    PaymentList
  },
  methods: {
    addNewPayment (data) {
      this.paymentsList = [...this.paymentsList, data]
    }
  },


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

.costs{
  display: flex;
  justify-content: space-around;
}
</style>
