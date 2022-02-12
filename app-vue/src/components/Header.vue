<template>
    <header>
        <img :src="logo" alt="logo" id="logo">
        <h1>Caixa</h1>
        <p>Bem-vindo ao Veterinário-VueJS</p>
    </header>
</template>

<script>

export default {
    name:'Header',

    data(){
        return{
            logo:'/img/logo.png'
        }
    }
}
</script>

<style scoped>
header{
    text-align: center;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.2em;
    font-weight: bold;
    background-color: rgb(4, 189, 4);
    height: 100px;
}

/* Imagem */
#logo{
    float: left;
    width: 100px;
    margin-left: 10px;
}
</style>