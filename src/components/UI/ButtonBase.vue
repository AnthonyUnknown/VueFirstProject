<template>
  <button class="button" type="button">
    <slot></slot>
  </button>
</template>
<script>
export default {
name: "button-base"
}
</script>

<style>
.button {
    border: 1px solid green;
    background: transparent;
    cursor: pointer;
}
</style>