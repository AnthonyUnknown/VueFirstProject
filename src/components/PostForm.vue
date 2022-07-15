<template>
<form>
    <input-base v-model:value="name" placeholder="Название" />
    <input-base v-model:value="title" placeholder="Описание" />
    <button-base @click="createNewPost">Создать пост</button-base>
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
</style>