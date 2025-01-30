<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
const characters = [
  {name: "Stelle", image:""},
  {name: "Caelus", image:""},
  {name: "March 7th", image:""},
  {name: "Dan Heng", image:""},
]
</script>

<template>
  <div class="container">
    <CharacterCard v-for = "character in characters" :key="character.name" :character="character"/>
  </div>
</template>
