<script>
import SingleCard from './SingleCard.vue';
import { store } from '../store';
export default{
    name:"AppMain",
    components:{
        SingleCard
    },
    data(){
        return{
            store
        }
    }
}
</script>

<template>
    <div class="container row">
        <SingleCard v-for="( elem,index ) in store.arrayCard" :key="index" :infoCarta="elem"/>
    </div>
</template>

<style lang="scss" scoped>
.container{
    margin: 0 auto;
}
</style>