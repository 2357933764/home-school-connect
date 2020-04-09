<template>
  <div>
    <div class="leave-reason-wrapper">
      <div class="leave-reason-title">
        <span :style="{color: '#f00'}">*</span>
        请假理由
      </div>
      <div class="leave-reason-box">
        <van-field
          v-model="reason"
          border=false
          auto-focus="true"
          type="textarea"
          autosize
          maxlength=200
          show-word-limit
          placeholder="请输入请假理由"
        />
      </div>
    </div>
      <div class="leave-for-teacher">
        <div class="leave-for-title">
          <span :style="{color: '#f00'}">*</span>
          老师
        </div>
        <div class="leave-teacher-box">
            <van-field
              v-model="teacher"
              auto-focus="true"
              border="false"
              type="text"
              placeholder="班主任"
            />
        </div>
      </div>
      <div class="upload" @click="uploadMore">
        上传文件
      </div>
      <div class=“button”
        
      >
        <van-button
        @click="handleSubmit"
          size="small"
          type="info"
        >
          发送
        </van-button>
      </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      reason: 'jfhirh还会反复若非和任何个人和骨骼和他回过头合法化合法化人',
      teacher: '杨老师'
    }
  },
  methods: {
    handleSubmit () {
      // eslint-disable-next-line eqeqeq
      if (this.teacher == '' || this.reason == '') {
        console.log('请完善必填项目')
      }
      console.log(this.reason)
    },
    uploadMore () {
      console.log('上传附件')
    }
  }

}
</script>

<style lang="scss">
 .leave-reason-wrapper{
   padding:30px 20px 0px;
   box-sizing: border-box;
   .leave-reason-title{
     font-size:16px;
     color:#333;
     margin:10px 0;
   }
   .leave-reason-box{
     height: 150px;
     width: 100%;
     border:1px solid #ccc;
     border-radius: 5px;
     overflow:scroll;
     color:#888;
   }
   
 }
 .leave-for-teacher{
   padding:20px 20px 0px;
   box-sizing: border-box;
   .leave-for-title{
     margin:10px 0;
     font-size:16px;
     color:#333;
   }
   .leave-teacher-box{
     
     font-size: 16px;
     color:#888;
     width: 100%;
     border:1px solid #ccc;
     border-radius: 5px;
     overflow: hidden;
   }
 }
 .upload{
   margin-left: 20px;
   padding-left:10px;
   box-sizing: border-box;
   width:86px;
   margin-top:15px;
   border:1px solid #ccc;
   border-radius: 5px;
   height: 30px;
   line-height: 30px;
   font-size: 16px;
   text-align: left;
   color:#888;
 }
 .button{
   font-size:16px;
   margin-left:20px;
   margin-top:20px;
 }

</style>