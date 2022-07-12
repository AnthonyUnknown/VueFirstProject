<template>
<form >
    <input v-model="name" type="text" placeholder="Имя">
    <input v-model="title" type="text" placeholder="Описание">
    <button type="submit" @click="createNewPost">Создать пост</button>
</form>
</template>

<script>
export default {
    data () {
        return {
            name: "",
            title: "",
        }
    },
    methods: {
        createNewPost (event) {
             event.preventDefault()
        const newPost = {
            id: Date.now,
            name: this.name,
            title: this.title
        }
        this.$emit("createPost", newPost)
        this.name = ""
        this.title = ""
        }
    },
   
}
</script>

<style scoped>
.post {
            border: 1px solid blue;
            padding: 20px;
            margin-top: 20px;
        }
</style>