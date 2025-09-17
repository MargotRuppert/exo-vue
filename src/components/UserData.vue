<template>
  <fieldset class="fieldset bg-primary-content border-base-300 rounded-box w-xs border p-4">
    <legend class="fieldset-legend">Formulaire d'édition</legend>

    <label class="label">Nom</label>
    <input type="text" class="input" v-model="name" />

    <label class="label">Age</label>
    <input type="number" class="input" v-model="age" />

    <button class="btn btn-primary mt-4" @click="changeUser">Modifier</button>
  </fieldset>
</template>


<script setup>
import { ref } from 'vue';

const name = ref("");
const age = ref("");

const emit = defineEmits({
  'change': (name) => {
    if (name) {
      return true;
    } else {
      console.log('name is required');
      console.warn('C\'est la catastrophe !!!!!!');
      console.error('ON A PAS DE NAME Dans le event change');
      return false;
    }
  }
})

function changeUser() {
  emit("change", name.value, age.value);
}

</script>