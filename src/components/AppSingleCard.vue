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
        <h4>{{ character.name }}</h4>
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
        transition: 1s;
        @include upbold;
        width: calc(100% / 5 - 30px);

        &:hover{
            transform: scale(1.1);
            box-shadow: 0 0 8px 5px rgb(87, 43, 43);
           
            h4{
                font-size: 20px;
                text-shadow: 5px 5px 5px red; 
            }
        }
        
        h4{
            color: white;
            font-size: 17px;
            font-weight: 500;
            transition: 1s;
        }

        h5{
            font-size: 15px;
            font-weight: 300;
        }
        .img-card{
            img{
                width: 200px;
            }
        }
    }
</style>