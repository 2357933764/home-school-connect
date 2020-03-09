<template>
  <div>
    <Banner
      title="你有一封最新通知"
      subTitle="点击查看"
      img="../../../static/img/bg.jpg"
      @onClick="onBannerClick"
    />
    <Func
      @onClassClick="onClassClick"
      @onWorkClick="onWorkClick"
      @onLeaveClick="onLeaveClick"
      @onScoreClick="onScoreClick"
    />
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

<style scoped>

</style>
