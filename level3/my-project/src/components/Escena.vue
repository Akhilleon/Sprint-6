<template>
    <div id="escena">
        <ul>
            <p v-for="(frase, index) in frases" :key="index" :class="{active: index === currentSentence}">{{frase.txt}}</p> 
        </ul>
    </div>
</template>

<script>
export default {
   name: 'EscenaItem',
   props: ['frases', 'currentSentence']
}
</script>

<style scoped>
    p {
        border: 2px solid;
        border-radius: 50px;
        padding: 15px;
        background-color: rgba(255, 255, 255, 0.5);
    }
    .active {
        background-color: rgba(255, 131, 131, 0.881);
    }
</style>