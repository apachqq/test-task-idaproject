<template>
    <div>
        <div class="cards">
            <transition-group name="offer-list">
                <card-item
                        v-for="offer in offers"
                        :key="offer.id"
                        :offer="offer"
                        @remove="$emit('remove', offer)"
                ></card-item>
            </transition-group>
        </div>
    </div>
</template>

<script>
    import CardItem from '@/components/CardItem'

    export default {
        props: {
            offers: {
                type: Array,
                required: true
            }
        },
        components: {CardItem}
    }
</script>

<style lang="scss" scoped>
    .cards {
        display: flex;
        flex-wrap: wrap;
        margin-left: 380px;
    }

    .offer-list-item {
        display: inline-block;
        margin-right: 10px;
    }

    .offer-list-enter-active,
    .offer-list-leave-active {
        transition: all 0.7s ease;
    }

    .offer-list-enter-from,
    .offer-list-leave-to {
        opacity: 0;
        transform: translateY(130px);
    }

    .offer-list-move {
        transition: transform 0.8s ease;
    }

    @media screen and (max-width: 601px) {
        .cards {
            margin-left: 250px;
            margin-right: 0;
        }
    }
</style>
