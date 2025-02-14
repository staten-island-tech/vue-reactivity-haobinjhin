<script setup>
import { ref } from 'vue'
import { useTemplateRef } from 'vue'
import { store } from '@/cart'
import { characters } from '@/character'
import { reactive } from 'vue'

    const amountofitems = ref(0)



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