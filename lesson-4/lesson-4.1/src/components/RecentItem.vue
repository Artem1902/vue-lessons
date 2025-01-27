<script>
import StarRating from "@/components/StarRating.vue";

export default {
  name: "RecentItem",
  components: {StarRating},
  props: {
    prod: {
      type: Object,
      required: true
    },
  },
  computed: {
    hasRating() {
      return this.prod.reviews.length > 0;
    },
    averageRating() {
      return Number((this.prod.reviews.reduce((acc, current) => acc + current, 0) / this.prod.reviews.length))
    },
    availableText() {
      return this.prod.isAvailable ? 'Available' : 'Not Available'
    },
    hasDiscount() {
      return this.prod.discount;
    }
  }
}
</script>

<template>
  <div class="item">
    <div class="item-img">
      <img :src="prod.img" :alt="prod.title">
    </div>
    <div class="body">
      <h3 class="title">{{ prod.title }}</h3>
      <p>{{ prod.description }}</p>
      <div>
        <div v-if="hasRating" class="rating">
          <star-rating
              :averageRating='averageRating'></star-rating>
          <div class='icon-container'>
            <img class="icon"
                 src="../assets/free-icon-good-feedback-11899486.png"
                 alt="icon">
            <span>{{ prod.reviews.length }}</span>
          </div>
        </div>
        <span v-else>Leave a review</span>
      </div>
      <div>
        <span>{{ availableText }}</span>
      </div>
      <div>
        <span
            :class="{ 'price-with-discount': hasDiscount}">{{
            prod.price
          }}</span>
      </div>
      <div class=" bottom">
        <p v-if="hasDiscount" class="discount">
          {{ prod.discount }}</p>
        <img
            src="../assets/shopping-cart-icon_609277-489.avif"
            alt="cart" class="cart" l>
      </div>
    </div>
  </div>
</template>

<style scoped>
.item {
  max-width: 220px;
  border-right: 1px solid black;
  padding: 15px;
}

.item-img img {
  max-width: 100%;
}

.body {
  display: flex;
  flex-direction: column;
  gap: 5px;
}

.title {
  font-size: 18px;
}

.rating {
  display: flex;
  align-items: center;
}

.icon-container {
  display: flex;
  align-items: center;
  gap: 5px;
}

.icon {
  width: 24px;
  height: 24px;
}

.cart {
  width: 30px;
  height: 30px;
}

.bottom {
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.discount {
  color: red;
}

.price-with-discount {
  text-decoration: line-through;
  opacity: 0.5;
}
</style>