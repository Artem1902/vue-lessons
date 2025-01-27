<script>
import CompareItem from "@/components/CompareItem.vue";

export default {
  name: "CompareList",
  components: {CompareItem},
  props: {
    products: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <h2>Compare list</h2>
  <h3>{{ products[0].type }}</h3>
  <h4>Number of products: {{ products.length}}</h4>
  <div class="items">
    <compare-item v-for=" prod in products" :key='prod.id'
                  :prod='prod'></compare-item>
  </div>
</template>

<style scoped>
.items {
  display: flex;
  align-items: center;
  justify-content: start;
}
</style>