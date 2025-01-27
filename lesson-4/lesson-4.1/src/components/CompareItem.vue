<script>
export default {
  name: "CompareItem",
  props: {
    prod: {
      type: Object,
      required: true
    }
  }
}
</script>

<template>
  <img :src="prod.img" :alt="prod.title">
</template>

<style scoped>
img {
  width: 100px;
}
</style>