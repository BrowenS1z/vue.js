<template>
    <div>
        <input type="text" v-model.number="operandOne">
        <input type="text" v-model.number="operandTwo">
        = {{ result }}
        <br>
        <h4 v-show="error">Ошибка!</h4>
        <button v-for="item in operators" :key="item" @click="calculateHandler(item)"> {{ item }} </button>
        <br>

        <input type="checkbox" v-model="checked">
        <label for="">Отобразить экрунную клавиатуру</label>
        <br>

        <div v-show="checked">
            <button v-for="i in keyboard" :key="i" @click="input(i)"> {{ i }} </button>
            <br>
            <input type="radio" value="One" name="op1" v-model="picked">
            <label for="">Операнд 1</label>
            <input type="radio" value="Two" name="op1" v-model="picked">
            <label for="">Операнд 2</label>
        </div>
    </div>
</template>

<script>
export default {
    name: "Calc",
    data: () =>({
        operandOne: '',
        operandTwo: '',
        result: 0,
        error: false,
        checked: true,
        picked: '',
        operators: ['+', '-', '*', '/'],
        keyboard: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    }),
    methods: {
        input: function(item){
            if(this.picked == 'One'){
                parseFloat(this.operandOne += item)
            }
            else{
                parseFloat(this.operandTwo += item)
            }
        },
        calculateHandler(name) {
            this.error = false
            switch(name){
                case '+':
                    this.plus()
                    break;
                case '-':
                    this.minus()
                    break;
                case '/':
                    this.divide()
                    break;
                case '*':
                    this.multiply()
                break;
            }
        },
        plus(){
            this.result = this.operandOne + this.operandTwo
        },
        minus(){
            this.result = this.operandOne - this.operandTwo
        },
        divide(){
            if(this.operandTwo != 0 || this.operandOne != 0){
                this.result = this.operandOne / this.operandTwo
            }
            else{
                this.error = true
            }
        },
        multiply(){
            this.result = this.operandOne * this.operandTwo
        },
    }
}
</script>