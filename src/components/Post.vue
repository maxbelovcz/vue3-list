<template>
    <div class="content">
        <div class="container">
            <div class="content__wrapper">
                <div class="title">Список постов</div>
                <div class="post" v-for="post in posts">
                    <div class="post__text"><span>Название:</span>{{ post.title }}</div>
                    <div class="post__text"><span>Описание:</span>{{ post.description }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Post',
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>