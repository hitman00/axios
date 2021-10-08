<template>
  <div :class="$style.user_main">
    <div :class="$style.box">
      <div :class="$style.title">List Of Users</div>
      <div v-for="i in rr" :key="i.id" :class="$style.name_list">
        <ul>
          <li>
            <a :href="i.id">{{ i.name }}</a>
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
    rr: [],
  }),
  async fetch() {
    const data = await this.$axios.get(
      'https://jsonplaceholder.typicode.com/users'
    )
    // this.len = data.data.length
    for (let i = 0; i < data.data.length; i++) {
      this.rr[i] = data.data[i]
      console.log(this.rr)
    }
  },
  methods: {
    // async getData() {
    //   const data = await this.$axios.get(
    //     'https://jsonplaceholder.typicode.com/users'
    //   )
    //   for (let i = 0; i < data.data.length; i++) {
    //     this.ip[i] = data.data[i].name
    //     console.log(this.ip)
    //   }
    // },
    // async fetchSomething() {
    //   const ip = await this.$axios.get('http://icanhazip.com')
    //   this.ip = ip
    //   console.log(this.ip)
    // },
  },
}
</script>

<style lang="scss" module>
.user_main {
  margin-top: 5%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box {
  width: 40%;
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
    a {
      color: #1eeef9;
      padding: 3%;
      transition: all 0.3s ease;
      cursor: pointer;
      display: inline-block;
      border-radius: 5px;
      &:hover {
        background: rgb(36, 215, 228);
        color: #fff;
      }
    }
  }
}
</style>
