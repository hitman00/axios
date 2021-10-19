<template>
  <div :class="$style.get_main">
    <div :class="$style.titles_box">
      <ul :class="$style.title">
        <li>Photo</li>
        <li>Member name</li>
        <li>Mobile</li>
        <li>Email</li>
        <li style="text-align: right">Details</li>
      </ul>
      <ul v-for="item in items" :key="item.id" :class="$style.members">
        <li>
          <div :class="$style.avatar_img">
            <img src="@/assets/imgs/avatar2.png" />
          </div>
        </li>
        <li>{{ item.username }}</li>
        <li>{{ item.address.zipcode }}</li>
        <li>{{ item.email }}</li>
        <li style="text-align: right">
          <NuxtLink :to="'/user/' + item.id">Read more</NuxtLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GetMembers',
  data: () => ({
    items: [],
  }),
  async fetch() {
    const { data } = await this.$axios.get(
      'https://jsonplaceholder.typicode.com/users'
    )
    this.items = data
    console.log(data)
  },
}
</script>

<style lang="scss" module>
.get_main {
  width: 100%;
  background: #fff;
  box-shadow: 0px 0px 3px #0303037a;
  margin: 5% 0;
  border-radius: 5px;
}

.titles_box {
  color: #767676;
  padding: 2% 3% 0;
  ul {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #b5b5b540;
  }
}
.title {
  padding: 0 0 2%;
  li {
    font-weight: 500;
    font-size: 17px;
    width: 14%;
  }
}

.members {
  color: #626c7b;
  font-size: 14px;
  li {
    width: 14%;
    padding: 1% 0;
    font-weight: 500;
    a {
      color: #6f5cc2;
      font-weight: 600;
      &:hover {
        opacity: 0.8;
      }
    }
  }
}

.avatar_img {
  position: relative;
  width: 45%;
  &:before {
    content: '';
    display: block;
    padding-bottom: 100%;
  }
  img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
  }
}

@media (max-width: 1260px) {
  .title {
    li {
      font-size: 15px;
    }
  }

  .members li {
    overflow: hidden;
  }
}

@media (max-width: 500px) {
  .title li {
    font-size: 11px;
  }

  .members {
    font-size: 10px;
  }
}
</style>
