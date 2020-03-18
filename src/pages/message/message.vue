<template>
  <div>
      <div class="read-select-nav">
        <div class="read-select-text">
          只显示未读消息{{read}}
        </div>
        <div class="read-select-radio">
          <van-switch :value="checked"
          size="18px"
          @change="onChangeRead($event)" />
       </div>
      </div>
    <div >
      <van-tabs sticky color="#4585ff" @change="onChangeDesc($event)">
        <van-tab title="校内通知">
        </van-tab>
        <van-tab title="班级通知" ></van-tab>
      </van-tabs>
    </div>
    <MessageBox/>
  
  </div>
</template>

<script>
import SearchBar from '../../components/base/SearchBar'
import MessageBox from '../../components/base/MessageBox'
export default {
  data () {
    return {
      type: '',
      read: false,
      checked: false
    }
  },
  components: {
    SearchBar,
    MessageBox
  },
  mounted () {
    wx.setNavigationBarTitle({
      title: '通知'
    })
  },
  methods: {
    onChangeDesc (event) { // 获取表单组件filed的值
      console.log(event.mp.detail.title) // 注意加入mp
      if (event.mp.detail.title === '校内通知') {
        this.type = 'school'
      } else {
        this.type = 'class'
      }
    },
    onChangeRead (event) {
      this.checked = !this.checked
      // read=false  表示只看未读
      this.read = !this.checked
      // 如果read 为真，表示显示所有的通知
      if (this.read) {
        // 获取全部
      } else {
        // 只看未读
      }
    }
  }
}
</script>

<style lang="scss">
  .read-select-nav{
    margin:10px 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding:5px 20px;
    box-sizing: border-box;
    display:flex;
    justify-content: space-between;
    align-items: center;
    line-height: 36px;
    .read-select-text{
      font-size:16px;
      line-height:36px;
    }
    .read-select-radio{
      height: 21px;
      line-height: 21px;
      align-items: center;
      display:flex;
    }
  }
</style>