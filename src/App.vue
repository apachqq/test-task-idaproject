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
