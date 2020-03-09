<template>
  <div>
      <UserInfo/>
      <div class="setting-box">
        <div class="setting-wrapper">
        <div class="setting-item-wrapper">
          <div class="item-left">
            <van-icon 
              name="manager-o"
              color="#30D9C4"
            ></van-icon>
            <div class="item-text">班级认证</div>
          </div>
          <van-icon name="arrow" color="#30D9C4"></van-icon>
        </div>
        <div class="setting-item-wrapper">
          <div class="item-left">
            <van-icon 
            name="setting-o"
            color="#30D9C4"
            ></van-icon>
            <div class="item-text">通用设置</div>
          </div>
          <van-icon name="arrow" color="#30D9C4"></van-icon>
        </div>
        <div class="setting-item-wrapper">
          <div class="item-left">
            <van-icon 
              name="warning-o"
              color="#30D9C4"
            ></van-icon>
            <div class="item-text">关于我们</div>
          </div>
          <van-icon name="arrow" color="#30D9C4"></van-icon>
        </div>
      </div>
      </div>
  </div>
</template>

<script>
import UserInfo from '../../components/base/UserInfo'
export default {
  components: {
    UserInfo
  }
}
</script>

<style lang="scss">
  .setting-box{
    width:100%;
    margin-top:20px;
    display: flex;
    justify-content: center;
    .setting-wrapper{
    width:90%;
     border: 3px solid #30D9C4;
    border-radius: 10px;
    box-sizing: border-box;
      padding:5px;
    .setting-item-wrapper{
      width:100%;
      display:flex;
      align-items: center;
      justify-content: space-between;
      box-sizing: border-box;
      padding: 10px;
      .item-left{
        display: flex;
        align-items: center;
        .item-text {
          font-size:20px;
          font-weight: 300;
          color:#666;
          margin-left: 5px;
        }
      }
    }
  }
  }

</style>