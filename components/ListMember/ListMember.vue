<template>
  <div :class="$style.member_main">
    <div :class="$style.member_box">
      <div :class="$style.type_member">
        <div :class="$style.type">
          <div :class="$style.member">Members</div>
          <div :class="$style.admins">Admins</div>
        </div>
        <div :class="$style.total">Total Members: 10<br />Current Used: 10</div>
      </div>
      <div :class="$style.filter_box">
        <div :class="$style.title">Members</div>
        <div :class="$style.add_member">
          <ul>
            <li>Add new</li>
            <li>Import members</li>
            <li>Export members (Exlcle)</li>
          </ul>
        </div>
        <div :class="$style.filter">Filter</div>
      </div>
      <GetMembers />
    </div>
  </div>
</template>

<script>
import GetMembers from '@/components/ListMember/GetMembers/GetMembers.vue'
export default {
  name: 'ListMember',
  components: {
    GetMembers,
  },
}
</script>

<style lang="scss" module>
.member_main {
  width: 100%;
}

.type_member {
  display: flex;
  justify-content: space-between;
  color: #767676;
}

.type {
  width: 20%;
  background: #fff;
  border-radius: 5px;
  display: flex;
  justify-content: space-around;
  box-shadow: 0px 0px 3px #0303037a;
  font-weight: 600;
}

.member,
.admins {
  &:hover {
    border-bottom: 3px solid #6f5cc2;
    color: #000;
  }
  transition: all 0.3s ease;
  border-bottom: 3px solid #ffffff;
  padding: 7% 5%;
  cursor: pointer;
}

.total {
  width: 20%;
  text-align: right;
}

.filter_box {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 2%;
}

.title {
  width: 12%;
  margin-left: 2%;
  color: #000;
  font-size: 25px;
  font-weight: 500;
}

.add_member {
  width: 78%;
  ul {
    display: flex;

    li {
      background: #fff;
      padding: 1% 2%;
      margin-right: 4%;
      border-radius: 5px;
      border: 1px solid #b4b6ba;
      font-weight: 600;
      color: #535d6b;
      cursor: pointer;
      transition: all 0.3s ease;
      &:hover {
        background: #6f5cc2;
        color: #fff;
      }
    }
  }
}

.filter {
  background: #6f5cc2;
  color: #fff;
  padding: 0.7% 3%;
  border-radius: 5px;
  border: 1px solid #b4b6ba;
  cursor: pointer;
  transition: all 0.3s ease;
  &:hover {
    opacity: 0.8;
  }
}

@media (max-width: 1290px) {
  .type {
    width: 25%;
  }

  .total {
    width: 50%;
  }

  .title {
    width: 17%;
  }

  .add_membe {
    width: 71%;
  }
}

@media (max-width: 1000px) {
  .type {
    width: 30%;
  }

  .title {
    font-size: 20px;
  }

  .add_member ul li,
  .filter {
    font-size: 13px;
  }
}

@media (max-width: 870px) {
  .filter {
    display: none;
  }

  .filter_box {
    flex-direction: column;
  }

  .title,
  .add_member {
    width: 100%;
  }

  .type {
    font-size: 14px;
    width: 36%;
  }
}

@media (max-width: 500px) {
  .type {
    width: 50%;
    font-size: 12px;
  }

  .add_member ul li {
    font-size: 11px;
  }

  .total {
    font-size: 14px;
  }
}
</style>
