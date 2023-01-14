<script>

export default {
    props: {
        character: Object
    }
    
}
</script>

<template>
    <div>
        <img :src="character.card_images[0].image_url" :alt="character.name" />
        <span>{{ character.name }}</span>
        <span>{{ character.archetype }}</span>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/mixins' as *;
@use '../styles/partials/variables' as *;
</style>