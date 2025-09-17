<template>
    <div class="card bg-primary-content w-96 shadow-sm">
        <div class="card-body justify-center">
            <h2 class="card-title">Affichage des données</h2>
            <p>Nom: {{name}}</p>
            <p>Age: {{ age }}</p>
        </div>
    </div>
</template>


<script setup>

const props = defineProps({
    name: {
        type: String,
        required: true,
    },
    age: {
        type: Number,
        required: true,
    },

})


</script>