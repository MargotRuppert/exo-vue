<template>
    <div class="card w-full max-w-md bg-base-200 shadow-xl my-4">
        <div class="card-body">
            <h2 class="card-title text-primary">
                👤 {{ name }}
                <div class="badge" :class="premium ? 'badge-success' : 'badge-ghost'">
                    {{ premium ? 'Premium' : 'Standard' }}
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
            </div>
        </div>
    </div>
</template>

<script setup>

const friend = defineProps({
id: String,
name: String,
phone: String,
email: String,
premium: Boolean,
});

const emit = defineEmits(["suppr"]);


function supprimer() {
    // On EMIT un Event Custom
    // emit("liked");
    // On EMIT un Event Custom avec des données dedans
    emit("suppr", friend.id);
}


</script>
