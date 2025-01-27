<script>
export default {
  name: "NewPost",
  data() {
    return {
      enteredText: null
    }
  },
  methods: {
    onSend() {
      const newPost = {
        id: new Date().getTime(),
        title: this.enteredText,
      }
      this.$emit('send', newPost)
      this.enteredText = null
      this.$refs.input.focus()
    }
  },
  mounted() {
    this.$refs.input.focus()
  }
}
</script>

<template>
  <div>
    <label>
      <input type="text" placeholder="Type a new message"
             ref='input'
             v-model="enteredText">
    </label>
    <button @click='onSend'>Send</button>
  </div>
</template>

<style scoped>

</style>