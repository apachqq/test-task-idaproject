<template>
    <div class="addProductSelect">
        <div>Добавление товара</div>
        <div>
            <select>
                <option disabled value="">По умолчанию</option>
                <option value=""></option>
            </select>
        </div>
    </div>
    <form>
        <div class="form-control">
            <label for="name">Наименование товара</label>
            <input type="text" id="name" placeholder="Введите наименование товара">
        </div>
        <div>
            <label for="description">Описание товара</label>
            <textarea type="text" id="description" cols="30" rows="7">Введите описание товара</textarea>
        </div>
        <div>
            <label for="url">Ссылка на изображение товара</label>
            <input type="url" id="url" placeholder="Введите ссылку">
        </div>
        <div>
            <label for="price">Цена товара</label>
            <input type="text" id="price" placeholder="Введите цену">
        </div>
        <button class="btn" @click.prevent>Добавить товар</button>
    </form>
</template>

<script>
</script>

<style lang="scss">
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
</style>
