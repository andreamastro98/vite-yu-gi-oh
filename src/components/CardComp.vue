<script>

    import { store } from '../store';
    import SingleCardComp from './SingleCardComp.vue';



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
    <div class="container d-flex flex-wrap">
        <SingleCardComp
        v-for="(elem, index) in store.ArrayCarte"
        :key="index"
        :dettagliCarta="elem"
        />
    </div>
</template>


<style lang="scss" scoped>

</style>