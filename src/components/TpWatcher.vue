<template>
   <button @click="add" class="btn btn-square btn-success">-</button>
   <p>{{ count }}</p>
</template>

<script setup>
import {ref, watch} from "vue";

let count = ref(0);

const add = () => {
    count.value++;
};

watch(count, (newCount) => {
    if (newCount == 7){
        count.value = 0;
    }
})

</script>

<style scoped>

</style>