<template>
  <button class="btn" :type="btnType">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'my-button',
  props: {
    btnType: {
      type: String,
    }
  }
}
</script>

<style scoped>
.btn {
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

.btn:active {
  background: teal;
  color: white;
}
</style>