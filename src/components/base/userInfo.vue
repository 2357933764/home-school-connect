<template>
  <div class="user-info-wrapper">
      <div class="user-info">
          <div class="user-avatar">
              <ImageView
              round
              height="100%"
              mode="scaleToFill"
              src="https://www.youbaobao.xyz/book/img/loading2.ae9e5924.jpeg"
              />
          </div>
          <div class="info-wrapper">
              <div class="nickname">{{userInfo.nickname}}</div>
              <div class="id">{{userInfo.id}}</div>
          </div>
      </div>
  </div>
</template>

<script>
import ImageView from './ImageView'
export default {
  components: {
    ImageView
  },
  data () {
    return {
      userInfo: {
        nickname: '花花',
        id: '123456789'
      }
    }
  }
}
</script>

<style lang="scss">
    .user-info-wrapper{
      margin-top:20px;
        width:100%;
        display:flex;
        justify-content: center;
        .user-info{
            width:90%;
            box-sizing: border-box;
            padding: 10px 20px;
            border-radius: 10px;
            border: 3px solid #30D9C4;
            display: flex;
            align-items:center;
            .user-avatar{
                width: 100px;
                height: 100px;
                overflow: hidden;
            }
            .info-wrapper{
                margin-left:20px;
                display: flex;
                flex-direction: column;
                .nickname{
                    font-size:24px;
                    color:#000;
                    margin:8px 0;
                }
                .id{
                     font-size:16px;
                    color:#666
                }
            }
        }
    }
</style>