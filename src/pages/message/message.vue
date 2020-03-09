<template>
  <div>
    <SearchBar/>
  <MessageBox/>
  </div>
</template>

<script>
import SearchBar from '../../components/base/SearchBar'
import MessageBox from '../../components/base/MessageBox'
export default {
  components: {
    SearchBar,
    MessageBox
  },
  mounted () {
    wx.setNavigationBarTitle({
      title: '通知'
    })
  }
}
</script>

<style>

</style>