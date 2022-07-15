<template>
<div class="post">
<div>{{post.name}}</div>
<div>{{post.title}}</div>
<button-base @click="deletePost">Удалить пост</button-base>
</div>
</template>

<script>
export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    },
    methods: {
        deletePost() {
            this.$emit("deletePost", this.post)
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