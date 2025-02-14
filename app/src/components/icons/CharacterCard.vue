<script setup>
import { ref } from 'vue'
import { useTemplateRef } from 'vue'
import { store } from '@/cart'
import { characters } from '@/character'
import { reactive } from 'vue'
import { amountofitems } from '@/cart'




    defineProps({
        character:{
            type: Object,
            required: true
        },

        increaseitems: {
            type: Function,
            required: true
        },


    })    



    
</script>  

<template>

    <div class="character">
        <h2 class="name">{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
        <button @click="increaseitems" class="increase">{{ amountofitems }}</button>
    </div>




</template>    

<style scoped>

.character{
    display: flex;
    flex-wrap: wrap;
    height: 300px;
}


.image{
    height: 200px;
    width: auto;
}
    
</style>