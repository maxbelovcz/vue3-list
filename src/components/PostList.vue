<template>
    <div class="content">
        <div class="container">
            <div class="content__wrapper" v-if="posts.length > 0">
                <div class="title">Список постов</div>
                <PostItem v-for="post in posts" :post="post" :key="post.id" @remove="$emit('remove', post)"></PostItem>
            </div>
            <div class="content__wrapper" v-else>
                <div class="title">Список постов пуст</div>
            </div>
        </div>
    </div>
</template>

<script>
import PostItem from './PostItem.vue'
export default {
    name: 'postList',
    components: {
        PostItem
    },
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>