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
            <select name="" v-model="store.selectType" @click="$emit('pippo')">
                <option value="" disabled>--Cerca per Archetipo--</option>
                <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayArchetype" :key="index">{{ elem.archetype_name }}</option>
            </select>
            <div class="container text-center " v-if="store.soldatino">
                <h1>LOADING...</h1>
            </div>
            <div class="container row" v-else>
                <SingleCard v-for="( elem,index ) in store.arrayCard" :key="index" :infoCarta="elem"/>
            </div>
</template>

<style lang="scss" scoped>
.container{
    margin: 0 auto;
}
</style>