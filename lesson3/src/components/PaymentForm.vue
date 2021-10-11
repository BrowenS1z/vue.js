<template>
<div>
    <form class="form">
      <input type="text" placeholder="Description" v-model="category" />
      <input type="text" placeholder="Amount" v-model="value" />
      <input type="date" placeholder="Date" v-model="date" />
      <button class="AddBtn" type="button" @click="addPayment">Add +</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "PaymentForm",
  data() {
    return {
      category: "",
      date: "",
      value: null
    };
  },
  methods: {
    addPayment() {
      const data = {
        category: this.category,
        value: this.value,
        date: this.date,
      };
      this.$emit("addPayment", data);
    },
  },
};
</script>

<style scoped>
.form{
    box-sizing: border-box;
    margin-top: 10px;
    width: 300px;
    display: flex;
    flex-direction: column;
}
.form input{
    margin-top: 10px;
    padding: 10px;
}
.AddBtn{
    width: 150px;
    background-color: #25A79A;
    color: #fff;
    border: none;
    cursor: pointer;
    padding: 10px 15px 10px 15px;
    margin-top: 10px;
}
</style>