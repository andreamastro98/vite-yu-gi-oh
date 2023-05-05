<script >

import axios from 'axios'
import {store} from './store'

export default{
  name:'app',
  components:{

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
        const datiApi = res.data;

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
  <h1>Ciao mondo</h1>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
