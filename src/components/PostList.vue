<template>
<post-item @deletePost="$emit('deletePost', post)" v-for="post in posts" :post="post" :key="post.id" />
</template>

<script>
import PostItem from "@/components/PostItem"
    export default {
        components: {
            PostItem
        },
        props: {
            posts: {
                type: Array,
                required: true,
            }
        },
        methods: {
            
        }
    }
</script>

<style scoped>

</style>
