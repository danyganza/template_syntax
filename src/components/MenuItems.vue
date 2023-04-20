<template>
  <div>
    <button v-for="(item, i) in items" :key="i">
      <h3>{{ item.title }}</h3>
      <p>{{ item.description }}</p>
      <img :src="item.image_url" alt="item Image">
      <span>Price: {{ item.price }}</span>
      <button @click="addToCart(item)">Add to cart</button>
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          title: `Vegan salad bowl`,
          price: 153,
          description: `the health in this place is unimainable`,
          image_url: `https://images.unsplash.com/photo-1512621776951-a57141f2eefd?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80`,
        },
        {
          title: `Meal with salmon and zucchini`,
          price: 123,
          description: `good food, good mood`,
          image_url: `https://images.unsplash.com/photo-1467003909585-2f8a72700288?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80`,
        },
      ],
    };
  },
  methods: {
    addToCart(item) {
      // implement your add to cart logic here
      console.log(`Adding item ${item.title} to cart...`);
    },
  },
};
</script>

<style scoped>
</style>
