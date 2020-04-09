<template>
  <div class="search-table-wrapper">
    <div class="search-table-inner">
      <div
        class="search-table-message"
        v-for="(message, index) in mdata"
        :key="index"
        @click="() => onMessageClick(message)"
      >
           <div class="message-info-wrapper">
          <div class="message-title">{{message.title}}</div>
          <div class="message-data">{{message.reason}}</div>
          <div class="message-bottom">
            <div class="message-tag-wrapper">
              <van-tag 
              round type="primary" 
              v-if="message.state  === 'reading'"
              class="tag-style"
              >审批中</van-tag>
              <van-tag 
              round type="success" 
              v-if="message.state  === 'pass'"
              class="tag-style"
              >通过</van-tag>
              <van-tag 
              round type="danger" 
              v-if="message.state  === 'fail'"
              class="tag-style"
              >拒绝</van-tag>
            </div>
            <div class="message-other">
              {{message.teacherName}}
              {{message.date}}
            </div>
          </div>
            </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      mdata: {
        type: String,
        default: ''
      }
    },
    data () {
      return {
      }
    },
    methods: {
      // 跳转详情页
      onMessageClick (message) {
        this.$emit('onMessageClick', message)
      }
      // onClick (message) {
      //   this.$router.push({
      //     path: '/pages/detail/main',
      //     query: {
      //       fileName: message.fileName
      //     }
      //   })
      //   this.$emit('onClick', message)
      // }
    }
  }
</script>

<style lang="scss" scoped>
  .search-table-wrapper {
      padding: 0 20px;
      box-sizing: border-box;
      .search-table-inner {
        .search-table-message {
          width:100%;
          border:1px solid #ccc;
          box-shadow: 5px 5px 10px 2px #ddd;
          border-radius:5px;
          padding:10px 20px;
          margin: 15px 0 ;
          box-sizing: border-box;
          .message-info-wrapper {
          .message-title {
            color: #222;
            font-size: 20px;
            line-height: 24px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            font-weight: 500;
            margin:10px 0;
          }

          .message-data {
            padding:0 20px;
            box-sizing: border-box;
            color: rgba(0, 0, 0, .65);
            font-size: 16px;
            line-height: 18px;
            height: 52px;
            overflow: hidden;
          }

          .message-bottom{
            margin-top:10px;
            display:flex;
            align-items: center;
            justify-content: space-between;
            .message-tag-wrapper{
              display: flex;
              align-items: center;
            }
            .message-other {
            text-align: center;
            color: rgba(0, 0, 0, .45);
            font-size: 13px;
            line-height: 18px;
          }
          }
        }
      }
    }
  }
</style>
<style scoped>
.tag-style{
  margin-right:10px;
}
</style>
