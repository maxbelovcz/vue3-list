<template>
    <div class="modal" v-if="show" @click="hideModal">
        <div class="modal__content" @click.stop>
            <slot></slot>
        </div>
    </div>
</template>
<script>
export default {
    name: 'my-modal',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    }
    ,
    methods: {
        hideModal() {
            this.$emit('update:show', false);
        }
    }
}
</script>