<template>
    <button @click="console.log(character.name)" class="character">
        <h2>{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
    </button>

</template>
    
<script setup>
    defineProps({
        character: Object,
    })    

function printname(name){
    
}

    
</script>
    
<style scoped>

.image{
    height: 200px;
    width: auto;
}
    
</style>