<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from './components/PostForm.vue'
import PostList from './components/PostList.vue'

export default {
  name: 'App',
  mounted() {
    console.log('App mounted!')
  },
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'вопросы?', body: 'Оветы?' },
        { id: 2, title: 'вопросы? 2', body: 'Оветы? 2' },
        { id: 3, title: 'вопросы? 3', body: 'Оветы? 3' },
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post)
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id !== post.id)
    },
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0 box-sizing border-box;
}

.app {
  padding: 20px;
}

.form {
  display: flex;
  flex-direction: column;
}
</style>
