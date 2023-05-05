<script >

import axios from 'axios'
import {store} from './store'
import NavComp from './components/NavComp.vue'
import CardComp from './components/CardComp.vue'
import SingleCardComp from './components/SingleCardComp.vue'


export default{
  name:'app',
  components:{
    NavComp,
    CardComp,
    SingleCardComp,
  },
  data(){
    return{
      store
    }    
  },
  created(){
    this.chiamataApi()

  },
  methods:{
    chiamataApi(){
      axios.get(' https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((res)=>{

        // associo a datiApi il le 20 carte restituite dall'api
        const datiApi = res.data.data;
        console.log(res.data)

        //associo allárray in store.js la const datiApi
        this.store.ArrayCarte = datiApi

        console.log(this.store.ArrayCarte)
        }
      
      )
    }
  }
}

</script>

<template>
  <NavComp/>
  <main class="py-5">
    <CardComp/>
  </main>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
