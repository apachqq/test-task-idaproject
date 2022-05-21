<template>
    <div class="select">
        <select @change="changeOption">
            <option value="">По умолчанию</option>
            <option
                    v-for="option in options"
                    :key="option.value"
                    :value="option.value"
            >{{ option.name }}</option>
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

<style scoped>
    .select {

    }
</style>
