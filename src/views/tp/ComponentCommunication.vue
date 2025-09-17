<template>
    <div class="bg-secondary-content shadow-sm w-full p-5 grid justify-items-center">
        <div>
            <UserActive v-on:show="showUser" :name="user.name" :age="user.age"></UserActive>
        </div>
        <div>
            <UserData v-on:change="changeUser"></UserData>
        </div>
    </div>

</template>


<script setup>
import UserActive from '../../components/UserActive.vue';
import UserData from '../../components/UserData.vue';

import { ref } from 'vue';

const user = ref(
    {
        name: "John",
        age: 26
    }
);

function showUser(name) {
    console.log(name);
}

function changeUser(name, age) {
    const modifyUser = {
        name: name,
        age: age
    }

    user.value = modifyUser;
    console.log("utilisateur modifié");
}

</script>