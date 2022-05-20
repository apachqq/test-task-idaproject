<template>
    <form>
        <div class="form-control">
            <label for="name">Наименование товара</label>
            <input type="text" id="name" placeholder="Введите наименование товара" required v-model.trim="name">
        </div>
        <div>
            <label for="description">Описание товара</label>
            <textarea id="description" placeholder="Введите описание товара" cols="30"
                      rows="7"></textarea>
        </div>
        <div>
            <label for="url">Ссылка на изображение товара</label>
            <input type="url" id="url" placeholder="Введите ссылку" required v-model.trim="url">
        </div>
        <div>
            <label for="price">Цена товара</label>
            <input type="number" id="price" placeholder="Введите цену" required v-model.trim="price">
        </div>
        <button class="btn" :class="{btnn : isValid}">Добавить товар</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                name: '',
                url: '',
                price: ''
            }
        },
        computed: {
            isValid() {
                return this.name !== '' && this.url !== '' && this.price !== ''
            }
        }
    }
</script>

<style lang="scss" scoped>
    .btnn {
        background: #7BAE73;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        border-radius: 10px;
    }
</style>
