<template>
    <div class="card w-full max-w-md bg-base-200 shadow-xl my-4">
        <div class="card-body">
            <h2 class="card-title text-primary">
                👤 {{ name }}
                <div class="badge badge-outline badge-success" v-if="premium">
                    Premium 
                </div>
                <div class="badge badge-outline badge-success" v-else>
                    Pas Premium
                </div>
            </h2>

            <div class="space-y-2 text-base-content">
                <p class="flex items-center gap-2">
                    <span class="badge badge-outline badge-primary">ID</span>
                    {{ id }}
                </p>

                <p class="flex items-center gap-2">
                    <span class="badge badge-outline badge-secondary">📞</span>
                    {{ phone}}
                </p>

                <p class="flex items-center gap-2">
                    <span class="badge badge-outline badge-accent">📧</span>
                    {{ email }}
                </p>
                <p class="flex items-center gap-2">
                    <button class="btn bg-error" @click="supprimer">Supprimer</button>
                </p>
                <p class="flex items-center gap-2">
                    <button class="btn bg-accent" @click="supprPremium">Toggle Premium</button>
                </p>
            </div>
        </div>
    </div>
</template>


<script setup>
const friend = defineProps({
    id: {
        type: String,
        required: true,
    },
    name: {
        type: String,
        required: true,
    },
    phone: {
        type: String,
        required: true,
    },
    email: {
        type: String,
        required: true,
    },
    premium: {
        type: Boolean,
        required: false,
        default: false,
    },
})

const emit = defineEmits({
    'suppr': (id)=>{
        if(id){
            return true;
        }else{
            console.log('id is required');
            console.warn('C\'est la catastrophe !!!!!!');
            console.error('ON A PAS DE ID Dans le event suppr');
            return false;
        }
    },
    'isPremium': (id)=>{
        if(id){
            return true;
        }else{
            console.log('id is required');
            console.warn('C\'est la catastrophe !!!!!!');
            console.error('ON A PAS DE ID Dans le event supprPremium');
            return false;
        }
    }
})


function supprimer() {
    emit("suppr", friend.id);
}

function supprPremium(){
  emit("isPremium", friend.id);
}
</script>
