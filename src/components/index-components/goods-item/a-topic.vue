<template>
    <view class="nav a-section a-topic">
      <view class="b">
        <scroll-view scroll-x="true" class="list">
          <view class="item" v-for="item of content.goodslist" :key="item.item_id">
            <navigator  @click="toDetail(item)" class="nav">
              <img class="img" :src="baseUrl+ item.pic" background-size="cover" />
              <view class="np">
                <text class="name">{{item.title}}</text>
               <text class="price">￥{{item.price}}</text>   
              </view>
            </navigator>
          </view>
        </scroll-view>
      </view>  
    </view>
</template>
<script>
export default {
    name: 'a-topic',
    props: {
        content: Object
    },
    computed: {
        baseUrl() {
            return this.$wx.baseUrl
        }
    },
    methods: {
      toDetail(item) {
        this.$emit('onClick' , item);
      }
    }
}
</script>
<style scoped>
.a-topic .b {
  height: 378rpx;
  width: 750rpx;
  padding: 0;
  background-color: #fff;
  margin-bottom: 20rpx;
}

.clear:after{
    display: block;
    content:'';
    clear: both;
    height:0;
    }
.a-topic .b .list {
  height: 378rpx;
  width: 750rpx;
  white-space: nowrap;
}
.a-topic .b .item {
  display: inline-block;
  height: 378rpx;
  width: 280rpx;
  margin-left: 20rpx;
  overflow: hidden;
  background-color: #fff;
  border-radius: 5rpx;
}
.a-topic .b .item:last-child {
  margin-right: 20rpx;
}

.a-topic .b .img {
  height: 280rpx;
  width: 280rpx;
  display: block;
  overflow: hidden;
  background-color: #666666;
}

.a-topic .b .np {
  height: 98rpx;
  color: #333;
  font-size: 30rpx;
  padding: 10rpx 10rpx 20rpx 10rpx;
  box-sizing: border-box;
}
.a-topic .b .np .name {
  display: block;
  height: 30rpx;
  line-height: 30rpx;
  font-size: 24rpx;
  color: #282828;
  width: 270rpx;
  overflow: hidden;
  white-space: nowrap;
  text-overflow:ellipsis;

}
.a-topic .item .np .price{
  display: block;
  height: 40rpx;
  line-height: 40rpx;
  font-size: 24rpx;
  color: #dc2121;
}
</style>


