<template>
    <div v-if="mostrar">
        
        <h2>INFO</h2>
        
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. 
            Sunt sequi earum natus suscipit aliquid, reprehenderit error totam, et id, quibusdam laboriosam consequatur. 
            Deleniti quas, sunt totam sapiente error aperiam debitis.</p>

        <button @click="mostrar = false; canviFondo()">Iniciar</button>
    </div>
    <div v-else id="home" :style="fondo">
        <BotonsItem @botons="pasarFrase"></BotonsItem>
        <EscenaItem :frases= "frasesArray" :currentSentence="currentSentence"></EscenaItem>
    </div>
</template>

<script>
import EscenaItem from './Escena.vue'
import BotonsItem from './Botons.vue'
import {frasesObject} from '../frases.js'

export default {
    name: 'HomeItem',
    components: {
       EscenaItem,
       BotonsItem
    },
    data() {
        return {
           frasesArray: frasesObject,
           currentSentence: 0,
           mostrar: true,
           fondo: {backgroundImage: ""},
        }
    },
    methods: {
        pasarFrase(n) {
            this.currentSentence += n;
            if(this.currentSentence > this.frasesArray.length - 1) {
                this.currentSentence = 0;
            } else if(this.currentSentence < 0) {
                this.currentSentence = this.frasesArray.length - 1;
                }
                this.fondo.backgroundImage=`url( ${this.frasesArray[this.currentSentence].img} )`
        },
        canviFondo() {
            this.fondo.backgroundImage=`url( ${this.frasesArray[this.currentSentence].img} )`
        }
    }
}
</script>

<style scoped>
    #home {
        height: 100vh;
        width: 100vw;
        position: absolute;
        background-size: cover;
        background-repeat: no-repeat;
        padding-top: 16px;
    }
</style>