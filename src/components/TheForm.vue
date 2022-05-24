<template>
    <form @submit.prevent="createOffer">
        <div>
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
        <button class="btn" :class="{'btn-isValid' : isValid}">Добавить товар</button>
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
