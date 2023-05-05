<script>

    import { store } from '../store';
    import SingleCardComp from './SingleCard.vue';



    export default {
        name:'CardComp',
        components:{
            SingleCardComp
        },
    
    data(){
        return{
            store
            }
        }   
    } 
</script>

<template>
    <div class="container">
        <SingleCardComp
        v-for="(elem, index) in store.ArrayCarte"
        :key="index"
        :dettagliCarta="elem"
        />
    </div>
</template>


<style lang="scss" scoped>

</style>