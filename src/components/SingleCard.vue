<script>

export default{
    name:"SingleCard",
    props:["infoCarta"]
}
</script>

<template>
    
        
            <div class="col-12 col-md-4 col-lg-2 mia-card">
                <img :src="infoCarta.card_images[0].image_url" alt="">
                <h3>{{ infoCarta.name }}</h3>
                <span>{{ infoCarta.archetype }}</span>
            </div>
        
</template>

<style lang="scss" scoped>
    .mia-card{
        text-align: center;
        img{
            width: 100%;
        }
    }

</style>