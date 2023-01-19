<template>
    <div id="escena">
        <ul>
            <p v-for="(frase, index) in frases" :key="index" :class="{active: index === currentSentence}">{{frase}}</p> 
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
    }
    .active {
        background-color: rgba(255, 0, 0, 0.4);
    }
</style>