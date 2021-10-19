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
.user_main {
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

@media (max-width: 500px) {
  .title {
    font-size: 20px;
  }

  .detals {
    font-size: 14px;
  }
}
</style>
