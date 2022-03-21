<template>
  <form @submit.prevent>
    <h2>Создание поста</h2>
    <my-input
      placeholder="Название"
      v-model="post.title"
    />
    <my-input
      placeholder="Описание"
      v-model="post.body"
    />
    <my-button
      class="btn-component"
      @click="createPost"
      :btnType="btnType"
    >
      Создать
    </my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
      btnType: 'button',
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: '',
      }
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.btn-component {
  align-self: flex-end;
  margin-top: 15px;
}
</style>