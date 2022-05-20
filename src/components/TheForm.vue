<template>
    <form>
        <div class="form-control">
            <label for="name">Наименование товара</label>
            <input type="text" id="name" placeholder="Введите наименование товара" required v-model.trim="offer.title">
        </div>
        <div>
            <label for="description">Описание товара</label>
            <textarea id="description" placeholder="Введите описание товара" cols="30"
                      rows="7" v-model.trim="offer.body"></textarea>
        </div>
        <div>
            <label for="url">Ссылка на изображение товара</label>
            <input type="url" id="url" placeholder="Введите ссылку" required v-model.trim="offer.picture">
        </div>
        <div>
            <label for="price">Цена товара</label>
            <input type="number" id="price" placeholder="Введите цену" required v-model.trim="offer.price">
        </div>
        <button class="btn" :class="{'btn-isValid' : isValid}" @click.prevent="createOffer">Добавить товар</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                offer: {
                    title: '',
                    body: '',
                    picture: '',
                    price: ''
                }
            }
        },
        methods: {
            createOffer() {
                this.offer.id = Date.now();
                this.$emit('create', this.offer)
                this.offer = {
                    title: '',
                    body: '',
                    picture: '',
                    price: ''
                }
            }
        },
        computed: {
            isValid() {
                return this.offer.title !== '' && this.offer.picture !== '' && this.offer.price !== ''
            }
        }
    }
</script>

<style lang="scss" scoped>
    .btn {
        border-radius: 10px;
        border: none;
        margin: 24px;
        padding: 10px 95px 11px 96px;
        white-space: nowrap;
    }

    .btn-isValid {
        background: #7BAE73;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    }
</style>
