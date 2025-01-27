<script>
import PostItem from "@/components/PostItem.vue";

export default {
  name: "PostList",
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true,
    }
  },
  methods: {
    onDelete(id){
      this.$emit("onDelete", id);
    }
  }
}
</script>

<template>
  <div v-if="posts.length > 0">
    <post-item v-for="post in posts" :key='post.id'
               :post='post' @onDelete = 'onDelete'></post-item>
  </div>
  <div v-else>
    The list of posts is empty...
  </div>
</template>

<style scoped>

</style>