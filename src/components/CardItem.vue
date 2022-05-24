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
    .card {
        width: 332px;
        margin: 16px;
        background: #FFFEFB;
        box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;

        &:hover .delete-icon {
            opacity: 1;
        }

        .scale {
            display: block;
            overflow: hidden;
            transition: 1s;

            &:hover {
                transform: scale(1.2);
            }
        }

        .delete-icon {
            opacity: 0;
            position: relative;
            bottom: 215px;
            left: 310px;
            padding: 0;
            margin: 0;
        }

        .card-name {
            font-weight: 600;
            font-size: 20px;
            line-height: 25px;
            color: #3F3F3F;
            padding: 16px 115px 0 16px;
        }

        .card-description {
            font-weight: 400;
            font-size: 16px;
            line-height: 20px;
            color: #3F3F3F;
            padding: 16px 16px 0 16px;
        }

        .card-price {
            font-weight: 600;
            font-size: 24px;
            line-height: 30px;
            color: #3F3F3F;
            padding: 32px 199px 24px 16px;
        }
    }

    @media screen and (max-width: 700px) {
        .card {
            width: 400px;

            .scale {
                width: 400px;
            }
        }
    }

    @media screen and (max-width: 550px) {
        .card {
            width: 300px;

            .scale {
                width: 300px;
            }
        }
    }
</style>
