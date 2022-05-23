<template>
  <div>
    <div class="nav">
      <img class="nav-logo" src="http://www.yenyon.com/uploads/image/20200602/20200602095326_7488.jpeg">
      <ul class="nav-bar">
        <li v-for="(item,index) in menuList" :key="index" :class="{active: item.isActive}">
          <router-link :to="item.path">{{item.menu}}</router-link>
        </li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>
<script>
import { MENU_LIST } from '../data'
export default {
  data(){
    return {
      menuList: MENU_LIST
    }
  }
}
</script>
<style lang="less" scoped>
.nav {
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 8px 0;
  padding: 0 30px;
  background-color: transparent;
  &-logo {
    height: 100px;
  }
  &-bar {
    font-size: 14px;
    font-weight: bold;
    list-style: none;
    li {
      display: inline-block;
      &:not(:last-child){
        margin-right: 50px;
      }
      cursor: pointer;
        a {
          color: #333;
          text-decoration: none;
          &:hover {
            color: #409eff;
          }
        }
        &.active {
          a {
            color: #409eff;
          }
        }
    }
  }
}
</style>