<template>
      <div class="card-body shadow-xl">
      <h1 class="card-title text-primary">
        Ajout d'un ami
      </h1>
      <fieldset class="fieldset bg-base-200 border-base-300 rounded-box w-xs border p-4"> 

        <label class="label">Name</label>
        <input type="text" class="input" v-model="name" />

        <label class="label">Tel</label>
        <input type="text" class="input" v-model="phone"/>

        <label class="label">Email</label>
        <input type="text" class="input" v-model="email"/>
        <button class="btn bg-accent" @click="addFriend">Ajouter</button>
      </fieldset>
    </div>
</template>


<script setup>
import {ref} from 'vue';

const emit = defineEmits(["add"]);

const name = ref("");
const phone = ref('');
const email = ref("");

function addFriend() {
  emit("add", name.value, phone.value, email.value);
}

</script>