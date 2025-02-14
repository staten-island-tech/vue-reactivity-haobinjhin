<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
import Items from '@/components/icons/Items.vue';
import ShoppingCards from '@/components/icons/ShoppingCards.vue';
import { characters } from '../character.js';
import { ref } from 'vue';
import { store } from '@/cart.js';


  const shoppingcart = ref([])

  function buyhuman(character){
    shoppingcart.value.push({...character})

    function countdups(list, dups){
      let dupli = 0
      list.forEach((item) => {if (item === dups){ dupli++ }});
      return dupli
    }

    if(countdups(shoppingcart, character) > 1){
      shoppingcart.filter(character)


    }
    console.log(shoppingcart)
    }

  function nobuyhuman(humans, character){
    const getridofitem = humans.findIndex((human) => human === character)
    if (getridofitem !== -1){
      humans.splice(getridofitem, 1)
    }
  }


  



</script>

<template>
  <br>
  <div class="container">
    <div class="shopping">
      <div class="shoppingcart">
        <h1>Shopping Cart</h1>
        <ShoppingCards v-for="character in shoppingcart" 
        :item="character"
        :key="character.name"
        :decreaseitem="() => nobuyhuman(shoppingcart, character)"/>
        <div>
        </div>
        
      </div>
    </div>
    <div class="character"><CharacterCard v-for = "character in characters" 
      :key="character.name" 
      :character="character" 
      :increaseitems="() => buyhuman(character)"/></div>
  </div>

  

</template>

<style scoped>

.character{
    display:flex;
    flex: 20%;
    flex-direction: row;
    gap: 10px;
}

.shoppingcart{
  display: flex;
  flex-direction: column;
  border: 4px solid black;
  width: 400px;
  
}

.container{
  display: flex;
  flex-direction: row;
}



</style>
