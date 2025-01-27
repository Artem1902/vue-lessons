<script>
export default {
  name: "StarRating",
  props: {
    averageRating: {
      type: Number,
      required: true,
    }
  },
}
</script>

<template>
  <div class="star-rating">
  <span v-for="(star, index) in 5" :key="index" class="star"
        :class="{
    filled: index < Math.round(this.averageRating)
  }">*
  </span>
  </div>
</template>

<style scoped>
.star-rating {
  display: flex;
  gap: 4px;
}

.star {
  width: 24px;
  height: 24px;
  font-size: 24px;
  color: #ccc;
}

.star.filled {
  color: #f5c518;
}
</style>