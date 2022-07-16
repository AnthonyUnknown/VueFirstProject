<template>
  <div v-if="show" class="modal" @click.stop="closeModal">
    <div @click.stop class="modal-content">
        <slot></slot>
        <button-base @click="closeModal">Закрыть</button-base>
    </div>
  </div>
</template>

<script>
import ButtonBase from './ButtonBase.vue'
export default {
  components: { ButtonBase },
name: "modal-base",
props: {
    show: {
        type: Boolean,
        default: false
    }
},
methods: {
    closeModal () {
        this.$emit("update:show", false)
    }
}
}
</script>

<style scoped>

.modal {
    display: flex;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5)
}

.modal-content {
    display: flex;
    align-items: center;
    margin: 0 auto;
    padding: 20px;
    min-width: 200px;
    min-height: 200px;
    background: lightgreen;
    border-radius: 20px;
}

</style>