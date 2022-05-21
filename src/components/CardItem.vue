<template>
    <div class="card">
        <img class="scale" :src="offer.picture" width="332" height="200"/>
        <img class="delete-icon" src="img/delete.svg" @click="$emit('remove', offer)"/>
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

<style lang="scss" scoped>
    .scale {
        display: block;
        overflow: hidden;
        transition: 1s;

        &:hover {
            transform: scale(1.2);
        }
    }
</style>
