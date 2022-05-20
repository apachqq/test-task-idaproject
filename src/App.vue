<template>
    <the-header></the-header>
    <div style="display: flex">
        <the-form
                @create="createOffer"
        ></the-form>
        <offer-list
                :offers="offers"
                @remove="removeOffer"
        ></offer-list>
    </div>
</template>

<script>
    import TheForm from '@/components/TheForm'
    import TheHeader from '@/components/TheHeader'
    import OfferList from '@/components/OfferList'

    export default {
        data() {
            return {
                offers: [
                    {
                        id: 1,
                        title: 'Наименование товара',
                        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '10 000'
                    }
                ]
            }
        },
        methods: {
            createOffer(offer) {
                this.offers.push(offer)
            },
            removeOffer(offer) {
                this.offers = this.offers.filter(o => o.id !== offer.id)
            }
        },
        components: {TheForm, TheHeader, OfferList}
    }
</script>

<style lang="scss">
    .cards {
        display: flex;
        flex-wrap: wrap;

        .card {
            width: 332px;
            margin: 16px;
            background: #FFFEFB;
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
            border-radius: 4px;

            &:hover .delete-icon {
                opacity: 1;
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
    }

    .addProductSelect {
        display: flex;
        justify-content: space-between;

        div:nth-child(1) {
            margin: 30px 0 16px 32px;
            font-weight: 600;
            font-size: 28px;
            line-height: 35px;
        }

        div:nth-child(2) {
            margin: 32px 32px 0 0;
        }
    }

    label {
        display: block;
        font-weight: 400;
        font-size: 10px;
        line-height: 13px;
        letter-spacing: -0.02em;
        padding-bottom: 4px;
    }

    textarea {
        width: 284px;
        background: #FFFEFB;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        border: none;
        font-size: 12px;
        line-height: 15px;
        color: #3F3F3F;
        padding: 10px 0 0 16px;
        resize: none;
    }

    textarea::placeholder {
        font-size: 12px;
        line-height: 15px;
        color: #B4B4B4;
        padding-left: 1px;
    }

    input {
        background: #FFFEFB;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        border: none;
        width: 284px;
        height: 36px;
        padding: 10px 0 11px 16px;
    }

    input::placeholder {
        font-size: 12px;
        line-height: 15px;
        color: #B4B4B4;
    }

    form {
        box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02);
        border-radius: 4px;
        width: 332px;
        height: 440px;
        margin: 16px 16px 0 32px;


        div:nth-child(1) {
            margin: 24px 24px 16px 24px;
        }

        div:nth-child(2),
        div:nth-child(3) {
            margin: 16px 24px 16px 24px;
        }

        div:nth-child(4) {
            margin: 16px 24px 0 24px;
        }
    }
</style>
