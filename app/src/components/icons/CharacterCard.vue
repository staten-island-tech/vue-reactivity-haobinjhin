<script setup>
    import { ref } from 'vue'
    import { useTemplateRef, onMounted } from 'vue'

    const amountofitems = ref(0)

    const characters = useTemplateRef('character')

    

    defineProps({
        character: Object,
    })    

    setup(){
      const increaseitems = () =>{amountofitems.value++}

      const returntrue = () => {}
        
    }  




    
</script>  

<template>

    <div ref="character">
        <h2>{{ character.name }}</h2>
        <img class="image" :src="character.image" alt="">
        <button @click="increaseitems">{{ amountofitems }}</button>
    </div>

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