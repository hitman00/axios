<template>
  <div :class="$style.main">
    <div :class="$style.details">
      <div :class="$style.box" @click="test"></div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    page: Number,
  }),
  methods: {
    test() {
      this.page = this.$router.history._startLocation
      console.log(this.page)
      console.log(this.$router)
    },
  },
}
</script>

<style lang="scss" module>
.main {
}

.box {
  width: 40px;
  height: 40px;
  background: red;
}
</style>
