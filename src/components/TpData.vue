<template>
    <div class="card bg-base-100 w-96 shadow-sm">
      <div class="card-body">
        <img :src="img">
        <h2 class="card-title">{{ name }}</h2>
        <p>{{ age }}</p>
        <p>{{ numberRandom }}</p>
        <p>{{ ageAdd() }}</p>
        <input type="text" :value = "name">
  </div>
</div>

</template>

<script setup>
import {ref} from "vue";

let img = ref("https://www.clipartmax.com/png/small/168-1681657_mario-classic-dr-mario-3d-model.png")
let name = "Dr Mario";
let age = 50;
let numberRandom = Math.random();

function ageAdd(){
  return age + 10;
}
</script>
<style>
input{
  border: solid 1px black;
}
</style>