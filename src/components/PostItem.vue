<template>
  <div class="post">
    <div><strong>Амогус:</strong> {{ post.title }}</div>
    <div><strong>Абоба:</strong> {{ post.body }}</div>
    <div class="post__btns">
      <my-button @click="$emit('remove', post)">удалить</my-button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PostItem',
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 3px solid teal;
  margin-top: 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
