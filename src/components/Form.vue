<template>
    <div class="content">
        <div class="container">
            <div class="content__wrapper">
                <form class="form" action="" @submit.prevent>
                    <div class="title">Создать новый пост</div>
                    <input class="input" type="text" placeholder="Название" v-bind:value="title"
                        @input="title = $event.target.value">
                    <input class="input" type="text" placeholder="Описание" v-bind:value="description"
                        @input="description = $event.target.value">
                    <button class="button" type="button" @click="createPost">Создать</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Form'
}

</script>