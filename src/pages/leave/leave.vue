<template>
  <div>
      <div class="leave-list-nav">
          <span class ="leave-list-title" >请假列表</span>
          <div class="ask-leave-button"
            @click="askForLeave"
          >
              <van-button 
                size="mini"
                type="info"
              >
              请假</van-button>
          </div>
      </div>
      <div>
          <leaveBox
            :mdata = leaveData
            @onMessageClick="gotoLeaveDetail"
            />
      </div>
  </div>
</template>

<script>
import leaveBox from '../../components/leave/leaveBox'
export default {
  components: {
    leaveBox
  },
  data () {
    return {
      leaveData: [
        {
          date: '2020-10-10',
          teacherName: '杨老师',
          reason: 'orem ipsum dolor sit amet, consectetur adipiscing elit. Aenean euismod bibendum laoreet. Proin gravida dolor sit amet lacus accumsan et viverra justo commodo. Proin sodales pulvinar tempor. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam fermentum, nulla luctus pharetra vulputate, felis tellus mollis orci, sed rhoncus sapien nunc eget odio. Lorem ipsum dolor sit a',
          state: 'pass'
        },
        {
          date: '2020-10-10',
          teacherName: '杨老师',
          reason: 'orem ipsum ',
          state: 'fail'
        },
        {
          date: '2020-10-10',
          teacherName: '杨老师',
          reason: 'orem ipsum ',
          state: 'fail'
        },
        {
          date: '2020-10-10',
          teacherName: '杨老师',
          reason: 'orem ipsum ',
          state: 'reading'
        }
      ]
    }
  },
  mounted () {
    this.init()
  },
  methods: {
    init () {
      wx.setNavigationBarTitle({
        title: '请假列表'
      })
    },
    gotoLeaveDetail (leave) {
      const {teacherName, date, reason, state} = leave
      console.log(leave.teacherName)
      this.$router.push({ path: '/pages/leaveDetail/main', query: {teacherName, date, reason, state} })
    },
    askForLeave () {
      this.$router.push({ path: '/pages/askForLeave/main', query: {} })
    }
  }
}
</script>

<style  lang="scss">
    .leave-list-nav{
        padding:30px 20px 20px;
        box-sizing: border-box;
        height: 30px;
        line-height: 30px;
        text-align: center;
        display:flex;
        align-items: center;
        justify-content: space-between;
        .leave-list-title{
            padding:0;
            font-size:22px;
        }
        .ask-leave-button{
            font-size:16px;
        }
    }
</style>