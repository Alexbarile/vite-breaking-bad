<script>
import { store } from '../store';
export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<template lang="">
    <!-- select -->

    <div class="select">
        <select class="form-select w-25" id="floatingSelect" aria-label="Floating label select example">
            <option selected>Scegli la carta</option>
            <option value="1">Alien</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
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