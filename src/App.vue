<template>
    <div class="wrapper">
        <main class="page">
            <div class="content">
                <div class="container">
                    <div class="content__wrapper">
                        <div class="title">Страница с постами</div>
                        <my-button @click="showModal">Создать пост</my-button>
                    </div>
                </div>
            </div>
            <my-modal v-model:show="modalVisible">
                <Form @create="createPost" />
            </my-modal>
            <PostList :posts="posts" @remove="removePost" v-if="!isPostLoading" />
            <div class="title" v-else>Идет загрузка...</div>
        </main>
    </div>
</template>

<script>
import PostList from './components/PostList.vue';
import Form from './components/Form.vue';
import axios from 'axios';
export default {
    name: 'App',
    components: {
        PostList, Form
    },
    data() {
        return {
            posts: [],
            modalVisible: false,
            isPostLoading: false,
        }
    },
    methods: {
        createPost(post) {
            this.posts.push(post);
            this.modalVisible = false;
        },
        removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id)
        },
        showModal() {
            this.modalVisible = true
        },
        async fetchPosts() {
            try {
                this.isPostLoading = true;
                const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
                this.posts = response.data;
            } catch (error) {
                alert('Ошибка получения данных')
            } finally {
                this.isPostLoading = false;
            }
        }
    },
    mounted() {
        this.fetchPosts();
    }
}
</script>

<style lang="scss">
@import '@/assets/scss/main.scss';
</style>