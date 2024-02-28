<template>
  <post-form/>
  <post-list :posts="posts"/>
</template>

<script>
import PostForm from "./components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: {
    PostList, PostForm
  },

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


</style>