<script >
import axios from 'axios';
import {store} from "./store";
import AppMain from "./components/AppMain.vue";
import SingleCard from "./components/AppMain.vue"


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
    this.chiamataApi()
  },
  methods: {
      chiamataApi(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien')
        .then((res) =>{
         
          const dataApi = res.data.data
          this.store.arrayCard = dataApi
          console.log(dataApi)
        })
      }
    }
}
</script>

<template>
  <AppMain/>

</template>

<style lang="scss">
@use './style/main.scss';
</style>
