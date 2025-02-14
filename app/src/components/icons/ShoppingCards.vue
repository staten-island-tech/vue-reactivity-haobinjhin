<script setup>

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
        <h2>{{ shoppingcart.value.name }}</h2>
        <img class = "image" :src="shoppingcart.value.image" alt=" "/>
        <button @click="decreaseitem" class="decrease">{{ amountofitems }}</button>
        

    </div>
</template>



<style scoped>

</style>