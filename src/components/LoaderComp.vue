<script>
    import { store } from '../store';

    export default {
        name:'LoaderComp',

    data(){
        return{
            store
            }
        }
    }
</script>


<template>
    <div class="spinner-border container" role="status">
        <span class="visually-hidden">Loading...</span>
    </div>
</template>


<style lang="scss" scoped>

</style>