<script>

export default {
    props: {
        character: Object
    }
    
}
</script>

<template>
    <div class="cards">
        <div class="img-card mb-3">
            <img :src="character.card_images[0].image_url" :alt="character.name" />
        </div>
        <h4 class="text-white">{{ character.name }}</h4>
        <h5>{{ character.archetype }}</h5>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;

    .cards{
        background-color: $orange;
        text-align: center;
        margin: 15px;
        
        @include upbold;
        width: calc(100% / 5 - 30px);

        h4{
            font-size: 17px;
            font-weight: 500;
        }

        h5{
            font-size: 17px;
            font-weight: 300;
        }
        .img-card{
            img{
                width: 200px;
            }
        }
    }
</style>