<template>
    <div id="btn">
        <button @click.right="btnDown" class="btn btn-square btn-error">-</button>
        <p>Le nombre : {{ number }}</p>
        <button @click.middle="btnUp" class="btn btn-square btn-success">+</button>
        <p>{{ afficherUsername() }}</p>

    </div>
</template>

<script setup>
import {ref} from "vue";

let number = ref(0);
let username = ref("");

function btnUp(){
    number.value += 5;
}

function btnDown(){
    number.value -= 11;
}

function afficherUsername(){
    console.log("la fonction fonctionne");
    if(username.value == " "){
        return "test";
    } else {
        return "autre test";
    }
}

</script>

<style scoped>
#btn {
    margin-top : 50px;
    display: flex;
    flex-direction: row;
}
</style>