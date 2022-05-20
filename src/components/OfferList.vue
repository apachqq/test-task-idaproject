<template>
    <div>
        <div class="cards">
            <transition-group name="offer-list">
                <card-item
                        v-for="offer in offers"
                        :key="offer.id"
                        :offer="offer"
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
                type: Array
            }
        },
        components: {CardItem}
    }
</script>
<!--222-->
<style scoped>
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
</style>
