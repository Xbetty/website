<template>
  <div class="home">
    <!-- 轮播图 -->
    <el-carousel :interval="3000" trigger="click"  height="500px">
      <el-carousel-item v-for="item in list" :key="item">
        <img :src="item"/>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
  },
  data(){
    return {
      list:[
        'http://www.linquick.com.cn/datasy/attachment/202103/25/145427447a3e07a3f346585742d66095.jpg',
        'http://www.linquick.com.cn/datasy/attachment/202105/06/0a15a7ed8d0d24e6ff1a44a1259d1c7a.jpg',
        'http://www.linquick.com.cn/datasy/attachment/202103/25/af7bb3399b652715b6afd294762596cd.jpg',
        'http://www.linquick.com.cn/datasy/attachment/202103/25/700e123fa224122cba75896c87e63de3.jpg'
      ]
    }
  }
}
</script>
<style lang="less" scoped>
.home {
  img {
    width: 100%;
  }
}
</style>
