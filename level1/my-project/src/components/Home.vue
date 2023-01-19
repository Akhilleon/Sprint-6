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
           currentSentence: 0,
           next: true,
           back: false
        }
    },
    methods: {
        pasarFrase(n) {
            if(this.currentSentence == 1) {
                this.back = true;
            } else if(this.currentSentence == 0) {
                this.back = false;
                this.next = true;
            }

            if(n == 1 && this.back == true ) {
                this.currentSentence--;
            }
             
            if(n == 2 && this.next == true) {
                this.currentSentence++
            } 
            
            if(this.currentSentence == 3) {
                this.next = false;
                this.back = true;
            } 
            
            console.log(this.currentSentence);
            console.log("Next: " + this.next);
            console.log("Back: " + this.back);
        }
    }
}
</script>

<style>

</style>