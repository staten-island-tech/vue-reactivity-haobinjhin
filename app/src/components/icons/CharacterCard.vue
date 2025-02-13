<script setup>
import { ref } from 'vue'
import { useTemplateRef } from 'vue'
import { store } from '@/cart'
import { characters } from '@/character'
import { reactive } from 'vue'

    const amountofitems = ref(0)



    defineProps({
        character: Object,
    })    


    function increaseitems(){
        amountofitems.value++
        store.push(characters)
        console.log(store)
    }

    function decreaseitem(){
        amountofitems.value--
        store.shift()
        console.log(store)
    }


    
</script>  

<template>

    <div ref="character">
        <h2 ref="name">{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
        <button @click="increaseitems" class="increase">{{ amountofitems }}</button>
        <button @click="decreaseitem" class="decrease">{{ amountofitems }}</button>
    </div>

    <h1 v-if="amountofitems > 0">buy more than one</h1>



</template>    

<style scoped>

.character{
    display: flex;
    flex-wrap: wrap;
}


.image{
    height: 200px;
    width: auto;
}
    
</style>