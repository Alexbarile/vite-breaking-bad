<script>

export default {
    props: {
        option: Object,
    },
    data() {
        return {
            change: "",
        }
    },
}
</script>

<template lang="">
    <!-- select -->

    <div class="select">
    
        <!-- creo l'$emit con il v-model  -->
        
        <select class="form-select w-25" id="floatingSelect" aria-label="Floating label select example" v-model="change" @change="$emit('selection', change)">
            <option value="" disabled selected>Choose the Cards</option>
            <option v-for="(item, index) in option" :key="index" :value="item.archetype_name">{{item.archetype_name}}</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;

    .select{
        padding: 25px;
    }
</style>