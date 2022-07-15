<template>
  <input :value="value" @input="changeValue" type="text">
</template>

<script>
export default {
    name: "input-base",
    props: {
        value: [String, Number]
    },
    methods: {
        changeValue(event) {
            this.$emit("update:value", event.target.value)
        }
    }
}
</script>

<style>

</style>