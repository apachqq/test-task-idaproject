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
                    v-if="isOffersLoaded"
            ></offer-list>
            <the-loader class="loader" v-else></the-loader>
        </div>
    </div>
</template>

<script>
    import TheForm from '@/components/TheForm'
    import OfferList from '@/components/OfferList'
    import MySelect from '@/components/MySelect'
    import TheLoader from '@/components/TheLoader'

    export default {
        data() {
            return {
                offers: [
                    {
                        id: 1,
                        title: 'IP-камера видеонаблюдения Axis Q1635-E',
                        body: 'Камера может не только работать при температуре -40°C, но и включаться при этой температуре после аварийного отключения электропитания.',
                        picture: 'https://ipvs.ru/upload/iblock/5e0/IP_______________582af60d5d7d8[1].jpg',
                        price: '149831'
                    },
                    {
                        id: 2,
                        title: 'Наименование товара',
                        body: 'Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк',
                        picture: 'https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg',
                        price: '10000'
                    },
                    {
                        id: 3,
                        title: 'Камера видеонаблюдения ТЕЛЕКОМ-МАСТЕР 4G Точка Зрения Вьюга',
                        body: '«Точка зрения Вьюга» уличная камера с температурным режимом -35°С / +50°С. на базе 4g LTE IP модуля с поддержкой протокола ONVIF.',
                        picture: 'https://cdnmedia.220-volt.ru/content/products/197/197243/images/original/n1200x800_q80/1.jpeg',
                        price: '26599'
                    },
                    {
                        id: 4,
                        title: 'Камера видеонаблюдения 4G 2Мп 1080P PST GBK20T',
                        body: 'Уличная компактная камера, работающая в 3G/4G сетях. В камеру можно установить сим карту любого оператора. Сим карта должна поддерживать 3G/4G протоколы передачи данных.',
                        picture: 'https://rusmarta.ru/upload/resize_cache/iblock/5eb/1000_1000_138bc3980d02b28565b325bedea7c3638/GBK50_2.jpg',
                        price: '8599'
                    }
                ],
                sortOptions: [
                    {value: 'title', name: 'По наименованию'},
                    {value: 'min', name: 'Сначала дешёвые'},
                    {value: 'max', name: 'Сначала дорогие'}
                ],
                selectedSort: '',
                isOffersLoaded: false
            }
        },
        mounted() {
            setTimeout(() => {
                this.isOffersLoaded = true
            }, 2500)
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
        components: {TheForm, OfferList, MySelect, TheLoader}
    }
</script>

<style lang="scss">
    .main {
        display: flex;

        .loader {
            display: flex;
            flex-wrap: wrap;
            margin-left: 380px;
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
    }
</style>
