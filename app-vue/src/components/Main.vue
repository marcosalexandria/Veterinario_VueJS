<template>
    <main>
        <div>
            <label>Valor do pedido:</label> <Number/>
        </div>
        <label>O cliente possui convênio?</label>
        <div>
            <Radio name="cheq" id="sim" @click="yCheq"/>Sim 
            <Radio name="cheq" id="nao" @click="nCheq"/>Não
        </div>
        <div v-show="cheq">
            <label>Selecione o Convênio: </label>
            <select name="convenio" id="convenio">
                <option selected disabled value=""></option>
                <option>amigo dos animais</option>
                <option>saúde animal</option>
            </select>
        </div>

        <div>
            <Button/>
        </div>
    </main>
</template>

<script>
    import Number from './compForm/Number.vue'
    import Radio from './compForm/Radio.vue'
    import Button from './compForm/Button.vue'
export default {
    name:'Main',

    data(){
        return{
            cheq:false
        }
    },

    components:{
        Number,
        Radio,
        Button
    },

    methods:{
        //Faz os planos aparacerem
        yCheq(){
            this.cheq = true
        },
        //Faz os planos sumirem
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

/* Opções de convênio */
#convenio{
    height: 25px;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.1em;
    font-weight: bold;
}
</style>