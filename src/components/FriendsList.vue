<template>
    <div>
        <NewFriend v-on:add="addFriend" />
    </div>
    <div>
        <TpProps v-for="amis in lesAmis" :id="amis.id" :name="amis.name" :phone="amis.phone" :email="amis.email"
            :premium="amis.premium" v-on:suppr="handleDelete" v-on:isPremium="supprPremium" />
    </div>
</template>


<script setup>
import NewFriend from './NewFriend.vue';
import TpProps from './TpProps.vue';
import { ref } from "vue";

const lesAmis = ref([
    {
        id: 'lasticot',
        name: 'COCO L ASTICOT',
        phone: '01234 5678 991',
        email: 'coco@lasticot.com',
        premium: true
    },
    {
        id: 'lasticot2',
        name: 'COCO L ASTICOT',
        phone: '01234 5678 991',
        email: 'coco@lasticot.com',
        premium: true
    },
    {
        id: 'kimonoSurUnFrigo',
        name: "Steven Seagal",
        phone: '+338765477',
        email: 'steven@seagal.com',
        premium: true
    },
    {
        id: 'yoyoyo',
        name: "JAROD",
        phone: '+338765477',
        email: 'jAROD@seagal.com',
        premium: true
    }
]);

function handleDelete(id) {
    console.log(id);
    lesAmis.value.splice(lesAmis.id, 1);
}

function supprPremium(id) {
    const togglePrem = lesAmis.value.find((element) => element.id === id);
    togglePrem.premium = !togglePrem.premium;
}



function addFriend(name, phone, email) {

    const nouvelAmi = {
        name: name,
        phone: phone,
        email: email,
        premium: false,
        id: Math.random().toString(),
    }

    lesAmis.value.push(nouvelAmi);
    console.log("utilisateur ajouté");
}
</script>