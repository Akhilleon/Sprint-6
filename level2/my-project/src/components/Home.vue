<template>
    <div v-if="mostrar">
        
        <h2>INFO</h2>
        
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. 
            Sunt sequi earum natus suscipit aliquid, reprehenderit error totam, et id, quibusdam laboriosam consequatur. 
            Deleniti quas, sunt totam sapiente error aperiam debitis.</p>

        <button @click="mostrar = false">Iniciar</button>
    </div>
    <div v-else id="home">
        <BotonsItem @botons="pasarFrase"></BotonsItem>
        <EscenaItem :frases= "frasesArray" :currentSentence="currentSentence"></EscenaItem>
    </div>

</template>

<script>
import EscenaItem from './Escena.vue'
import BotonsItem from './Botons.vue'

export default {
    name: 'HomeItem',
    components: {
       EscenaItem,
       BotonsItem
    },
    data() {
        return {
           frasesArray: ["El nostre heroi estava surant per l'espai sideral quan a la llunyania va albirar una nau espacial", 
           
           "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes.", 
           
           "L'heroi va decidir travessar la porta que el portava a casa", 
           
           "Mentrestant, altres herois no van tenir tanta sort en la seva elecció ..."],
           currentSentence: 0,
           mostrar: true
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
        }
    }
}
</script>

<style>

</style>