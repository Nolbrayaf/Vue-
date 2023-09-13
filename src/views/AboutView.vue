<script setup>
import Card from "../components/TeamCard.vue"
import { ref } from 'vue'


const selected = ref(null)
const team = ref([
  {
    id: 1,
    name: 'Jean',
    job: 'Manager',
    avatar: 'https://i.pravatar.cc/150?u=fiorella@boxydev.com',
    biography:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam mollitia voluptatum sunt placeat aliquam iusto exercitationem at? Vel itaque porro quis saepe quod soluta alias facere eum deleniti? Rem, eveniet.'
  },
  {
    id: 2,
    name: 'Michel',
    job: 'Développeur',
    avatar: 'https://i.pravatar.cc/150?u=matthieu@boxydev.com',
    biography:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam mollitia voluptatum sunt placeat aliquam iusto exercitationem at? Vel itaque porro quis saepe quod soluta alias facere eum deleniti? Rem, eveniet.'
  },
  {
    id: 3,
    name: 'Lucien',
    job: 'Commercial',
    avatar: 'https://i.pravatar.cc/150?u=marina@boxydev.com',
    biography:
      'Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam mollitia voluptatum sunt placeat aliquam iusto exercitationem at? Vel itaque porro quis saepe quod soluta alias facere eum deleniti? Rem, eveniet.'
  }
])

</script>


<template>
  <div class="container">
    <h1>A propos</h1>
    <div class="cards-container">
      <Card class="card" v-for="teamMember in team" :key="teamMember.id" :user="teamMember" @opened="selected = $event.id"
        :open="selected === teamMember.id" />
    </div>
  </div>
</template>

<style scoped>
.container{
  margin: auto;
  max-width: 1400px;
  padding: 0 12px;
}

h1 {
  text-align: center;
  font-weight: 700;
  margin: 48px 0;
  font-size: 36px;
  color: white;
}


.cards-container{
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
}

.card{
  width: calc(100%/3 -(30px)*2/3);
}

</style>
