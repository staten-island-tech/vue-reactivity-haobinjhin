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

  amount:{
    type: Object,
    required: true,
  },

  totalprice:{
    type: Object,
    required: true,
  }
})


   


</script>




<template>
  <div class = "item">
        <h2 class="name">{{ item.name }}</h2>
        <img class = "image" :src="item.image" alt=" "/>
        <h5 class="amount">Amount: {{ item.amount }}</h5>
        <button @click="decreaseitem" class="decrease">Remove 1</button>
        

    </div>
</template>



<style scoped>

.name,.amount{
  color: black;
}


.decrease{
    box-shadow: 2px 2px black;
    transition: all 0.15s ease;
    height: 30px;
    width: 80px;
    border-radius: 4px;
    outline: none;
}

.decrease:active{
    transform: translate(1px, 1px);
    box-shadow: none;
}

.item{
    height: 320px;
    width: 320px;
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