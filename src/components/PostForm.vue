<template>
  <div class="App">
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
          class="btn">Создать</button>
    </form>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.app {
  padding: 20px;
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