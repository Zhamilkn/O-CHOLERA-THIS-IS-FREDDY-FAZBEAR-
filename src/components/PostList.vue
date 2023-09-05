<template>
   <div>
    <h3>Cписок</h3>
    <post-item
      v-for="post in posts" 
      :post="post"
      :key="post"
      @remove="$emit('remove', post)"
      />
  </div>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: {PostItem},
  props: {
    posts: {
        type:Array,
        required: true 
    }
  }
}

</script>

<style scoped>

</style>