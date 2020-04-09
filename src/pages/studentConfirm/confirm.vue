<template>
 <div>
    <div class="confirm-form">
      <van-field
          v-model="sno"
          label="学生学号"
          auto-focus="true"
          type="text"
          placeholder="输入学生学号"
     />
     <van-field
           v-model="sname"
           label="学生姓名"
           auto-focus="true"
           type="text"
           placeholder="输入学生姓名"
      />
      <van-field
        v-model="sgender"
        auto-focus="true"
        label="学生性别"
        type="text"
        placeholder="输入学生性别"
      />
      <van-field
        v-model="code"
        auto-focus="true"
        label="认 证 码"
        type="text"
        placeholder="输入认证码"
      />
  </div>
  <div :style="{margin: '20px auto',width: '60px'}" @click="submitConfirm">
    <van-button type="info"> 发送 </van-button>
  </div>
 </div>
</template>

<script>
export default {
  data () {
    return {
      sno: '',
      sname: '',
      sgender: '',
      code: ''
    }
  },
  methods: {
    submitConfirm () {
      // 提交
    }
  }
}
</script>

<style>

</style>