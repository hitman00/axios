<template>
  <div :class="$style.header_main">
    <div :class="$style.header_box">
      <div :class="$style.logo">
        <div :class="$style.logo_img">
          <img src="@/assets/imgs/logo.png" />
        </div>
        <div :class="$style.logo_name">Norsk<br />Timeregistering</div>
      </div>
      <div :class="$style.search">
        <div :class="$style.search_box">
          <img src="@/assets/imgs/search.png" />
          <input type="text" placeholder="Search" />
        </div>
        <div :class="$style.notifications"></div>
      </div>
      <div :class="$style.profile">
        <div :class="$style.avatar">
          <img src="@/assets/imgs/avatar.png" />
        </div>
        <div :class="$style.name">
          Luke Asote<span>Admin for Association</span>
        </div>
        <img src="@/assets/imgs/icon.png" :class="$style.icon_img" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" module>
.header_main {
  padding-bottom: 5.5%;
}

.header_box {
  width: 100%;
  color: #fff;
  display: flex;
  padding: 1% 5%;
  justify-content: space-between;
  position: fixed;
  background: #52438f;
  top: 0;
  z-index: 2;
}

.search {
  width: 60%;
  display: flex;
  justify-content: space-between;
  padding: 0.3% 0;
}

.profile,
.logo {
  width: 20%;
  display: flex;
  align-items: center;
}

.profile {
  justify-content: space-between;
}

.logo_name {
  font-weight: 600;
  font-size: 21px;
  line-height: 1.2;
}

.logo_img {
  position: relative;
  width: 10%;
  margin-right: 4%;
  &:before {
    content: '';
    display: block;
    padding-bottom: 205%;
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

.search_box {
  width: 60%;
  background: #fff;
  display: flex;
  border-radius: 4px;
  align-items: center;
  padding: 1% 2.5%;
  img {
    width: 15px;
    height: 15px;
    display: block;
    margin-right: 1%;
  }
  input {
    background: none;
    padding: 2%;
    border: none;
    width: 100%;
    color: #767676;
    &:focus {
      outline: none;
    }
  }
}

.avatar {
  position: relative;
  width: 20%;
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

.name {
  font-weight: 600;
  span {
    display: block;
    font-weight: 300;
  }
}

.icon_img {
  width: 12px;
  display: block;
}

@media (max-width: 1290px) {
  .logo_name {
    font-size: 16px;
  }

  .search {
    width: 56%;
  }

  .profile {
    width: 24%;
  }

  .name {
    font-size: 14px;
  }
}

@media (max-width: 1000px) {
  .header_main {
    padding-bottom: 7.5%;
  }

  .name {
    display: none;
  }

  .icon_img {
    display: none;
  }

  .profile {
    justify-content: right;
  }

  .logo {
    width: 30%;
  }

  .search_box {
    width: 100%;
  }

  .avatar {
    width: 31%;
  }
}

@media (max-width: 700px) {
  .logo_name {
    font-size: 13px;
  }
}

@media (max-width: 500px) {
  .header_main {
    padding-bottom: 12.5%;
  }

  .search {
    display: none;
  }

  .logo {
    width: 50%;
  }

  .profile {
    width: 40%;
  }

  .logo_name {
    font-size: 16px;
  }
}
</style>
