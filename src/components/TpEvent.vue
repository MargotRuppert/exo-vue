<template>
<input @keyup="afficherInput($event)" type="text" class="input">
<p > {{ text }}</p>
<input id="input2" @keyup.esc="afficherEsc($event)" type="text" class="input">
<button @click="alertBtn('hello there')" class="btn btn-error">Alert</button>
</template>

<script setup>
import {ref} from "vue";


let text = ref("");

function afficherInput(e){
text.value = e.target.value;
}

function afficherEsc(){

}

function alertBtn(message) {
  alert(message)
}
</script>

<style scoped>
template {
    display: flex;
    flex-direction: column;
}
</style>