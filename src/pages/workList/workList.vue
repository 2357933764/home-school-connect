<template>
  <div>
      <div class="work-list-nav">
          <span class ="work-list-title" >仅显示七天内作业</span>
      </div>

      <!-- 作业列表 -->
      <div>
          <div class="table-wrapper">
            <div class="table-inner">
              <div
                class="table-box"
                v-for="(work, index) in workData"
                :key="index"
                @click=" gotoWorkDetail(work)"
              >
                <div class="work-info-wrapper">
                    <div class="work-title">{{work.title}}</div>
                    <div class="work-data">{{work.reason}}</div>
                    <div class="work-bottom">
                        <div class="work-tag-wrapper">
                          <van-tag 
                          round type="success" 
                          v-if="work.state  === 'pass'"
                          class="tag-style"
                          >通过</van-tag>
                          <van-tag 
                          round type="danger" 
                          v-if="work.state  === 'fail'"
                          class="tag-style"
                          >拒绝</van-tag>
                        </div>
                        <div class="work-other">
                          {{work.teacherName}}
                          {{work.date}}
                        </div>
                    </div>
                </div>
              </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script>

export default {
  components: {

  },
  data () {
    return {
      workData: [
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
    },
    gotoWorkDetail (work) {
      const {teacherName, date, reason, state} = work
      console.log(work.teacherName)
      this.$router.push({ path: '/pages/workDetail/main', query: {teacherName, date, reason, state} })
    }
  }
}
</script>

<style  lang="scss">
    .work-list-nav{
        padding:30px 20px 20px;
        box-sizing: border-box;
        height: 30px;
        line-height: 30px;
        text-align: center;
        display:flex;
        align-items: center;
        justify-content: left;
        .work-list-title{
            padding:0;
            font-size:22px;
        }
    }
     .table-wrapper {
      padding: 0 20px;
      box-sizing: border-box;
      .table-inner {
        .table-box {
          width:100%;
          border:1px solid #ccc;
          box-shadow: 5px 5px 10px 2px #ddd;
          border-radius:5px;
          padding:10px 20px;
          margin: 15px 0 ;
          box-sizing: border-box;
          .work-info-wrapper {
          .work-title {
            color: #222;
            font-size: 20px;
            line-height: 24px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            font-weight: 500;
            margin:10px 0;
          }

          .work-data {
            padding:0 20px;
            box-sizing: border-box;
            color: rgba(0, 0, 0, .65);
            font-size: 16px;
            line-height: 18px;
            height: 52px;
            overflow: hidden;
          }

          .work-bottom{
            margin-top:10px;
            display:flex;
            align-items: center;
            justify-content: space-between;
            .work-tag-wrapper{
              display: flex;
              align-items: center;
            }
            .work-other {
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