<template>
  <div>
      <UserInfo/>
      <div class="setting-box">
        <div class="setting-wrapper">
        <div 
          class="setting-item-wrapper"
          @click="goToConfirm"
        >
          <div class="item-left">
            <van-icon 
              name="manager-o"
              color="#4585ff"
            ></van-icon>
            <div class="item-text">班级认证</div>
          </div>
          <van-icon name="arrow" color="#4585ff"></van-icon>
        </div>
        <div class="setting-item-wrapper">
          <div class="item-left">
            <van-icon 
            name="setting-o"
            color="#4585ff"
            ></van-icon>
            <div class="item-text">通用设置</div>
          </div>
          <van-icon name="arrow" color="#4585ff"></van-icon>
        </div>
        <div class="setting-item-wrapper">
          <div class="item-left">
            <van-icon 
              name="warning-o"
              color="#4585ff"
            ></van-icon>
            <div class="item-text">关于我们</div>
          </div>
          <van-icon name="arrow" color="#4585ff"></van-icon>
        </div>
      </div>
      </div>
  </div>
</template>

<script>
import UserInfo from '../../components/user/UserInfo'
export default {
  components: {
    UserInfo
  },
  mounted () {
    this.init()
  },
  methods: {
    init () {
    },
    goToConfirm () {
      this.$router.push({path: '/pages/studentConfirm/main', query: {}})
    }
  }
}
</script>

<style lang="scss">
  .setting-box{
    width:100%;
    display: flex;
    justify-content: center;
    .setting-wrapper{
    width:90%;
    
    box-sizing: border-box;
      padding:5px;
    .setting-item-wrapper{
      width:100%;
      margin:8px 0;
      border-radius: 5px;
      border:1px solid #eee;
      box-shadow:5px 5px 5px 2px #ddd;
      display:flex;
      align-items: center;
      justify-content: space-between;
      box-sizing: border-box;
      padding: 10px;
      .item-left{
        display: flex;
        align-items: center;
        .item-text {
          font-size:16px;
          font-weight: 300;
          color:#666;
          margin-left: 5px;
        }
      }
    }
  }
  }

</style>