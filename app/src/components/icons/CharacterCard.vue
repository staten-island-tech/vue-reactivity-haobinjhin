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
        <h2 class="totalprice">${{ character.price }} per hour</h2>
        <button @click="increaseitems" class="increase">Add to Cart</button>
        
    </div>




</template>    

<style scoped>

.name,
.totalprice{
    color: rgb(0, 0, 0);
}

.increase{
    box-shadow: 2px 2px black;
    transition: all 0.15s ease;
    height: 50px;
    width: 100px;
    border-radius: 4px;
    outline: none;
}

.increase:active{
    transform: translate(1px, 1px);
    box-shadow: none;
}

.character{
    width: 450px;
    height: 350px;
    padding: 10px;
    border: 2px solid rgb(79, 110, 121);
    background-color: rgb(153, 200, 241);
}


.image{
    height: 200px;
    width: 250px;
    object-fit: cover;
    overflow: hidden;
}
    
</style>