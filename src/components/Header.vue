<script setup>
import Button from "./Button.vue"
import { RouterLink } from 'vue-router'
import{ref} from 'vue'

const isConnected = ref(false)


</script>


<template>
    <nav>
        <div class="left-side">
            <RouterLink to="home">
                <div class="logo">
                    Vue+
                </div>
            </RouterLink>

            <ul>
                <RouterLink to="home">
                    <li>Accueil</li>
                </RouterLink>

                <RouterLink to="home">
                    <li>Films</li>
                </RouterLink>

                <RouterLink to="home">
                    <li>Catégories</li>
                </RouterLink>

                <RouterLink to="about">
                    <li>A propos</li>
                </RouterLink>
            </ul>

        </div>

        <div class="right-side">
            <Button v-if="!isConnected" @click="isConnected = !isConnected">Connexion</Button>
            <div v-if="isConnected" class="user-info">
                <strong>
                    Brayan NOLF
                </strong>
                <img src="../assets/profil.jpg" alt="Photo de profil">
            </div>
        </div>
    </nav>
</template>


<style scoped>
nav,
.left-side,
ul {
    display: flex;
    align-items: center;
    text-decoration: none;
}



nav {
    max-width: 1280px;
    font-size: 1.2rem;
    justify-content: space-between;
    color:white;
    padding: 1rem 0.75rem;
    max-width: 100%;
}

nav a:visited{
    color: white;
}


.left-side .logo {
    font-size: 2rem;
    border-right: 5px solid white;
    border-bottom: 5px solid white;
    padding: 0 5px 3px 0;
    margin-right: 1rem;
}

.left-side ul {
    gap: 15px;
}

.left-side li {
    position: relative;
    list-style: none;
}

.left-side li::before{
    content: "";
    position: absolute;
    left: 0;
    bottom: -8px;
    width: 0;
    height: 0;
    border-bottom: 3px solid white;
    border-radius: 8px;
    transition: 0.3s ease-in-out;
    opacity: 0;
}

.left-side li:hover::before{
    width: 100%;
    opacity: 1;
}


.right-side .user-info{
    display:flex;
    align-items: center;
    gap: 15px;
}
.right-side img{
    max-height: 82px;
    max-width: 82px;
    border-radius: 50%;
}

</style>