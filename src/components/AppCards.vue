<script>
import AppSingleCard from './AppSingleCard.vue';
import {store} from '../store.js'
export default {
    components: {
        AppSingleCard,
    },
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="bg-orange">
        <div class="container height-100vh">
            <div v-if="store.loading" class="loading">
                <h4>Caricando</h4>    
            </div>
            <div v-else>
                <div class="select">
                    <select class="form-select w-25" id="floatingSelect" aria-label="Floating label select example">
                        <option selected>Scegli la carta</option>
                        <option value="1">Alien</option>
                        <option value="2">Two</option>
                        <option value="3">Three</option>
                    </select>
                </div>
                <div class="container-white">
                    <div class="container-card pt-5">
                        <div class="top-bar p-4 mb-3">
                            <h4 class="text-white">Found 39 cards</h4>
                        </div>
                        <div class="card-list">
                            <AppSingleCard v-for="(item, index) in store.cardList" :key="index" :character="item"></AppSingleCard>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;

    .bg-orange{
        background-color: $orange;
        width: 100%;
        .height-100vh{
            height: 100vh;
        }

        // barra di caricamento
        .loading{
            position: relative;
            width: 100%;
            height: 100%;

            h4{
                position: absolute;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                font-size: 20px;
                font-weight: 400;
            }
        }

        // sezione select
        .select{
            padding: 25px;
        }

        // sezione carte

        .container-white{
            .container-card{
                .top-bar{
                    width: 100%;
                    background-color: black;

                    h4{
                        font-size: 20px;
                        margin: 0;
                    } 
                }
                .card-list{
                    display: flex;
                    justify-content: center;
                }
            }
        }
    }
</style>