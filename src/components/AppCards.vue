<script>
import axios from 'axios'; 
import AppSelect from './AppSelect.vue';
import AppSingleCard from './AppSingleCard.vue';
import {store} from '../store.js'

export default {
    components: {
        AppSelect,
        AppSingleCard,
    },
    data() {
        return {
            store
        }
    },
    methods: {

        // creo funzione per l'AppSelect

        select_archetype( item ) {
            axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${item}`).then((response)=>{
            store.cardList = response.data.data;
            store.loading = false
            })
        }
    }
}
</script>

<template>
    <div class="bg-orange">
        <div class="container">

            <!-- caricamento -->

            <div v-if="store.loading" class="loading">
                <h4>Caricando</h4>
                <div class="lds-ring"><div></div><div></div><div></div><div></div></div>
            </div>
            <div v-else>

                <!-- select -->

                <!-- richiamo il props dell'AppSelect e il punto di ancoraggio dell'$emit -->

                <AppSelect :option="store.archetypeList" @selection="select_archetype"></AppSelect>

                <!-- main card -->

                <div class="container-white">
                    <div class="container-card pt-5">
                        <div class="top-bar p-4 mb-3">
                            <h4 class="text-white">Found 39 cards</h4>
                        </div>
                        <div class="card-list">

                            <!-- richiamo props di AppSingleCard -->

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

        // barra di caricamento
        .loading{
            width: 100%;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;

            h4{
                font-size: 20px;
                font-weight: 400;
                margin-right: 20px;
            }
            
            // elemento di caricamento
            .lds-ring {
                display: inline-block;
                position: relative;
                width: 80px;
                height: 80px;
                }
                .lds-ring div {
                    box-sizing: border-box;
                    display: block;
                    position: absolute;
                    width: 50px;
                    height: 50px;
                    margin: 8px;
                    border: 5px solid #fff;
                    border-radius: 50%;
                    animation: lds-ring 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
                    border-color: #fff transparent transparent transparent;
                }
                .lds-ring div:nth-child(1) {
                    animation-delay: -0.45s;
                }
                .lds-ring div:nth-child(2) {
                    animation-delay: -0.3s;
                }
                .lds-ring div:nth-child(3) {
                    animation-delay: -0.15s;
                }
                @keyframes lds-ring {
                0% {
                    transform: rotate(0deg);
                }
                100% {
                    transform: rotate(360deg);
                }
            }
        }

        // sezione carte
        .container-white{
            .container-card{
                .top-bar{
                    width: 100%;
                    background-color: rgb(40, 40, 40);

                    h4{
                        font-size: 20px;
                        margin: 0;
                    } 
                }

                // disposizione carte
                .card-list{
                    height: 100vh;
                    overflow: scroll;
                    display: flex;
                    flex-wrap: wrap;
                }
            }
        }
    }
</style>