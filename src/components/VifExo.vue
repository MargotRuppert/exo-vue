<template>
    <div class="container mx-auto p-4">
        <div class="card shadow-lg p-6 bg-base-100">
            <h2 class="text-2xl font-bold mb-4">WatchList 🎬 (Films à voir) - Mode : Composition</h2>

            <input v-model="ajout" type="text" placeholder="Entrez le nom d'un film" class="input input-bordered w-full mb-3" />

            <button @click="tabFilm.push(ajout)" class="btn btn-primary mb-4">
                Ajouter à votre Liste
            </button>

            <hr class="my-4" />

            <div>
                <h3 class="text-xl font-semibold mb-2">Votre film ajouté : </h3>
            </div>

            <p class="text-gray-500" v-if="tabFilm[0]">
                {{ tabFilm[0] }}
            </p>

            <p class="text-gray-500" v-else>
                Pas encore de films dans votre liste ? Veuillez en ajouter un.
            </p>
        </div>
    </div>
</template>

<script setup>
import {ref} from 'vue'
const tabFilm = ref([]);

const ajout = ref("");

</script>