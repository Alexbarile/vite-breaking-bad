<script>
import AppHeader from './components/AppHeader.vue';
import AppCards from './components/AppCards.vue';
import axios from 'axios';
import {store} from './store.js';

export default {
  components: {
    AppHeader,
    AppCards,
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
        store.cardList = response.data
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
