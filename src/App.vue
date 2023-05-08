<script >
import axios from 'axios';
import {store} from "./store";
import AppMain from "./components/AppMain.vue";



export default{
  name:"app",
  components:{
    AppMain,
    

  },
  data(){
    return{
      store
    }
  },
  created(){
    this.chiamataApi(),
    this.archetypeCall()
  },
  methods: {
    archetypeCall(){
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
       .then( (res) =>{
        this.store.arrayArchetype = res.data
       })
    }, 
      chiamataApi(){
        store.soldatino = true
        if(store.selectType !== ""){
         
          axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.selectType}`)
          .then((res) =>{
           
            const dataApi = res.data.data
            this.store.arrayCard = dataApi
            console.log(dataApi)
            store.soldatino = false
          })
          
        }else{
          store.soldatino = false
        }
      }
    }
}
</script>

<template>
  <AppMain @pippo="chiamataApi"/>

</template>

<style lang="scss">
@use './style/main.scss';
</style>
