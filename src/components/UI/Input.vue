<template>
  <input class="input" type="text" v-bind:value="modelValue" @input="updateInput" />
</template>

<script lang="ts">
export default {
  name: 'my-input',

  props: {
    modelValue: [String, Number],
  },

  methods: {
    updateInput(event: any) {
      this.$emit('update:modelValue', event.target.value);
    },
  },
};
</script>

<style scoped>
.input {
  width: 100%;
  border: 2px solid rgb(6, 223, 219);
  padding: 10px 15px;
  margin-top: 10px;
}

.input:first-child {
  margin-top: 0;
}
</style>
