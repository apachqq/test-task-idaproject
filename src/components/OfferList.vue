<template>
    <div>
        <div class="cards">
            <card-item
                    v-for="offer in offers"
                    :key="offer.id"
                    :offer="offer"
            ></card-item>
        </div>
    </div>
</template>

<script>
    import CardItem from '@/components/CardItem'

    export default {
        props: {
            offers: {
                type: Array
            }
        },
        components: {CardItem}
    }
</script>

<style scoped>
</style>
