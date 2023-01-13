<script>

export default {
    props: {
        card: Object,
    }
    
}
</script>

<template>
    <div>
        <img :src="card.card_images[0].image_url" alt="card.name" />
        <span>{{ card.name }}</span>
        <span>{{ card.archetype }}</span>
    </div>
</template>

<style lang="scss" scoped>
// @use '../styles/partials/mixins' as *;
// @use '../styles/partials/variables' as *;
</style>