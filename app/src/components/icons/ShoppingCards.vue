<script setup>
import { ref } from 'vue';

const items = ref(0)



defineProps({

  item:{
    type: Object,
    required: true
  },

  decreaseitem:{
    type: Function,
    required: true,
  },

  amountofitems:{
    type: Object,
    required: true,
  },
})
   


</script>




<template>
  <div class = "item">
        <h2 class="name">{{ item.name }}</h2>
        <img class = "image" :src="item.image" alt=" "/>
        <h5 class="amountofitems">{{ items }}</h5>
        <button @click="decreaseitem" class="decrease">Remove 1</button>
        

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