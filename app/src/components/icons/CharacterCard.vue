<script setup>
    defineProps({
        character: Object,
    })    

    function addtocart(){

    }



    
</script>  

<template>
    <button @click="" class="character">
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