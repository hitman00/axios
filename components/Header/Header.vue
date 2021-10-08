<template>
  <div :class="$style.header_main">
    <div :class="$style.max_size">
      <div :class="$style.logo">
        <div :class="$style.logo_image">
          <img src="@/assets/imgs/logo.png" />
        </div>
        <div :class="$style.logo_title">MR Company</div>
      </div>
      <div :class="$style.meno">
        <ul>
          <li>Home</li>
          <li>Customers</li>
          <li>Features</li>
          <li>Contact Us</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" module>
.header_main {
  width: 100%;
  background: #000;
  color: #fff;
}

.max_size {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 15px;
  display: flex;
}

.logo {
  width: 30%;
  display: flex;
  align-items: center;
}

.logo_image {
  position: relative;
  width: 21%;
  margin-right: 5%;
  &:before {
    content: '';
    display: block;
    padding-bottom: 82%;
  }
  img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
  }
}

.meno {
  width: 70%;
  padding: 2% 0;
  ul {
    display: flex;
    justify-content: end;
    li {
      padding: 2% 3%;
      transition: all 0.3s ease;
      border-radius: 5px;
      font-weight: 500;
      cursor: pointer;
      &:hover {
        background: #ffc100;
        color: black;
      }
    }
  }
}
</style>
