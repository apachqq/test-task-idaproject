<template>
    <div class="select">
        <select @change="changeOption">
            <option>По умолчанию</option>
            <option
                    v-for="option in options"
                    :key="option.value"
                    :value="option.value"
            >
                {{ option.name }}
            </option>
        </select>
    </div>
</template>

<script>
    export default {
        props: {
            options: {
                type: Array,
                default: () => []
            }
        },
        methods: {
            changeOption(event) {
                this.$emit('update:modelValue', event.target.value)
            }
        }
    }
</script>

<style lang="scss" scoped>
    select {
        background: #FFFEFB;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        border-radius: 4px;
        border: none;
        padding: 10px 17px 11px 16px;
        appearance: none;
        font-weight: 400;
        font-size: 12px;
        line-height: 15px;
        color: black;
    }
</style>
