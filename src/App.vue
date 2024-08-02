<template>
    <div class="wrapper">
        <main class="page">
            <Form />
            <Post :posts="posts" />
        </main>
    </div>
</template>

<script>
import Post from './components/Post.vue';
import Form from './components/Form.vue';
export default {
    name: 'App',
    components: { Post, Form },
    data() {
        return {
            posts: [
                { id: 1, title: 'Наименование поста1', description: 'Описание поста1' },
                { id: 2, title: 'Наименование поста2', description: 'Описание поста2' },
                { id: 3, title: 'Наименование поста3', description: 'Описание поста3' }
            ],
            title: '',
            description: ''
        }
    },
    methods: {
        createPost() {
            const newPost = {
                id: Date.now(),
                title: this.title,
                description: this.description
            }
            this.posts.push(newPost);
            this.title = '';
            this.description = '';
        },
    }
}
</script>

<style lang="scss">
@import '@/assets/scss/main.scss';
</style>