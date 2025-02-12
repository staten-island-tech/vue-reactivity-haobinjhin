<script setup>
    import { ref } from 'vue'
    import { useTemplateRef } from 'vue'

    const amountofitems = ref(0)


    

    defineProps({
        character: Object,
    })    


    function increaseitems(){
        amountofitems.value++
        
    }

    function decreaseitem(){
        amountofitems.value--
    }
    






    
</script>  

<template>

    <div ref="character">
        <h2>{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
        <button @click="increaseitems" >{{ amountofitems }}</button>
        <button @click="decreaseitem" >{{ amountofitems }}</button>
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