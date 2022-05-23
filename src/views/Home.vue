<template>
  <div class="home">
    <!-- 轮播图 -->
    <el-carousel :interval="3000" trigger="click"  height="550px">
      <el-carousel-item v-for="item in list" :key="item">
        <img class="banner" :src="item"/>
      </el-carousel-item>
    </el-carousel>
    <!-- 产品中心 -->
    <div class="module">
      <div class="module-head">
        <div class="module-head-title">
          <h1>产品中心 <br/><span>PRODUCT CENTER</span></h1>
        </div>
      </div>
      <div class="module-content products">
        <div
          class="list-item"
          v-for="(item,index) in productList"
          :key="index">
          <div class="list-item-img">
            <img :src="item.img"/>
          </div>
          <div class="list-item-desc">{{item.name}}</div>
        </div>
      </div>
    </div>
    <!-- 新闻中心 -->
    <div class="module">
      <div class="module-head">
        <div class="module-head-title">
          <h1>新闻中心 <br/><span>NEWS CENTER</span></h1>
        </div>
      </div>
      <div class="module-content news">
        <el-carousel :interval="4000" type="card" height="360px">
          <el-carousel-item v-for="(item,index) in newsList" :key="index">
            <div class="list-item">
              <img :src="item.img"/>
              <div class="desc"></div>
            </div>
          </el-carousel-item>
        </el-carousel>
      </div>
    </div>
    <!-- 关于公司 -->
    <div class="module about">
      <div class="module-head">
        <div class="module-head-title">
          <h1>关于公司 <br/><span>ABOUT US</span></h1>
        </div>
      </div>
      <div class="module-content">
        <img src="http://www.yenyon.com/uploads/image/20200511/20200511120528_8231.jpeg"/>
        <div class="desc">
          关注未来，更思考未来。<br/>
          我们只是科技公司吗？<br/>
          准确来讲，<br/>
          我们连接万物，<br/>
          为你未来的一切赋能。<br/>
        </div>
      </div>
    </div>
    <!-- 联系我们 -->
    <div class="module contact">
      <div>
        <h1>联系我们</h1>
        <h3>CONTACT US</h3>
        <!-- <img src="http://www.linquick.com.cn/tpl/LjimitateIm/image/foot_logo.png"> -->
      </div>
      <div>
        <h4>友情链接</h4>
        <div>客户链接1</div>
        <div>客户链接2</div>
        <div>客户链接3</div>
        <div>客户链接4</div>
        <div>客户链接5</div>
      </div>
      <div>
        <h4>网页导航</h4>
        <div>网站首页</div>
        <div>产品中心</div>
        <div>新闻中心</div>
        <div>关于我们</div>
        <div>联系我们</div>
      </div>
      <div>
        <h4>联系方式</h4>
        <div>电话：0573-85606156</div>
        <div>手机：18121073165</div>
        <div>地址：浙江省平湖市新埭镇虹桥北路333号</div>
        <div>邮编：314211</div>
        <div>邮箱：sales@linquick.com.cn</div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import {CAROUSEL_LIST, PRODUCT_LIST, NEWS_LIST} from '../data'
export default {
  name: 'Home',
  components: {
  },
  data(){
    return {
      list: CAROUSEL_LIST,
      productList: PRODUCT_LIST,
      newsList: NEWS_LIST
    }
  }
}
</script>
<style lang="less" scoped>
.home {
  img.banner {
    width: 100%;
  }
  .module {
    width: 100%;
    margin-top: 30px;
    &-head {
      display: flex;
      justify-content: center;
      margin-bottom: 45px;
      &-title {
        position: relative;
        width: 300px;
        text-align: center;
        border-bottom: solid 1px #333;
        &::after {
          display: inline-block;
          content: '';
          width: 50px;
          height: 10px;
          border-radius: 3px;
          background-color: #409eff;
          position: absolute;
          bottom: -5px;
          left: 50%;
          margin-left: -25px;
        }
        h1 {
          letter-spacing: 2px;
          span {
            font-weight: normal;
            font-size: 26px;
          }
        }
      }
    }
    &-content {
      &.products {
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
        .list-item {
          cursor: pointer;
          font-size: 14px;
          font-weight: 400;
          text-align: center;
          margin-top: 30px;
          &-img {
            width: 300px;
            margin-bottom: 8px;
            overflow: hidden;
            img {
              width: 100%;
              height: 100%;
              &:hover {
                transform: scale(1.5);
              }
            }
          }
        }
      }
      &.news {
        .list-item {
          position: relative;
          img {
            width: 100%;
          }
        }
      }
    }
  }
  .about {
    .module-content {
      position: relative;
      padding: 0 100px;
      img {
        width: 680px;
        height: 400px;
      }
      .desc {
        position: absolute;
        left: 680px;
        top: 50px;
        width: 600px;
        height: 300px;
        padding: 30px 50px;
        box-sizing: border-box;
        background-color: #fffcfc;
      }
    }
  }
  .contact {
    display: flex;
    justify-content: space-around;
    padding: 30px 100px;
    box-sizing: border-box;
    background-color: #333;
    color: #fff;
    margin-top: 100px;
    h3 {
      font-weight: normal;
      font-size: 26px;
    }
  }
}
</style>
