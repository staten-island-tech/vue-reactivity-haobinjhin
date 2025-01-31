<template>
    <div class="character">
        <h2>{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
    </div>
</template>
    
<script setup>
    defineProps({
        character: Object,
    })    
</script>
    
<style scoped>

.image{
    height: 200px;
    width: auto;
}
    
</style>