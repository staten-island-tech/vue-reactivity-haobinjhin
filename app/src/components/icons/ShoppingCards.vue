<script setup>
import { amountofitems } from '@/cart';

defineProps({

  item:{
    type: Object,
    required: true
  },

  decreaseitem:{
    type: Function,
    required: true,
  },
})
   


</script>




<template>
  <div class = "item">
        <h2 class="name">{{ item.name }}</h2>
        <img class = "image" :src="item.image" alt=" "/>
        <button @click="decreaseitem" class="decrease">{{ amountofitems }}</button>
        

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