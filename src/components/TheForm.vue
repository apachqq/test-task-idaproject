<template>
    <form>
        <div class="form-control">
            <label for="name">Наименование товара</label>
            <input type="text" id="name" placeholder="Введите наименование товара" required>
        </div>
        <div>
            <label for="description">Описание товара</label>
            <textarea id="description" placeholder="Введите описание товара" cols="30"
                      rows="7"></textarea>
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

<style scoped>
</style>
