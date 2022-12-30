<template>
  <!-- Модификатор @submit.prevent эквивалентен event.preventDefault() -->
  <form class="form" @submit.prevent>
    <h4>Создание поста</h4>
    <!-- Директива v-model позволяет реализовать двустороннее связывание компонентов более лаконично -->
    <my-input type="text" placeholder="Название поста" v-model="post.title" />
    <!-- Директива v-bind:value="title" связывает инпут с моделью title из data. -->
    <!-- Директива @input="inputTitle" связывает значение инпута с функцией обновления, таким образом реализовано двустороннее связывание -->
    <my-input type="text" placeholder="Описание поста" v-model="post.body" />
    <my-button type="submit" @click="createPost">Отправить</my-button>
  </form>
</template>

<script lang="ts">
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    };
  },

  methods: {
    createPost() {
      //@ts-ignore
      this.post.id = Date.now();

      //Обмен данными между дочерним и родительским компонентом
      this.$emit('create', this.post);

      this.post = {
        title: '',
        body: '',
      };
    },
  },
};
</script>

<style scoped>
.form {
  padding-left: 15px;
  padding-right: 15px;
}
</style>
