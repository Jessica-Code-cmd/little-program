<template>
  <div>
    <swiper
      :indicator-dots="indicatorDots"
      :autoplay="autoplay"
      :interval="interval"
      :duration="duration"
    >
    <block v-for="img in imgUrls" :key="img">
      <swiper-item>
        <image :src="img" style="width:100%;"/>
      </swiper-item>
    </block>
    </swiper>
    <i-grid i-class="no-border">
      <i-grid-item @click="goType(grid)" v-for="grid in grids" :key="grid" i-class="no-border">
          <i-grid-icon>
              <image :src="grid.image" />
          </i-grid-icon>
          <i-grid-label>{{grid.title}}</i-grid-label>
      </i-grid-item>
    </i-grid>
    <i-panel :title="title_name">
    <view style="padding: 15px;">
      <i-card v-for="item in top" :key="item" i-class="split" :extra="item.name" :thumb="item.image">
        <view slot="content">{{item.remark}}</view>
        <view slot="footer">{{item.address}}</view>
      </i-card>
    </view>
  </i-panel>
  </div>
</template>
<script>

export default {
  data () {
    return {
      title_name:"热门",
      grids:[
        {title:"汉堡",image:"/static/images/burger.png"},
        {title:"烤肉",image:"/static/images/BBQ.png"},
        {title:"奶茶",image:"/static/images/milktea.png"},
        {title:"火锅",image:"/static/images/hotpot.png"}
      ],
      top:[
        {name:"Das Burger House德堡屋",address:"武昌区公正路铁建1818中心地下一楼",image:"/static/images/DasBurger.jpg",remark:"招牌德堡、比利时脆炸薯条"},
        {name:"海底捞火锅",address:"武昌区徐东大街120号群星城4层SL4-6",image:"/static/images/hdl.jpg",remark:"整体服务很细致，女士周内提供美甲服务"},
        {name:"酒拾烤肉",address:"武昌区友谊大道三角花园王家湾小区湖北大学地铁A口",image:"/static/images/bbq1.png",remark:"鱼丸外焦里嫩、酱油炒饭超香！"},
        {name:"KOI",address:"武昌区中北路武汉中央文化区楚河汉街室内步行街3F层Q2-1号商铺",image:"/static/images/koi.jpg",remark:"伯爵奶茶中伯爵茶的清新与奶茶搭配的刚刚好！"}
      ],
      imgUrls:[
          "/static/images/tophotpot.jpg",
          "/static/images/topmilktea.jpg",
          "/static/images/topburger.jpg",
          "/static/images/topbbq.jpg"
   ],
      indicatorDots: true,
      autoplay: true,
      interval: 5000,
      duration: 1000
    }
  },

   methods: {
    goType(type){
      console.log(type)
      let url = '../list/main?type=' + type.title
      mpvue.navigateTo({ url })
    }
  },

  created () {
  }
}
</script>

<style scoped>
div >>> .no-border{
  border-width:0pt;
}
div >>> .split{
  margin-bottom:10pt;
}
</style>
