<template>
  <div :class="$style.user_main">
    <div :class="$style.box">
      <div :class="$style.title">List Of Users</div>
      <div :class="$style.name_list">
        <ul>
          <li v-for="item in items" :key="item.id">
            <NuxtLink :to="'/user/' + item.id">{{ item.name }}</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FoundUserBox',
  data: () => ({
    items: [],
  }),
  async fetch() {
    const { data } = await this.$axios.get(
      'https://jsonplaceholder.typicode.com/users'
    )
    this.items = data
  },
}
</script>

<style lang="scss" module>
.user_main {
  margin-top: 5%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.box {
  width: 100%;
  background: #fff;
  box-shadow: -3px 4px 7px #557582;
  border-radius: 10px;
  padding: 0 4% 4%;
  margin-bottom: 10%;
}
.title {
  font-size: 30px;
  font-weight: 600;
  color: #1eeef9;
  text-align: center;
  padding: 4% 0;
  border-bottom: 1px solid rgb(114, 113, 113);
  margin-bottom: 10%;
}
.name_list {
  font-size: 20px;
  ul {
    display: flex;
    flex-wrap: wrap;
    li {
      width: 50%;
      a {
        color: #1eeef9;
        padding: 4%;
        transition: all 0.3s ease;
        cursor: pointer;
        display: inline-block;
        border-radius: 5px;
        margin: 4%;
        &:hover {
          background: rgb(36, 215, 228);
          color: #fff;
        }
      }
    }
  }
}
</style>
