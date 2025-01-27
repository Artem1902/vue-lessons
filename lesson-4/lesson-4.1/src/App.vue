<template>
  <h3>Задача 1. Спробуйте відтворити використовуючи
    відповідні компоененти
  </h3>
  <compare-list
      :products="compareProductsImg"></compare-list>
  <recent-list :products='recentProducts'></recent-list>
</template>

<script>
import CompareList from "@/components/CompareList.vue";
import RecentList from "@/components/RecentList.vue";

export default {
  name: 'App',
  components: {RecentList, CompareList},
  data() {
    return {
      compareProductsImg: [
        {
          id: 4,
          type: 'Mobile phones',
          title: 'iPhone 16 Pro & iPhone 16 Pro Max',
          img: require('@/assets/iphone-card-40-iphone16prohero-202409.jpeg'),
        },
        {
          id: 5,
          type: 'Mobile phones',
          title: 'iPhone 16 & iPhone 16 Plus',
          img: require('@/assets/iphone-card-40-iphone16hero-202409.jpeg'),
        },
        {
          id: 6,
          type: 'Mobile phones',
          title: 'iPhone 15 & iPhone 15 Plus',
          img: require('@/assets/iphone-card-40-iphone15hero-202309.jpeg'),
        }
      ],
      recentProducts: [
        {
          id: 1,
          title: 'iPad Pro',
          img: require('@/assets/ipad_pro_512ae2f91.png'),
          description: 'The ultimate iPad experience with the most advanced technology.',
          price: 'From $1399 or $119.75/mo. for12 mos. at 4.99% APR *',
          isAvailable: true,
          discount: null,
          reviews: [5, 4, 5, 3, 5],
        },
        {
          id: 2,
          title: 'iPad Air',
          img: require('@/assets/ipad_air_e65ef7467.png'),
          description: 'Serious performance in a thin and light design.',
          price: 'From $799 or $68.39/mo. for12 mos. at 4.99% APR *',
          discount: 'From $699 or $58.39/mo. for12 mos. at 4.99% APR *',
          isAvailable: true,
          reviews: [],
        },
        {
          id: 3,
          title: 'iPad',
          img: require('@/assets/ipad_10th_gen_0486de254.png'),
          description: 'The colourful, all-screen iPad for the things you do every day.',
          price: 'From $499 or $42.71/mo. for12 mos. at 4.99% APR *',
          discount: null,
          isAvailable: false,
          reviews: [3, 4, 3, 3, 2, 3, 5],
        }
      ]
    }
  }
}
</script>

<style>
</style>
