    <template>
        <div>
            <h2>{{ character.name }}</h2>
            <img :src="character.image" alt="">
        </div>
    </template>
    
    <script setup>
    defineProps({
        character: Object,
    })
    </script>
    
    <style scoped>
    
    </style>