<template>
  <div>
    <div class="nav">
      <img class="nav-logo" src="http://www.linquick.com.cn/datasy/attachment/202101/18/61ec6f67579d5b1d117bb8648d7fecdb.png">
      <ul class="nav-bar">
        <li v-for="(item,index) in menuList" :key="index">
          <router-link :to="item.path">{{item.menu}}</router-link>
        </li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>
<script>
export default {
  data(){
    return {
      menuList:[
        {
          menu:'首页',
          path:'/home'
        },
        {
          menu:'关于公司',
          path:'/about'
        },
        {
          menu:'产品中心',
          path:'/product'
        },
        {
          menu:'新闻中心',
          path:'/news'
        },
        {
          menu:'联系我们',
          path:'/contact'
        },
      ]
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
    height: 50px;
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
            color: red;
          }
        }
    }
  }
}
</style>