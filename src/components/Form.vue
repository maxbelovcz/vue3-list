<template>
    <form class="form" action="" @submit.prevent>
        <div class="title">Создать новый пост</div>
        <my-input placeholder="Название" v-model.trim="post.title"></my-input>
        <my-input placeholder="Описание" v-model.trim="post.body"></my-input>
        <my-button class="button" type="button" @click="createPost">Создать</my-button>
    </form>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            post: {
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post);
            this.post = {
                title: '',
                body: ''
            }
        }
    }
}

</script>