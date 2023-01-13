<script>
import AppSingleCard from './AppSingleCard.vue';
import {store} from '../store'
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
    <div v-if="store.loading">
            Caricando
        </div>
    <div>
        <AppSingleCard v-for="(item, index) in store.cardList" :key="index" :card="item"></AppSingleCard>
    </div>
</template>

<style lang="scss" scoped>
// @use '../styles/partials/mixins' as *;
// @use '../styles/partials/variables' as *;


</style>