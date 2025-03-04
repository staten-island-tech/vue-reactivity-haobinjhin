<script setup>
import CharacterCard from '@/components/CharacterCard.vue';
import ShoppingCards from '@/components/ShoppingCards.vue';
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

  function removeall(){
    return shoppingcart.value = []
  }
  



</script>

<template>

  <div class="container">
    <div class="shopping">
      <div class="shoppingcart">
        <h1>Shopping Cart</h1>
        <button @click = "removeall" class="removeall">Clear All</button>
        <h2>Total: ${{ totalprice() }}</h2>
        <ShoppingCards v-for="character in shoppingcart" 
        :item="character"
        :decreaseitem="() => nobuyhuman(character)"/>

        

        
      </div>
    </div>

    <div class="charactercontain">
      <div class="charactercard"><CharacterCard v-for = "character in characters" 
      :character="character" 
      :increaseitems="() => buyhuman(character)"/></div>
  </div>
</div>
    

  

</template>

<style scoped>


h1,h2{
  color: black;
}

.removeall{
    box-shadow: 2px 2px black;
    transition: all 0.15s ease;
    border-radius: 4px;
    outline: none;
}

.removeall:active{
  transform: translate(1px, 1px);
  box-shadow: none;
}

.container{
  width: 1860px;
}


.charactercard{
    max-width: 1860px;
    display:flex;
    flex-direction: row;
    padding: 10px;
    gap: 15px;
    flex-wrap: wrap;
    background-color: beige;
    

}

.charactercontain{
  background-color: beige;
  overflow-y: auto;
  height: 900px;
}

.shopping{
  background-color: beige;
}

.shoppingcart{
  display: flex;
  flex-direction: column;
  border-right: 2px solid rgb(79, 110, 121) ;
  width: 400px;
  overflow-y: auto;
  gap: 10px;
  padding: 10px;
  height: 900px;
  overflow-y: auto;
  
}

.container{
  display: flex;
  flex-direction: row;
}



</style>
