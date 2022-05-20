<template>
    <div class="card">
        <img :src="offer.picture" width="332" height="200" />
        <img class="delete-icon" src="img/delete.svg" @click="$emit('remove', offer)" />
        <div class="card-name">{{ offer.title }}</div>
        <div class="card-description">{{ offer.body }}</div>
        <div class="card-price">{{ offer.price }} руб.</div>
    </div>
</template>

<script>
    export default {
        props: {
            offer: {
                type: Object
            }
        }
    }
</script>

<style scoped>
</style>
