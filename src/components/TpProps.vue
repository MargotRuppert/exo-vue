<template>
  <div class="p-6">
    <!-- Titre -->
    <h1 class="text-2xl font-bold text-center mb-6">
      Ici c'est le composant parent ExoPropsView
    </h1>
    <!-- Liste d'amis -->
    <div class="card bg-base-100 shadow-md mb-4">
      <div class="card-body">
          <p>ID: {{ id }}</p>
          <p>Nom: {{ name }}</p>
          <p>tel: {{ phone }}</p>
          <p>Email: {{ email }}</p>      
      </div>
    </div>
  </div>
</template>

<script setup>
// import { defineProps } from "vue";


const friend = defineProps({
id: String,
name: String,
phone: String,
email: String,
});

</script>
