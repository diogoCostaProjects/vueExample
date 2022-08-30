
<script>
import axios from "axios";

export default {
    
    name: 'CardComponent',
    data() {
        return {
            character: '',
            msgLoad:'Carregando...',
            atualClass: 'personagem'
        }
    },
    mounted() {     // MÉTODOS DE LIVECYCLE
                    // CHAMADA PARA API COM AXIOS
        this.loadChar()
    },
    methods: { // AQUI FICAM TODOS OS MÉTODOS QUE SERÃO USADOS NA APLICAÇÃO
        loadChar() {
            axios
                .get("https://swapi.dev/api/people/")
                .then((res) => {
                    this.character = res.data.results;
                    this.msgLoad = ''
                })
                .catch((error) => {
                    console.log(error);
                });
        },
        changeClass(type) {
            this.atualClass = type;
        }
    }
}
</script>

<template>
    <h2>{{msgLoad}}</h2>
    <h4>Chose your side</h4>
    <img src="../assets/force.jpg" alt="" class="imgL" @click="changeClass('personagem')"/>
    <img src="../assets/dark.jpg" alt="" class="imgL" @click="changeClass('personagem2')"/>
    
    <div v-for="char in character" :key="char.name" v-bind:class=atualClass>
        <strong>Personagem:</strong> {{char.name}} <br>
        <strong>Peso:</strong> {{char.mass}} KG
    </div>
</template>

<style scoped>
    .personagem{
        background-color: lightgray;
        padding: 20px;
        text-align: center;
        margin: 20px;
    }
    .personagem2{
        background-color: black;
        color: white;
        padding: 20px;
        text-align: center;
        margin: 20px;
    }
    .imgL{
        border-radius: 20px;
        width: 25%;
        margin-right: 10px;

    }
</style>