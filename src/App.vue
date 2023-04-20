<template>
 <div>

<menu-items></menu-items>
 </div>

</template>,

<script>

import menuItems from "@/components/MenuItems.vue"

export default {
  name: 'App',
  components: {
menuItems
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
