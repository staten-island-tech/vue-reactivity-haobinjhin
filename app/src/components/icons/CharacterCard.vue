<script setup>
    defineProps({
        character: Object,
    })    

    let shoppingcart = []

    function addtocart(event){
        shoppingcart.push(event.target)
        shoppingcart.forEach((item) => console.log(item))
    }



    
</script>  

<template>

    <button @click="addtocart" class="character">
        <h2>{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
    </button>

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