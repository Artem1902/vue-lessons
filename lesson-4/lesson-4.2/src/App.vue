<template>
  <h1>Задача 2. Створити імітатор мессенджера. Є можлиість
    додавати/відображати повідомлення і ставити лайки .
  </h1>
  <post-list :posts='posts'
             @onDelete='onDelete'></post-list>
  <new-post @send='onSend'></new-post>
</template>

<script>

import PostList from "@/components/PostList.vue";
import NewPost from "@/components/NewPost.vue";

export default {
  name: 'App',
  components: {
    NewPost,
    PostList
  },
  data() {
    return {
      posts: []
    }
  },
  methods: {
    onSend(newPost) {
      this.posts.push(newPost);
    },
    onDelete(id) {
      this.posts = this.posts.filter(el => el.id !== id);
    }
  },
}
</script>

<style>

</style>
