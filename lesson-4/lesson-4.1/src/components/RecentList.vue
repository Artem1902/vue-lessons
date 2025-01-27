<script>
import RecentItem from "@/components/RecentItem.vue";

export default {
  name: "RecentList",
  components: {RecentItem},
  props: {
    products: {
      type: Array,
      required: true,
    }
  }
}
</script>

<template>
  <h2>Recently viewed products</h2>
  <div class="container">
    <recent-item v-for="prod in products" :key='prod.id'
                 :prod='prod'></recent-item>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: start;
}
</style>