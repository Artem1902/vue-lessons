<script>
export default {
  name: "CardItem",
  props: {
    rasData: {
      type: Object,
      required: true
    }
  },
  computed: {
    isAvailable() {
      return this.rasData.isAvailable ? 'В наявності' : '';
    }
  }
}
</script>

<template>
  <div class="card">
    <img :src="rasData.imgSrc" :alt="rasData.description"
         class="card_img">
    <div class="content_top">
      <img :src="rasData.logo" :alt="rasData.companyTitle">
      <span>{{ rasData.companyTitle }}</span>
      <span class="available">{{ isAvailable }}</span>
    </div>
    <div class="content_bottom">
      <p>{{ rasData.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 100%;
  row-gap: 10px;
}

.card_img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  aspect-ratio: 1/1;
  border-radius: 12px;
}

.content_top {
  display: flex;
  align-items: center;
  gap: 10px;
}
.content_top img {
  width: 20px;
  height: 20px;
}
.content_bottom p {
  margin: 0;
  padding: 0;
}
.available{
  color: green;
}
</style>