<template>
    <div class="sss">
        <div class="addProductSelect">
            <div>Добавление товара</div>
            <my-select
                    v-model="selectedSort"
                    :options="sortOptions"
            ></my-select>
        </div>
        <div class="main">
            <the-form
                    @create="createOffer"
            ></the-form>
            <offer-list
                    :offers="offers"
                    @remove="removeOffer"
            ></offer-list>
        </div>
    </div>
</template>

<script>
    import TheForm from '@/components/TheForm'
    import OfferList from '@/components/OfferList'
    import MySelect from '@/components/MySelect'

    export default {
        data() {
            return {
                offers: [
                    {
                        id: 1,
                        title: 'Ваименование товара',
                        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '10000'
                    },
                    {
                        id: 2,
                        title: 'Бмя',
                        body: 'Описание',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '6500'
                    },
                    {
                        id: 3,
                        title: 'Текст',
                        body: 'Текст',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '7700'
                    },
                    {
                        id: 4,
                        title: 'Ааа',
                        body: 'Ааа',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '1200'
                    }
                ],
                selectedSort: '',
                sortOptions: [
                    {value: 'title', name: 'По наименованию'},
                    {value: 'min', name: 'Сначала дешёвые'},
                    {value: 'max', name: 'Сначала дорогие'}
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
        watch: {
            selectedSort(newValue) {
                console.log(newValue)
                if (newValue === 'title') {
                    this.offers.sort((offer1, offer2) => {
                        return offer1[newValue]?.localeCompare(offer2[newValue])
                    })
                }
                if (newValue === 'min') {
                    this.offers.sort((offer1, offer2) => {
                        return offer1.price - offer2.price
                    })
                }
                if (newValue === 'max') {
                    this.offers.sort((offer1, offer2) => {
                        return offer2.price - offer1.price
                    })
                }
            }
        },
        components: {TheForm, OfferList, MySelect}
    }
</script>

<style lang="scss">
    .main {
        display: flex;
    }

    .cards {
        display: flex;
        flex-wrap: wrap;
        margin-left: 380px;

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
        outline: none;

        &:focus {
            outline: 2px solid green;
        }
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
        outline: none;

        &:focus {
            outline: 2px solid green;
        }
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
        position: fixed;


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
