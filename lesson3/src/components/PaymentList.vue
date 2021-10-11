<template>
  <div class="container">
    <div class="addCostForm">
        <h1>My personal costs</h1>
        <button class="openForm" @click="isVisible = !isVisible">ADD NEW COST +</button>
    </div>
    <PaymentForm v-show="isVisible" @addPayment="addNewPayment" />
    <PaymentListData :list="responseData" />
  </div>
</template>

<script>
import PaymentListData from "./PaymentListData";
import PaymentForm from "./PaymentForm";
export default {
  name: "PaymentList",
  components: {
    PaymentListData,
    PaymentForm,
  },
  data() {
    return {
      responseData: [
        {
          date: "2020-03-28",
          category: "Food",
          value: 169,
        },
        {
          date: "2020-03-24",
          category: "Transport",
          value: 368,
        },
        {
          date: "2020-03-26",
          category: "Food",
          value: 532,
        },
      ],
      isVisible: false,
    };
  },
  methods: {
    addNewPayment(data) {
      this.responseData = [...this.responseData, data];
    },
  },
};
</script>

<style scoped>
.addCostForm{
    display: flex;
    flex-direction: column;
    align-items: flex-start;
}
.openForm{
    width: 150px;
    background-color: #25A79A;
    color: #fff;
    border: none;
    cursor: pointer;
    padding: 10px 15px 10px 15px;
}
</style>