<template>
  <div>
    <h3>Список пользователей</h3>
    <!-- Директива v-for="post in posts" позволяет нам отрендерить элементы на основе массива
		Директива v-bind:key="post.id" создает для каждого элемента свой ключ -->
    <PostItemVue class="post" v-for="post in posts" v-bind:key="post.id" :post="post" />
  </div>
</template>

<script lang="ts">
import PostItemVue from './PostItem.vue';
export default {
  components: {
    PostItemVue,
  },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style></style>
