<template>
    <main>
        <div>
            Valor do pedido: <Number/>
        </div>
        <label>O cliente possui plano?</label>
        <div>
            <Radio name="cheq" id="sim" @click="yCheq"/>Sim 
            <Radio name="cheq" id="nao" @click="nCheq"/>Não
        </div>
        <p v-show="cheq">teste</p>
    </main>
</template>

<script>
    import Number from './compForm/Number.vue'
    import Radio from './compForm/Radio.vue'
export default {
    name:'Main',

    data(){
        return{
            cheq:false
        }
    },

    components:{
        Number,
        Radio
    },

    methods:{
        yCheq(){
            this.cheq = true
        },
        
        nCheq(){
            this.cheq = false
        }
    }
}
</script>

<style scoped>
main{
    margin-top: 20px;
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.1em;
    font-weight: bold;
}

div{
    margin: 10px;
}
</style>