<template>
  <div class="post">
    <div>
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
    <div class="post_btns">
      <my-button>Удалить</my-button>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<!-- Флаг scoped означает, что стили будут доступны только текущему компоненту -->
<style scoped>
.post {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
  border: 2px solid teal;
  margin: 15px 15px 0;
}
</style>
