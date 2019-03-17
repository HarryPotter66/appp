<template>
 <div>
    <x-header :left-options="{showBack: true}" @click.native="login" :right-options="{showMore: true}">音乐之家</x-header>
    <swiper loop auto :list="demo06_list" :index="demo06_index"></swiper>
    <grid :show-lr-borders="false">
      <grid-item :label="('Grid')" v-for="i in 4" :key="i">
        <img slot="icon" src="../assets/xx.png">
      </grid-item>
    </grid>
   <panel :header="'推荐'" :footer="footer" :list="list" :type="type"></panel>
    <tabbar>
      <tabbar-item>
        <img slot="icon" src="../assets/fav.png">
        <span slot="label">爱好</span>
      </tabbar-item>
      <tabbar-item show-dot>
        <img slot="icon" src="../assets/home.png">
        <span slot="label">主页</span>
      </tabbar-item>
      <tabbar-item selected link="/component/demo">
        <img slot="icon" src="../assets/user.png">
        <span slot="label">使用者</span>
      </tabbar-item>
      <tabbar-item badge="2">
        <img slot="icon" src="../assets/wechat.png">
        <span slot="label">微信</span>
      </tabbar-item>
    </tabbar>
  </div>
</template>

<script>
import { Tabbar, TabbarItem, Group, Cell, XHeader, Grid, GridItem, Swiper, Panel } from 'vux'

const baseList = [{
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vvsr72j20p00gogo2.jpg',
  title: '送你一朵fua'
}, {
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw1k2wj20p00goq7n.jpg',
  title: '送你一辆车'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/5.jpg', // 404
  title: '送你一次旅行',
  fallbackImg: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw50iwj20ff0aaaci.jpg'
}]
const urlList = baseList.map((item, index) => ({
  url: 'http://www.baidu.com',
  img: item.img,
  fallbackImg: item.fallbackImg,
  title: `(可点击)${item.title}`
}))

export default {
  components: {
    Panel,
    XHeader,
    Tabbar,
    TabbarItem,
    Group,
    Cell,
    Grid,
    GridItem,
    Swiper
  },
  methods: {
    login () {
      this.$router.push('/login')
    }
  },
  data () {
    return {
      demo06_list: urlList,
      demo06_index: 0,
      msg: 'Hello World!',
      type: '1',
      list: [{
        src: 'http://www.zhantengwang.com/uploads/allimg/181016/1-1Q016144920196.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题一',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: '/component/cell'
      }, {
        src: 'http://www.zhantengwang.com/uploads/allimg/181016/1-1Q016144920196.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题一',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: '/component/cell'
      }, {
        src: 'http://www.zhantengwang.com/uploads/allimg/181016/1-1Q016144920196.jpg',
        fallbackSrc: 'http://placeholder.qiniudn.com/60x60/3cc51f/ffffff',
        title: '标题一',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: '/component/cell'
      }, {
        src: 'http://www.zhantengwang.com/uploads/allimg/181016/1-1Q016144920196.jpg',
        title: '标题二',
        desc: '由各种物质组成的巨型球状天体，叫做星球。星球有一定的形状，有自己的运行轨道。',
        url: {
          path: '/component/radio',
          replace: false
        },
        meta: {
          source: '来源信息',
          date: '时间',
          other: '其他信息'
        }
      }],
      footer: {
        title: '更多',
        url: 'http://vux.li'
      }
    }
  }
}
</script>
<style>
.container /deep/ .weui-tabbar {
  position: fixed;
}
</style>
