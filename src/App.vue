<template>
  <div class="post" v-for="post in posts" v-bind:key="post.id">
    <div><strong>Название: </strong>{{ post.title }}</div>
    <div><strong>Описание: </strong>{{ post.body }}</div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      likes: 0,
      dislikes: 5,
      posts: [
        { id: 1, title: 'Информация о JavaScript1', body: 'Описание поста1' },
        { id: 2, title: 'Информация о JavaScript2', body: 'Описание поста2' },
        { id: 3, title: 'Информация о JavaScript3', body: 'Описание поста3' },
        { id: 4, title: 'Информация о JavaScript4', body: 'Описание поста4' },
        { id: 5, title: 'Информация о JavaScript5', body: 'Описание поста5' },
      ],
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDisLike() {
      this.dislikes += 1;
    },
  },
};
</script>

<!-- <style scoped></style> Флаг scoped означает, что стили будут доступны только текущему компоненту -->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  padding: 15px;
  border: 2px solid teal;
  margin: 15px 15px 0;
}
</style>
