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
    <div style="display: flex">
        <form>
            <div class="form-control">
                <label for="name">Наименование товара</label>
                <input type="text" id="name" placeholder="Введите наименование товара">
            </div>
            <div>
                <label for="description">Описание товара</label>
                <textarea type="text" id="description" placeholder="Введите описание товара" cols="30"
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
        <div>
            <div class="cards">
                <div class="card">
                    <img src="https://jmdv.ru/UserFiles/Image/img305_39266_big.jpg" width="332" height="200">
                    <div>Наименование товара</div>
                    <div>Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание
                        товара в
                        несколько строк
                    </div>
                    <div>10 000 руб.</div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
</script>

<style lang="scss">
    .cards {
        display: flex;
        flex-direction: row;

        .card {
            width: 332px;
            height: 423px;
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
        color: #B4B4B4;
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
    }

    input::placeholder {
        font-size: 12px;
        line-height: 15px;
        color: #B4B4B4;
        padding: 10px 0 11px 16px;
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

        .btn {
            background: #EEEEEE;
            border-radius: 10px;
            border: none;
            margin: 24px;
            padding: 10px 95px 11px 96px;
            white-space: nowrap;
        }
    }
</style>
