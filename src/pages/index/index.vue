<template>
  <div>
    <div :style="{marginTop: '23px'}">
      <Banner
      title="你有一封最新通知"
      subTitle="点击查看"
      img="../../../static/img/bg.jpg"
      @onClick="onBannerClick"
    />
    </div>
    <Func/>
  </div>
</template>

<script>
import Banner from '../../components/home/Banner'
import Func from '../../components/home/Func'
import SearchBar from '../../components/base/SearchBar'
export default {
  components: {
    // Footer,
    SearchBar,
    Banner,
    Func
  },
  methods: {
    onClassClick () {
      // 跳转页面
    },
    onLeaveClick () {
      // 跳转页面
    },
    onWorkClick () {
      // 跳转
    },
    onScoreClick () {
      // 跳转
    },
    onBannerClick () {
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
