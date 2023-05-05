<script>
    export default {
        name:'SingleCard',
        props:['dettagliCarta']
    }
</script>

<template>
    <div class="card text-center">
        <img :src="dettagliCarta.card_images[0].image_url" alt="" class="mb-3">
        <h5>{{ dettagliCarta.name }}</h5>
        <span class="mb-3">{{ dettagliCarta.archetype }}</span>
    </div>
</template>


<style lang="scss" scoped>

.card{
    width: calc(90%/5);
    margin-left: 1rem;
    margin-bottom: 1rem;
}

</style>