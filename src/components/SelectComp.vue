<script>
    import { store } from '../store';

    export default {
        name:'SelectComp',

    data(){
        return{
            store
            }
        },    
    }
</script>


<template>
    <div class="container">
        <select v-model="store.selected"
        class="form-select form-select-sm" 
        aria-label=".form-select-sm example">
            <option selected>Archetype</option>
            <option :value="store.ArrayArchetipi[index].archetype_name" 
            v-for="(elem, index) in store.ArrayArchetipi" :key="index">{{ elem }}</option>
        </select>
    </div>
</template>



<style lang="scss" scoped>

</style>