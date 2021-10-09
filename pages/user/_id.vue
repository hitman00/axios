<template>
  <div :class="$style.user_main">
    <div :class="$style.box">
      <div v-if="$fetchState.pending" :class="$style.pre">loading</div>
      <div v-else-if="$fetchState.error" :class="$style.pre">error</div>
      <div v-else :class="$style.pre">
        <div :class="$style.title">{{ user.name }}</div>
        <div :class="$style.detals">
          <div>E-mail: {{ user.email }}</div>
          <div>City: {{ user.address.city }}</div>
          <div>Zip-Code: {{ user.address.zipcode }}</div>
          <div>Street: {{ user.address.street }}</div>
        </div>
      </div>
    </div>
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
}

.user_main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 15px;
  color: #55c3c9;
}

.box {
  background: #fff;
  width: 80%;
  margin: 4% auto;
  border-radius: 10px;
  padding: 5%;
}

.pre {
  a {
    color: rgb(40, 204, 233);
    padding: 4% 0;
    display: inline-block;
  }
}

.title {
  font-weight: 600;
  font-size: 30px;
  padding: 0% 0 3%;
  border-bottom: 1px solid gray;
}

.detals {
  div {
    padding: 3% 0 0;
  }
}
</style>
