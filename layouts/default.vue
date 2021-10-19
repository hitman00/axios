<template>
  <div>
    <Header />
    <LeftMenu />
    <Nuxt />
  </div>
</template>
<script>
import Header from '@/components/Header/Header.vue'
import LeftMenu from '~/components/LeftMenu/LeftMenu.vue'
export default {
  components: {
    Header,
    LeftMenu,
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
  font-family: 'Poppins';
  background: #f7f7f7;
  overflow-y: scroll;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 400;
  src: url('@/assets/fonts/Poppins-Regular.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 100;
  src: url('@/assets/fonts/Poppins-Thin.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 200;
  src: url('@/assets/fonts/Poppins-ExtraLight.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 300;
  src: url('@/assets/fonts/Poppins-Light.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 500;
  src: url('@/assets/fonts/Poppins-Medium.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 600;
  src: url('@/assets/fonts/Poppins-SemiBold.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 700;
  src: url('@/assets/fonts/Poppins-Bold.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 800;
  src: url('@/assets/fonts/Poppins-ExtraBold.woff') format('woff');
}

@font-face {
  font-family: 'Poppins';
  font-style: normal;
  font-weight: 900;
  src: url('@/assets/fonts/Poppins-Black.woff') format('woff');
}
</style>
