<template>
    <input type="text" v-model="text">
    <h2 :class="{ 'maClassHello': text === 'Hello','maClassWorld': text === 'World', hidden: btn }">Hello World class dynamique</h2>
    <input type="text" v-model="background">
    <h2 :style="{backgroundColor: background}">Hello world couleur dynamique</h2>
    <button @click="btn=!btn" class="btn btn-success">Cacher</button>

</template>

<script setup>
import { ref } from 'vue'

const text= ref("");
const background = ref('');

const btn = ref(false);

</script>


<style scoped lang="css">
.maClassHello{
background-color: green;
}

.maClassWorld{
background-color: red;
}
</style>