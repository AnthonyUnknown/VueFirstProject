<template>
<form >
    <input v-bind:value="name" @input="changeName" type="text" placeholder="Имя">
    <input v-bind:value="title" @input="changeTitle" type="text" placeholder="Описание">
    <button type="submit" @click="createPost">Создать пост</button>
</form>
<div class="post" v-for="post in posts">
<div>{{post.name}}</div>
<div>{{post.title}}</div>
</div>
</template>

<script>
export default {
    data () {
        return {
            posts: [
        {id: 1, name: "Пост1", title: "Описание поста 1"},
        {id: 2, name: "Пост2", title: "Описание поста 2"},
        {id: 3, name: "Пост3", title: "Описание поста 3"}
       ],
       name: "",
       title: "",
        }
    },
    methods: {
       changeName (event) {
        this.name = event.target.value
       },
       changeTitle (event) {
        this.title = event.target.value
       },
       createPost (event) {
        event.preventDefault()
        const newPost = {
            id: Date.now,
            name: this.name,
            title: this.title
        }
        this.posts = [...this.posts, newPost]
        this.name = ""
        this.title = ""
       }
    }
}
</script>


<style scoped>
        .post {
            border: 1px solid blue;
            padding: 20px;
            margin-top: 20px;
        }
</style>