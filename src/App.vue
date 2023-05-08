<script >

import axios from 'axios'
import {store} from './store'
import NavComp from './components/NavComp.vue'
import CardComp from './components/CardComp.vue'
import SingleCardComp from './components/SingleCardComp.vue'
import SelectComp from './components/SelectComp.vue'


export default{
  name:'app',
  components:{
    NavComp,
    CardComp,
    SingleCardComp,
    SelectComp,
  },
  data(){
    return{
      store
    }    
  },
  created(){
    this.chiamataApi,
    this.chiamataApi2

  },
  computed:{
    

    chiamataApi(){

      if(store.selected !== ''){
        axios.get(` https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.selected}`)
        .then((res)=>{

          // associo a datiApi il le 20 carte restituite dall'api
          const datiApi = res.data.data;
          //console.log(res.data)

          //associo all'array in store.js la const datiApi
          this.store.ArrayCarte = datiApi

          console.log(this.store.ArrayCarte)
          }
      
      )
      } else {

        axios.get(' https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then((res)=>{

          // associo a datiApi il le 20 carte restituite dall'api
          const datiApi = res.data.data;
          //console.log(res.data)

          //associo all'array in store.js la const datiApi
          this.store.ArrayCarte = datiApi

          console.log(this.store.ArrayCarte)
          }      
        )
      }

      
  },
  methods:{
    
    },
    chiamataApi2(){
      axios.get(' https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then((res)=>{

        // associo a datiApi i 20 archetipi restituite dall'api
        const datiApi = res.data;
        //console.log(res.data)

        //associo all'array in store.js la const datiApi
        this.store.ArrayArchetipi = datiApi

        console.log(this.store.ArrayArchetipi)
        }
      
      )
    }
  }
}

</script>

<template>
  <NavComp/>
  <main class="py-5">
    <SelectComp @select="chiamataApi" class="my-4"/>
    <CardComp/>
  </main>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
