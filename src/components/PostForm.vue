<template>
  <form @submit.prevent="createPost">
    <h4>Пост</h4>
    <my-input v-model="post.title" type="text" placeholder="Название???" />
    <my-input v-model="post.body" class="input" type="text" placeholder="Описание" />
    <my-button class="btn" style="align-self: flex-end; margin-top: 15px" @click="createPost">Создай</my-button>
  </form>
</template>

<script>
export default {
  name: 'PostForm',
  data() {
    return {
      post: {
        title: '',
        body: '',
      },
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    },
  },
}
</script>

<style scoped></style>
