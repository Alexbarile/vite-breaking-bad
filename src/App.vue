<script>
import AppHeader from './components/AppHeader.vue';
import AppCards from './components/AppCards.vue';
import AppSingleCard from './components/AppSingleCard.vue';
import axios from 'axios';
import {store} from './store';

export default {
  components: {
    AppHeader,
    AppCards,
    AppSingleCard,
  },
  data() {
    return {
      store
    }
  },
  created(){
    this.listCard();
  },
  methods: {
    listCard(){
      axios.get(store.url).then((response)=>{
        store.cardList = response.data;
        this.loading = false;
      })
    }
  },
}

</script>

<template>
  <AppHeader></AppHeader>
  <AppCards></AppCards>
  
</template>

<style lang="scss">
@use './styles/generals.scss' as *;

</style>
