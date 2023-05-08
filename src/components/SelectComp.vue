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
        @click="$emit('select')"
        class="form-select form-select-sm" 
        aria-label=".form-select-sm example">
            <option :value="store.ArrayArchetipi[index].archetype_name" 
            v-for="(elem, index) in store.ArrayArchetipi" :key="index">{{ store.ArrayArchetipi[index].archetype_name }}</option>
        </select>
    </div>
</template>



<style lang="scss" scoped>

</style>