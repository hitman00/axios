<template>
  <div :class="$style.meno_main">
    <div :class="$style.meno_box">
      <ul v-for="item in list" :key="item.id">
        <NuxtLink :to="item.address">
          <li>
            <img :src="item.img" /><span>{{ item.title }}</span>
          </li>
        </NuxtLink>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LeftMeno',
  data: () => ({
    list: [
      {
        img: require('@/assets/imgs/1.png'),
        title: 'Profile',
        address: '/build/Profile',
      },
      {
        img: require('@/assets/imgs/2.png'),
        title: 'Users',
        address: '/',
      },
      {
        img: require('@/assets/imgs/3.png'),
        title: 'Control Panel',
        address: '/build/Control Panel',
      },
      {
        img: require('@/assets/imgs/4.png'),
        title: 'Projects',
        address: '/build/Projects',
      },
      {
        img: require('@/assets/imgs/5.png'),
        title: 'Tasks',
        address: '/build/Tasks',
      },
      {
        img: require('@/assets/imgs/6.png'),
        title: 'Logs',
        address: '/build/Logs',
      },
      {
        img: require('@/assets/imgs/7.png'),
        title: 'Group chats',
        address: '/build/Group chats',
      },
      {
        img: require('@/assets/imgs/8.png'),
        title: 'Reports',
        address: '/build/Reports',
      },
    ],
  }),
}
</script>

<style lang="scss" module>
.meno_main {
  width: 20%;
  background: #6f5cc2;
  height: 100vh;
  position: fixed;
  color: #fff;
  padding-top: 2%;
}

.meno_box {
  ul {
    a {
      color: #fff;
    }
    li {
      padding: 3% 8% 3%;
      transition: all 0.3s ease;
      cursor: pointer;
      border-left: 4px solid #6f5cc2;
      font-size: 18px;
      &:hover {
        background: #7d6cc8;
        border-left: 4px solid #fff;
      }
      img {
        width: 20px;
        vertical-align: sub;
        margin-right: 6%;
      }
    }
  }
}

@media (max-width: 950px) {
  .meno_box ul li {
    font-size: 14px;
  }

  .meno_main {
    width: 25%;
  }
}

@media (max-width: 600px) {
  .meno_box ul li span {
    display: none;
  }

  .meno_main {
    width: 8%;
  }

  .meno_box ul a {
    margin: 12% 0px;
    display: block;
  }
}

@media (max-width: 450px) {
  .meno_main {
    width: 12%;
  }
}
</style>
