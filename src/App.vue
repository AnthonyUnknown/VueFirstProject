<template>
<div>
    <button-base @click="openModal">Создать пост</button-base>
<modal-base @closeModal="closeModal" v-model:show="showModal">
    <post-form @createPost="createPost" />
</modal-base>
<div v-if="loading">Loading posts...</div>
<post-list v-else @deletePost="deletePost" :posts="posts" />
</div>
</template>

<script>
import PostForm from "./components/PostForm.vue"
import PostList from "./components/PostList.vue"
import ButtonBase from './components/UI/ButtonBase.vue'
import axios from "axios"
export default {
    components: {PostForm, PostList, ButtonBase},
    data () {
        return {
       posts: [],
       name: "",
       title: "",
            showModal: false,
        loading: true,
        }
    },
    methods: {
       createPost (post) {
        this.posts.push(post)
        this.showModal = false
       },
       deletePost (post) {
        this.posts = this.posts.filter((item) => item.id !== post.id)
       },
       openModal () {
        this.showModal = true
       },
       async getPosts () {
        try {
            const posts = await axios.get("https://jsonplaceholder.typicode.com/posts?_limit=10")
            this.posts = posts.data
            this.loading = false

        } catch (e) {
            alert("Ошибка")
        }
       }
    },
    mounted() {
        this.getPosts()
    }
}
</script>


<style scoped>
        
</style>