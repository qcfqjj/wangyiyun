<template>
  <div id="swiperTop">
    <van-swipe :autoplay="3000" lazy-render>
      <van-swipe-item v-for="image in state.images" :key="image">
        <img :src="image.pic" />
      </van-swipe-item>
    </van-swipe>
  </div>
</template>

<script>
import { reactive, onMounted } from 'vue'
import { getBanner } from '@/request/api/index.js'
export default {
  setup() {
    const state = reactive({
      images: ['https://unpkg.com/@vant/assets/apple-1.jpeg', 'https://unpkg.com/@vant/assets/apple-2.jpeg']
    })
    onMounted(async () => {
      let res = await getBanner()
      state.images = res.data.banners
    })
    return { state }
  }
}
</script>

<style lang="less" scoped>
#swiperTop {
  .van-swipe {
    width: 100%;
    height: 3rem;
    .van-swipe-item {
      padding: 0 0.2rem;
      img {
        width: 100%;
        height: 3rem;
      }
    }
    /deep/ .van-swipe__indicator--active {
      background-color: rgb(219, 130, 130);
    }
  }
}
</style>
