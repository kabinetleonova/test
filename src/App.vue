<template>
  <div class="app">
    <div>
      <form @submit.prevent class="post-form">
        <h4>Создание поста</h4>

        <input
            v-bind:value="title"
            @input="title = $event.target.value"
            class="input"
            type="text"
            placeholder="Название">

        <input
            v-bind:value="body"
            @input="body = $event.target.value"
            class="input"
            type="text"
            placeholder="Описание">

        <button
            @click="createPost"
            class="btn">Создать</button>
      </form>
    </div>
    <div class="post" v-for="post in posts">
      <div>Название: {{ post.title }}</div>
      <div>Описание: {{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'Пост 1', body: 'Описание 1'},
        {id: 2, title: 'Пост 2', body: 'Описание 2'},
        {id: 3, title: 'Пост 3', body: 'Описание 3'},
        {id: 4, title: 'Пост 4', body: 'Описание 4'},
      ],
      title: '',
      body: '',
    }
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body,
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';
    },

  }
}
</script>

<style>

* {
  padding: 0;
  margin: 0;
}

.app {
  padding: 20px;
}

.post {
  border: 2px solid seagreen;
  padding: 20px;
  margin-top: 20px;
}

.post-form {
  display: flex;
  flex-direction: column;
}

.input {
  border: 2px solid seagreen;
  padding: 10px;
  margin-top: 10px;
}

.btn {
  align-self: flex-end;
  margin-top: 15px;
  background: none;
  border: 2px solid seagreen;
  padding: 10px;
}
</style>