<script>
    import { store } from '../store';

    export default {
        name:'SelectComp',

    Data(){
        return{
            store
            }
        },    
    }
</script>


<template>
    <div class="container">
        <select v-model="selected"
        class="form-select form-select-sm" aria-label=".form-select-sm example">
            <option selected>Archetype</option>
            <option :value="index" v-for="(elem, index) in store.ArrayArchetipi" :key="index">{{ elem }}</option>
        </select>
    </div>
</template>



<style lang="scss" scoped>

</style>