<template>
  <div class="post" v-for="post in posts">
    <div>Название: {{ post.title }}</div>
    <div>Описание: {{ post.body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style lang="scss" scoped>
.post {
  border: 2px solid seagreen;
  padding: 20px;
  margin-top: 20px;
}

</style>