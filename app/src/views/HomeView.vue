<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
import Items from '@/components/icons/Items.vue';
import ShoppingCards from '@/components/icons/ShoppingCards.vue';
import { characters } from '../character.js';
import { reactive } from 'vue';
import { store } from '@/cart.js';

  function buyhuman(){

}


  



</script>

<template>
  <br>
  <div class="container">
    <div class="shopping">
      <div class="shoppingcart">
        <h1>Shopping Cart</h1>
      <div></div>
        <div>
        </div>
        
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
