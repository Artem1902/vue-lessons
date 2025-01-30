<script>
import {raspberryList} from '@/constants/data_raspberry'
import CardItem from "@/components/CardsList/CardItem.vue";

export default {
  name: "CardsList",
  components: {CardItem},
  computed: {
    raspberriesList() {
      return raspberryList
    }
  }
}
</script>

<template>
  <div class="container">
    <card-item v-for="rasData in raspberriesList"
               :key='rasData.id' :ras-data=
                   rasData></card-item>
  </div>
</template>

<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(3, minmax(150px, 1fr));
  gap: 10px;
  background-color: black;
  color: grey;
  padding: 15px;
  max-width: 800px;
}
</style>