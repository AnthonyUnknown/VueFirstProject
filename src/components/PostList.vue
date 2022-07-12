<template>
<div class="post" v-for="post in posts">
<div>{{post.name}}</div>
<div>{{post.title}}</div>
</div>
</template>

<script>
    export default {
        props: {
            posts: {
                type: Array,
                required: true,
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
