<script setup>
import {ref} from 'vue'
import {$fetch} from 'ofetch'
const year = new Date().getFullYear()
const movieCount = ref()
$fetch("https://api.vueflix.boxydev.com/movies")
.then(response => {
    movieCount.value = response.length
})

</script>

<template>
<footer>
<p>Copyright &copy {{year}}. Catalogue de {{movieCount}} Films
</p>

</footer>

</template>

<style scoped>
footer{
text-align: center;
    color: white;
    margin-top: 40px;
    border-top: 1px solid #ffffff;
    padding: 48px 0;
}


</style>