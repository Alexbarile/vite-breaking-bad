<script>
import {store} from '../store.js'
export default {
    data() {
        return {
            store
        }
    },
    
}
</script>

<template>
    <div>
        {{ store }}
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;
</style>