<script setup>
import CharacterCard from '@/components/icons/CharacterCard.vue';
import ShoppingCards from '@/components/icons/ShoppingCards.vue';
import { characters } from '../character.js';
import { ref } from 'vue';


  const shoppingcart = ref([])

  function buyhuman(character){
    const item = shoppingcart.value.find(item => item.name === character.name)

    if (item){
      item.amount += 1 
      item.totalprice = item.amount*item.price

    } else {
      shoppingcart.value.push({...character, amount: 1, totalprice:character.price})
    }

    


    }

  function nobuyhuman(character){

    if (character.amount > 1){
      character.amount -= 1 
    } else {
      const index = shoppingcart.value.indexOf(character)
      shoppingcart.value.splice(index, 1)
    }

    character.totalprice = character.amount*character.price

  }

  function totalprice(){
    return shoppingcart.value.reduce((total,item) => total + (item.totalprice || 0), 0)
  }

  



</script>

<template>

  <div class="container">
    <div class="shopping">
      <div class="shoppingcart">
        <h1>Shopping Cart</h1>
        <h2>Total: ${{ totalprice() }}</h2>
        <ShoppingCards v-for="character in shoppingcart" 
        :item="character"
        :key="character.name"
        :amount="character.amount"
        :price = "character.price"
        :decreaseitem="() => nobuyhuman(character)"/>

        

        
      </div>
    </div>
    <div class="charactercard"><CharacterCard v-for = "character in characters" 
      :key="character.name" 
      :character="character" 
      :increaseitems="() => buyhuman(character)"/></div>
  </div>

  

</template>

<style scoped>


.container{
  width: 1860px;
}

.charactercard{
    display:flex;
    flex: 20%;
    flex-direction: row;
    margin: 15px;
    gap: 5px;
    

}

.shoppingcart{
  display: flex;
  flex-direction: column;
  border-right: 2px solid black;
  width: 400px;
  height: 100vh;
  overflow-y: auto;
  
}

.container{
  display: flex;
  flex-direction: row;
}



</style>
