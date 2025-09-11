<template>
    <input type="text" v-model="text">
    <h2 :class="{ 'maClassHello': text === 'Hello','maClassWorld': text === 'World' }">Hello World class dynamique</h2>
    <input type="text" v-model="background">
    <h2 :style="{backgroundColor: background}">Hello world couleur dynamique</h2>
    <button></button>

</template>

<script setup>
import { ref } from 'vue'

const text= ref("");
const background = ref('');

</script>


<style scoped lang="css">
.maClassHello{
background-color: green;
}

.maClassWorld{
background-color: red;
}
</style>