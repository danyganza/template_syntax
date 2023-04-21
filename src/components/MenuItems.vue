<template>
  <div>
    <div>
      <input type="number" ref="user_number" />
      <button @click="filter_prices">Price Filter</button>
    </div>
    <section class="menu_container">
      <div v-for="(item, i) in items" :key="i">
        <span v-if="item.price <= max_price">
          <h3>{{ item.title }}</h3>
          <p>{{ item.description }}</p>
          <img :src="item.image_url" :alt="item.description" />
          <h6>{{ item.price }}</h6>
        </span>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  methods: {
    filter_prices: function () {
      let input_tag = this.$refs[`user_number`];
      let input_value = input_tag[`value`];
      this.max_price = input_value;
    },
  },
  data() {
    return {
      max_price: 1000,
      items: [
        {
          title: `steak and brocoli`,
          price: 13.5,
          image_url: `https://images.unsplash.com/photo-1558199141-391d935676f0?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=765&q=80`,
          description: `good food.`,
        },
        {
          title: `good meat`,
          price: 15.5,
          image_url: `https://images.unsplash.com/photo-1504973960431-1c467e159aa4?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80`,
          description: `nice to meat you.`,
        },
        {
          title: `Salmon`,
          price: 11.5,
          image_url: `https://images.unsplash.com/photo-1467003909585-2f8a72700288?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80`,
          description: `Tasty Salmon.`,
        },
        {
          title: `Salad`,
          price: 9.0,
          image_url: `https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80`,
          description: `It is a great salad.`,
        },
      ],
    };
  },
};
</script>

<style scoped>
img {
  max-width: 100%;
  height: 400px;
}
.menu_container {
  display: grid;
  place-items: center;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}
</style>