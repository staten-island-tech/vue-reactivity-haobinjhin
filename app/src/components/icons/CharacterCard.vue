<script setup>





defineProps({
    character:{
        type: Object,
        required: true
    },

    increaseitems: {
        type: Function,
        required: true
    },

    totalprice: {
        type: Function,
        required: true
    }


})    


    
</script>  

<template>

    <div class="character">
        <h2 class="name">{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
        <h5 class="totalprice">${{ character.price }}</h5>
        <button @click="increaseitems" class="increase">Add to Cart</button>
        
    </div>




</template>    

<style scoped>

.character{
    display: flex;
    flex-wrap: wrap;
    height: 300px;
    padding: 10px;
    border: 2px solid black;
}


.image{
    height: 200px;
    width: auto;
}
    
</style>