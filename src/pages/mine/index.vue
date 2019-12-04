<template>
  <div>
    <view class="userinfo">
    <view class="userinfo-avatar">
    <open-data type="userAvatarUrl"></open-data>
    </view>
    <open-data type="userNickName"></open-data>
    </view>
    <i-panel title="吐槽星人来安利啦ヾ(◍°∇°◍)ﾉﾞ">
      <i-input :value="name" @change="changeName($event)" title="店铺名称" autofocus placeholder="请输入店铺的名称伐！" maxlength="20" />
      <i-input :value="address" @change="changeAddress($event)" title="详细地址" placeholder="请输入详细地址以防其他人找不到踩雷吼！" maxlength="30" />
      <i-input :value="remark" @change="changeRemark($event)" title="安利理由" placeholder="请输入安利理由嗷！" maxlength="50" />
    </i-panel>
    <i-button @click="handleClick" type="warning" size="default">我要安利</i-button>
    <view class="tips">武汉的小仙女们有好吃的店铺快来拔草叭！(*/ω＼*)</view>
  </div>
</template>
<script>
export default {
  data () {
    return {
      name:"",
      address:"",
      remark:""
    }
  },

  methods: {
    changeName (event) {
      this.name = event.mp.detail.detail.value
    },
    changeRemark (event) {
      this.remark = event.mp.detail.detail.value
    },
    changeAddress (event) {
      this.address = event.mp.detail.detail.value
    },
    handleClick () {
      if (this.name && this.remark && this.address) {
        wx.showToast({
          title: '推荐了' + this.name,
          icon: 'success',
          duration: 2000
        })
        // TODO:将推荐数据提交到云数据库
      } else {
        wx.showToast({
          title: '信息不完整',
          icon: 'none',
          duration: 2000
        })
      }
    }
  },
  created () {
  }
}
</script>



<style scoped>
.userinfo {
  position: relative;
  width: 750rpx;
  height: 320rpx;
  color: #666;
  display: flex;
  flex-direction: column;
  align-items: center;
}

 

.userinfo-avatar {
  overflow:hidden;
  display: block;
  width: 160rpx;
  height: 160rpx;
  margin: 20rpx;
  margin-top: 50rpx;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 3px 3px 10px rgba(0, 0, 0, 0.2);
}



.tips {
  padding: 20pt;
  font-size: 10pt;
  color:rgb(211, 128, 102);
}
</style>