<template>
  <div>
    <SearchBar/>
    <router-view class="router-views"/>
    <div>
    </div>
  </div>
</template>

<script>
// import Footer from '../../components/home/footer'
import SearchBar from '../../components/base/SearchBar'
export default {
  components: {
    // Footer,
    SearchBar
  }
}
</script>

<style scoped>

</style>
