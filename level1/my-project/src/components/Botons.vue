<template>
    <div id="button">
        <button @click="$emit('botons', 1)">Anterior</button>
        <button @click="$emit('botons', 2)">Següent</button>
    </div>
</template>

<script>
export default {
    name: 'BotonsItem',
}
</script>

<style scoped>
    button {
        padding: 40px;
        width: 50%;
        font-size: 24px;
    }
</style>