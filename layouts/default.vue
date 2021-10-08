<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>
<script>
import Header from '@/components/Header/Header.vue'
export default {
  components: {
    Header,
  },
}
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(90deg, #3bebce 0%, #40d7e6 49%, #458bbe 100%);
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}
</style>
