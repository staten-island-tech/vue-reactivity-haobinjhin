<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
import Items from '@/components/icons/Items.vue';
import { characters } from '../character.js'



</script>

<template>
  <br>
  <div class="container">
    <div class="shopping">
      <div ref="shoppingcart">
        <h1>Shopping Cart</h1>
        <Items v-if = "itemincart" :key = "character.name" :item = "item"/>
      </div>
    </div>
    <div class="character"><CharacterCard v-for = "character in characters" :key="character.name" :character="character"/></div>
  </div>

  

</template>

<style scoped>

.character{
    display:flex;
    flex: 20%;
    flex-direction: row;
    gap: 10px;
}

.container{
  display: flex;
  flex-direction: row;
  gap: 10px;
}



</style>
