<template>
    <div id="first">
        <div class="card bg-base-100 w-96 shadow-sm">
            <div class="card-body">
                <h2 class="card-title" @click="hActive=!hActive" :class="{ 'text-secondary': hActive }">Card title!</h2>
                <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
                <div class="card-actions justify-end">
                </div>
            </div>
        </div>

        <div class="card bg-base-100 w-96 shadow-sm">
            <div @click="isActive=!isActive" class="card-body" :class="{ 'bg-success': isActive }">
                <h2 class="card-title">Card title!</h2>
                <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
                <div class="card-actions justify-end">
                </div>
            </div>
        </div>
    </div>


    <div id="second">
        <div class="card bg-base-100 w-96 shadow-sm" @click="activeColor = activeColor === 'blue' ? 'red': 'blue'"  :style="{ color: activeColor}" >
            <div class="card-body">
                <h2 class="card-title">Card title!</h2>
                <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
                <div class="card-actions justify-end">
                </div>
            </div>
        </div>

        <div class="card bg-base-100 w-96 shadow-sm" >
            <div class="card-body">
                <h2 class="card-title">Card title!</h2>
                <p>A card component has a figure, a body part, and inside body there are title and actions parts</p>
                <div class="card-actions justify-end">
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const isActive = ref(true);
const hActive = ref(true);

const activeColor = ref('red');
const otherColor = ref('blue');

</script>

<style>
#first, #second {
    display: flex;
    flex-direction: row;
}
</style>