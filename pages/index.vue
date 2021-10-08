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
  width: 100%;
}
</style>
