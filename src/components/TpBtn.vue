<template>
    <div id="btn">
        <button @click.right="btnDown" class="btn btn-square btn-error">-</button>
        <p>Le nombre : {{ number }}</p>
        <button @click.middle="btnUp" class="btn btn-square btn-success">+</button>

    </div>
</template>

<script setup>
import {ref} from "vue";

let number = ref(0);
console.log(number);

function btnUp(){
    number.value += 5;
}

function btnDown(){
    number.value -= 11;
}

</script>

<style>
#btn {
    margin-top : 50px;
    display: flex;
    flex-direction: row;
}
</style>