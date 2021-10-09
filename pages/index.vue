<template>
  <div :class="$style.main">
    <FoundUserBox />
  </div>
</template>

<script>
import FoundUserBox from '@/components/FoundUserBox/FoundUserBox.vue'
export default {
  components: {
    FoundUserBox,
  },
  data: () => ({}),
}
</script>

<style lang="scss" module>
.main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 15px;
}
</style>
