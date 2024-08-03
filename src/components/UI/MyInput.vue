<template>
    <input class="input" :placeholder="placeholder" :value="modelValue" @input="updateInput">
</template>
<script>
export default {
    name: 'my-input',
    props: {
        modelValue: {
            type: [String, Number],
            default: ''
        },
        placeholder: {
            type: [String, Number],
            default: ''
        }
    },
    methods: {
        updateInput(event) {
            this.$emit('update:modelValue', event.target.value);
        }
    }
}
</script>