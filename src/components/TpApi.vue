<template>
  <div class="card card-border bg-secondary-content w-96">
    <div class="card-body">
      <h2 class="card-title">Mes pokémon</h2>
      <p class="badge badge-secondary" v-if="pkmon" v-for="(pokemon, index) in pkmon.results" :key="index">{{ pokemon.name }}</p>
      <p v-else>veuillez patienter</p>
    </div>
  </div>

  <div class="card card-border bg-secondary-content w-96">
    <div class="card-body">
      <h2 class="card-title">Ma météo à Toulouse</h2>
      <div v-if="meteo">
      <p>Température max: {{ meteo.fcst_day_0.tmax }}°C</p>
      <p>Température min: {{ meteo.fcst_day_0.tmin }}°C</p>
      <p>Température actuelle: {{ meteo.current_condition.tmp }}°C</p>
      <p>Condition météo: {{ meteo.current_condition.condition }}</p>
      </div>
      <p v-else>veuillez patienter</p>

    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const pkmon = ref(null);
const meteo = ref(null);

async function afficherPokemon() {
  const reponse = await fetch("https://pokeapi.co/api/v2/pokemon/");
  const data = await reponse.json();
  pkmon.value = data;
}

async function afficherMeteo() {
  try{
    const reponse = await fetch("https://prevision-meteo.ch/services/json/toulouse");
    const data = await reponse.json();
    meteo.value = data;
  } catch(error){
    console.log(error);
  }

}


onMounted( async() => {
 await afficherPokemon();
 await afficherMeteo();
});

// onUpdated(() => {
// });

// onBeforeUnmount(() => {

// });

</script>

<style scoped lang="css">

</style>