<script setup>
import Button from "./Button.vue"
import { RouterLink } from 'vue-router'
import { ref } from 'vue'

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
                    <li><span class="lg">Accueil</span>
                        <img src="../assets/images/home.svg" class="mb" alt="Accueil">
                    </li>

                </RouterLink>

                <RouterLink to="home">
                    <li><span class="lg">Films</span>
                        <img src="../assets/images/movies.svg" class="mb" alt="Films">
                    </li>
                </RouterLink>

                <RouterLink to="home">
                    <li><span class="lg">Catégories</span>
                        <img src="../assets/images/category.svg" class="mb" alt="Catégories">
                    </li>
                </RouterLink>

                <RouterLink to="about">
                    <li><span class="lg">A propos</span>
                        <img src="../assets/images/about.svg" class="mb" alt="A propos">
                    </li>
                </RouterLink>
            </ul>

        </div>

        <div class="right-side">
            <Button class="button" v-if="!isConnected" @click="isConnected = !isConnected">Connexion</Button>
            <div v-if="isConnected" class="user-info">
                <strong class="lg">
                    Brayan NOLF
                </strong>
                <img src="../assets/profil.jpg" alt="Photo de profil">
                <span @click="isConnected = !isConnected">X</span>
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

li img {
    display:none;
    filter: invert(92%) sepia(63%) saturate(1%) hue-rotate(67deg) brightness(104%) contrast(101%);
    height:35px;
    width: 35px;
}

nav {
    max-width: 100vw;
    font-size: 1.2rem;
    justify-content: space-between;
    color: white;
    padding: 1rem 0.75rem;
    height: 4rem;

}

nav a:visited {
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

.left-side li::before {
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

.left-side li:hover::before {
    width: 100%;
    opacity: 1;
}

.right-side {
    position: relative;
}

.right-side .user-info {
    display: flex;
    align-items: center;
    gap: 15px;
}

.right-side img {
    max-height: 50px;
    max-width: 50px;
    border-radius: 50%;
}

.right-side span {
    position: absolute;
    top: 0;
    right: 0;
    cursor: pointer;
}

.lg{
    display:block;
}
.mb{
    display:none;
}
@media screen and (max-width: 680px) {
    .lg{
        display:none;
    }
    .mb{
        display:block;
    }
}
</style>