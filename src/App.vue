<script>
import AppHeader from './components/AppHeader.vue';
import AppCards from './components/AppCards.vue';

export default {
  components: {
    AppHeader,
    AppCards,
  }
}

</script>

<template>
  <AppHeader></AppHeader>
  <AppCards></AppCards>
  
</template>

<style lang="scss">
@use './styles/generals.scss' as *;

</style>
