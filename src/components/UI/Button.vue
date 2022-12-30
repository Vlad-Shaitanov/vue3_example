<template>
  <button class="form_button">
    <slot></slot>
  </button>
</template>

<script lang="ts">
export default {
  // Имя компонента
  name: 'my-button',
};
</script>

<style scoped>
.form_button {
  margin-top: 15px;
  margin-bottom: 30px;
  padding: 10px;
  background: none;
  border: 2px solid rgb(6, 223, 219);

  width: 100px;
}
</style>
