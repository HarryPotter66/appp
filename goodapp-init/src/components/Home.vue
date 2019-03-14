<template>
 <div>
    <x-header :left-options="{ showBack: false}">音乐之家</x-header>
    <swiper loop auto :list="demo06_list" :index="demo06_index"></swiper>
    
     
     <grid :show-lr-borders="false">
      <grid-item :label="('Grid')" v-for="i in 4" :key="i">
        <img slot="icon" src="../assets/xx.png">
      </grid-item>
    </grid>
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
import { Tabbar, TabbarItem, Group, Cell, Swiper, XHeader, Grid, GridItem } from 'vux'

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
    Swiper,
    Tabbar,
    TabbarItem,
    Group,
    Cell,
    XHeader,
    Grid,
    GridItem
  },
  data () {
    return {
      demo06_list: urlList,
      demo06_index: 0
    }
  }
}
</script>