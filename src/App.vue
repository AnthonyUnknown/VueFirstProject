<template>
<div>
<post-form @createPost="createPost" />
<post-list :posts="posts" />
</div>
</template>

<script>
import PostForm from "./components/PostForm.vue"
import PostList from "./components/PostList.vue"
export default {
    components: {PostForm, PostList},
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
       createPost (post) {
        this.posts.push(post)
       }
    }
}
</script>


<style scoped>
        
</style>