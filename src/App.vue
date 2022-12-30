<template>
  <div class="wrap">
    <!-- Модификатор @submit.prevent эквивалентен event.preventDefault() -->
    <form class="form" @submit.prevent>
      <h4>Создание поста</h4>
      <input class="input" type="text" placeholder="Название поста" v-bind:value="title" @input="inputTitle" />
      <!-- Директива v-bind:value="title" связывает инпут с моделью title из data. -->
      <!-- Директива @input="inputTitle" связывает значение инпута с функцией обновления, таким образом реализовано двустороннее связывание -->
      <input class="input" type="text" placeholder="Описание поста" v-bind:value="body" @input="inputBody" />
      <button type="submit" class="form_button" @click="createPost">Отправить</button>
    </form>
    <div class="post" v-for="post in posts" v-bind:key="post.id">
      <!-- Директива v-for="post in posts" позволяет нам отрендерить элементы на основе массива
		Директива v-bind:key="post.id" создает для каждого элемента свой ключ -->
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script lang="ts">
export default {
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
      title: '',
      body: '',
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },

    addDisLike() {
      this.dislikes += 1;
    },

    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      };

      //Добавление в общий массив постов
      this.posts.push(newPost);

      this.title = '';
      this.body = '';
    },

    inputTitle(event: any) {
      this.title = event.target.value;
    },

    inputBody(event: any) {
      this.body = event.target.value;
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

.wrap {
  margin: 15px 15px;
  border: 2px solid #c1c1c1;
  padding-top: 15px;
  padding-bottom: 15px;
}

.form {
  padding-left: 15px;
  padding-right: 15px;
}

.input {
  width: 100%;
  border: 2px solid rgb(6, 223, 219);
  padding: 10px 15px;
  margin-top: 10px;
}

.input:first-child {
  margin-top: 0;
}

.form_button {
  margin-top: 15px;
  margin-bottom: 30px;
  padding: 10px;
  background: none;
  border: 2px solid rgb(6, 223, 219);

  width: 100px;
}
</style>
