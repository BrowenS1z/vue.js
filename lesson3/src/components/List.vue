<template>
    <div>
        <PaymentList :list="responseData"/>
        <!-- <PaymentForm/> -->
    </div>
</template>

<script>
import PaymentList from '../components/PaymentList'
export default {
    name: "List",
    components: {
        PaymentList,
    },
    data(){
        return {
            responseData: [
                {
                    date: '28.03.2020',
                    category: 'Food',
                    value: 169,
                },
                {
                    date: '25.03.2020',
                    category: 'Transport',
                    value: 360,
                },
                {
                    date: '24.03.2020',
                    category: 'Food',
                    value: 532,
                },
                
            ]
        }
    }
}
</script>

<style scoped>

</style>