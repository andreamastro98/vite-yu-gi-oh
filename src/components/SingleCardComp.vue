<script>
    export default {
        name:'SingleCard',
        props:['dettagliCarta']
    }
</script>

<template>
    <div class="col-12 col-md-6 col-lg-3 text-center">
        <img :src="dettagliCarta.card_images[0].image_url" alt="">
        <h3>{{ dettagliCarta.name }}</h3>
        <span>{{ dettagliCarta.archetype }}</span>
    </div>
</template>


<style lang="scss" scoped>

</style>