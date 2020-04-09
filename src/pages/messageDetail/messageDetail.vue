<template>
  <div class="detail-all-wrapper">
    <div class="detail-title">
      {{message.title}}
    </div>
    <div class="detail-other-wrapper">
      <span 
      class = "the-top"
      v-show= "message.orderfirst === 'true'">
      置顶
      </span>
      <span class="the-right">
        <span class="type">
        {{message.type}}
      </span>
      <span class="date">
        {{message.date}}
      </span>
      </span>
    </div>
    <div class="detail-data">
      {{message.data}}
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      id: '',
      message: {}
    }
  },
  mounted () {
    this.init()
  },
  methods: {
    init () {
      wx.setNavigationBarTitle({
        title: '通知详情'
      })
      const {id, date, type, read, title, data, orderfirst} = this.$route.query
      this.message = {id, date, type, read, title, data, orderfirst}
      console.log('message', this.message.title)
      // const openId = getStorageSync('openId')
      // const vue = this
      // getDetailData(openId, fileName).then(response => {
      //   this.book = response.data.data
      //   this.readerNum = this.book.readerNum
      //   this.readers = this.book.readers
      //   this.rankAvg = this.book.rankAvg
      //   this.rankNum = this.book.rankNum
      //   this.rateValue = this.book.rank
      //   if (openId) {
      //     getShelf(openId, this.book.fileName).then(response => {
      //       const data = response.data.data
      //       if (data.length === 0) {
      //         this.isInShelf = false
      //       } else {
      //         this.isInShelf = true
      //       }
      //     })
      //   }
      //   vue.$nextTick(() => {
      //     vue.loading = false
      //   })
      // })
      // getDetailContents(fileName).then(response => {
      //   this.contents = response.data.data
      // })
    }
  }
}
</script>

<style lang="scss">
.detail-all-wrapper{
  width:100%;
  background-color: #fff;
  padding:10px;
  box-sizing:border-box;
    .detail-title{
      font-size: 20px;
      font-weight:700;
      text-align: center;
      display:flex;
      padding:10px 20px;
      justify-content: center;
    }
    .detail-other-wrapper{
      margin: 0 auto;
      width:80%;
      padding:0 10px;
      box-sizing: border-box;
      font-size:16px;
      height:20px;
      line-height:20px;
      position: relative;
      .the-top{
        background-color: #4585ff;
        border-radius: 10px;
        color:#fff;
        font-size:14px;
        padding:2px 12px;
        position: absolute;
        left:0;
      }
      .the-right{
        color:#bbb;
        position: absolute;
        right:0;
      }
    }
    .detail-data{
      margin:20px auto;
      width: 90%;
      font-size: 18px;
      text-indent: 2em;
    }
}
</style>