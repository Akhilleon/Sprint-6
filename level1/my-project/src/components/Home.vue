<template>
    <div id="home">
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
           currentSentence: 0
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