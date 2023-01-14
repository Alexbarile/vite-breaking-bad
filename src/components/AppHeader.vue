<script>
export default {
    
}
</script>

<template>
    <header>
        <div class="row pt-3 pb-3">
            <div class="col ms-5">
                <img src="../../public/img/yugioh.jpg" alt="">
                <h1>Yu-Gi-Oh Api</h1>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;
    
    header{
        width: 100%;
        .col{
            width: 100%;
            height: 100%;
            @include center;

            img{
                width: 150px;
            }

            h1{
                font-weight: 300;
            }
        }
    }
</style>