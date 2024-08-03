<template>
    <div class="post">
        <div class="post__item">
            <div class="post__text"><span>Название:</span>{{ post.title }}</div>
            <div class="post__text"><span>Описание:</span>{{ post.body }}</div>
        </div>
        <div class="post__buttons">
            <my-button type="button" class="button">Изменить</my-button>
            <my-button type="button" class="button" @click="$emit('remove', post)">Удалить</my-button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PostItem',
    props: {
        post: {
            type: Object,
            required: true
        }
    }
}

</script>