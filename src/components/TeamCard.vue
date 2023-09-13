<script setup>
import Button from "./Button.vue"


const props = defineProps(['user', 'open'])
const emit = defineEmits(['opened'])

const toggleBiography = () => {
    emit('opened', props.user)
}

</script>

<template>
    <div class="card">
        <div>
            <img :src="user.avatar" :alt="user.name" />
            <h2>{{ user.name }}</h2>
        </div>
        <div>
            <p class="job">{{ user.job }}</p>
            <Button class="button" @click="toggleBiography" v-if="!open">Voir biographie</Button>
            <p v-if="open">{{ user.biography }}</p>
        </div>
    </div>
</template>


<style scoped>
.card {
    background-color: #f9f9f9;
    padding: 16px;
    border-radius: 10px;
    box-shadow: 0 1px 3px 0 #0000001a;
    display: flex;
    align-items: center;
    max-width: 500px;
}

.card div {
    width: 50%;
    text-align: center;
}

h2 {
    font-size: 1.25rem;
    margin-top: 5px;
}

img {
    border-radius: 50%;
    max-width: 128px;
}

.job {
    font-weight: 700;
    margin-bottom: 15px;
}

.button {
    background-color: #006e99;
    color: white;
}

</style>