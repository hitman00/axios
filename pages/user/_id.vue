<template>
  <div :class="$style.box">
    <div v-if="$fetchState.pending" :class="$style.pre">loading</div>
    <div v-else-if="$fetchState.error" :class="$style.pre">error</div>
    <pre v-else :class="$style.pre">{{ user }}</pre>
  </div>
</template>

<script>
export default {
  name: 'PageUserId',
  data: () => ({
    user: {},
  }),
  async fetch() {
    const { data } = await this.$axios.get(
      'https://jsonplaceholder.typicode.com/users/' + this.$route.params.id
    )
    this.user = data
  },
}
</script>

<style lang="scss" module>
.pre {
  max-width: 800px;
  margin: 50px auto;
  background: #fff;
}
</style>
