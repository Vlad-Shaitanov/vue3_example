<template>
  <div class="wrap">
    <PostFormVue @create="createPost" />
    <!-- Привязываем posts к компоненту и передаем как пропсы -->
    <PostListVue v-bind:posts="posts" />
  </div>
</template>

<script lang="ts">
import PostListVue from './components/PostList.vue';
import PostFormVue from './components/PostForm.vue';
export default {
  //Регистрируем компоненты
  components: {
    PostListVue,
    PostFormVue,
  },

  data() {
    return {
      likes: 0,
      dislikes: 5,
      posts: [
        { id: 1, title: 'Информация о JavaScript 1', body: 'Описание поста 1' },
        { id: 2, title: 'Информация о JavaScript 2', body: 'Описание поста 2' },
        { id: 3, title: 'Информация о JavaScript 3', body: 'Описание поста 3' },
        { id: 4, title: 'Информация о JavaScript 4', body: 'Описание поста 4' },
        { id: 5, title: 'Информация о JavaScript 5', body: 'Описание поста 5' },
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

    createPost(post: any) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.wrap {
  margin: 15px 15px;
  border: 2px solid #c1c1c1;
  padding-top: 15px;
  padding-bottom: 15px;
}
</style>
