<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
const characters = [
  {name: "Stelle", image:"/danheng.png"},
  {name: "Caelus", image:"/danheng.png"},
  {name: "March 7th", image:"/danheng.png"},
  {name: "Dan Heng", image:"/danheng.png"},
]
</script>

<template>
  <br>
  <div class="container">
    <CharacterCard v-for = "character in characters" :key="character.name" :character="character"/>
  </div>

</template>

<style scoped>

.container{
    display:flex;
    flex: 20%;
    flex-direction: row;
    gap: 10px;
}

</style>
