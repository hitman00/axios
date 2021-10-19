<template>
  <div :class="$style.main">
    <ListMember />
    <!-- <FoundUserBox /> -->
  </div>
</template>

<script>
// import FoundUserBox from '@/components/FoundUserBox/FoundUserBox.vue'
import ListMember from '@/components/ListMember/ListMember.vue'
export default {
  components: {
    // FoundUserBox,
    ListMember,
  },
  data: () => ({}),
}
</script>

<style lang="scss" module>
.main {
  width: 80%;
  float: right;
  padding: 2% 2% 0 1%;
}

@media (max-width: 950px) {
  .main {
    width: 75%;
  }
}

@media (max-width: 600px) {
  .main {
    width: 92%;
  }
}

@media (max-width: 450px) {
  .main {
    width: 88%;
  }
}
</style>
