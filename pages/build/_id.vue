<template>
  <div :class="$style.build_main">
    <div :class="$style.box">
      <div :class="$style.title">Comming soon . . .</div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" module>
.build_main {
  width: 80%;
  float: right;
  padding: 2% 2% 0 1%;
  color: #626c7b;
}

.box {
  background: #fff;
  width: 80%;
  margin: 4% auto;
  padding: 5%;
  border-radius: 5px;
  box-shadow: 0px 0px 3px rgba(3, 3, 3, 0.47843);
}

.title {
  font-size: 30px;
  text-align: center;
}

@media (max-width: 500px) {
  .title {
    font-size: 18px;
  }
}
</style>
