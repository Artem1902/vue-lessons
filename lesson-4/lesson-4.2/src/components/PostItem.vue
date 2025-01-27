<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      likes: 0
    }
  },
  methods: {
    onLike() {
      this.likes += 1;
    },
    onDislike() {
      if (this.likes >= 1) {
        this.likes -= 1;
      }
    },
    onDelete() {
      this.$emit('onDelete', this.post.id);
    }
  }
}
</script>

<template>
  <ul>
    <li class="post">
      <span>
        {{ post.title }}
      </span>
      <button @click='onLike'>Like</button>
      <button @click='onDislike'>Dislike</button>
      <span>Likes: {{ likes }}</span>
      <button @click='onDelete'>Delete</button>
    </li>
  </ul>
</template>

<style scoped>
.post {
  display: flex;
  align-items: center;
  gap: 10px
}
</style>