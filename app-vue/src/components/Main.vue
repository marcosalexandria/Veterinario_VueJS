<template>
    <main>
        <div>
            <label>Valor do pedido:</label> <Number id="preco"/>
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
            <Button @click="finalizar"/>
        </div>

        <div id="res">

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
            cheq:false,
            desconto: Number
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
        },

        finalizar(){
            const preco=document.getElementById('preco').value;
            const sim=document.getElementById('sim').checked;
            const nao=document.getElementById('nao').checked;
            const res=document.getElementById('res');
            const convenio=document.getElementById('convenio').value;

            if(nao==''&&sim==''){
                alert("*ERRO* O cliente possui convênio ou não?");

            }else if(nao==true){
                this.desconto=preco*10/100;
                res.innerHTML=`Valor da compra R$ ${preco} <br>desconto: R$ ${this.desconto} <br>Total a pagar: R$ ${preco-this.desconto}`;
                
            }else if(sim==true&&convenio=='amigo dos animais'){
                this.desconto=preco*30/100;
                res.innerHTML=`Valor da compra R$ ${preco} <br>desconto: R$ ${this.desconto} <br>Total a pagar: R$ ${preco-this.desconto}`;
            }else if(sim==true&&convenio=='saúde animal'){
                this.desconto=preco*50/100;
                res.innerHTML=`Valor da compra R$ ${preco} <br>desconto: R$ ${this.desconto} <br>Total a pagar: R$ ${preco-this.desconto}`;
            }
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