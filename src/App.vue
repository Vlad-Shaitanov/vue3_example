<template>
  <div>
    Количество лайков: <strong>{{ likes }}</strong>
  </div>
  <div>
    Количество дизлайков: <strong>{{ dislikes }}</strong>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      likes: 0,
      dislikes: 5,
    };
  },
};
</script>

<style></style>
