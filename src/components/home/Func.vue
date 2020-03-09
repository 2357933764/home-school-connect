<template>
  <div class="fun">
      <div class="fun-wrapper">
      <div class="fun-row">
          <div class="fun-item" @click="onClassClick">
              <van-icon 
              name="notes-o"
              color="#E8DBA6"
              size="50px"
               />
               <span class="fun-item-text"
                :style="{color: '#E8DBA6'}"
               >班级课表</span>
          </div>
          <div class="fun-item" @click="onLeaveClick">
              <van-icon 
              name="coupon-o"
              color="#20B9cb"
              size="50px"
               />
               <span 
               class="fun-item-text"
               :style="{color: '#20B9cb'}"
               >请假</span>
          </div>
      </div>
      <div class="fun-row">
          <div class="fun-item" @click="onWorkClick">
              <van-icon 
              name="records"
              color="#FBAFA2"
              size="50px"
               />
               <span class="fun-item-text"
                :style="{color: '#FBAFA2'}"
               >作业</span>
          </div>
          <div class="fun-item" @click="onScoreClick">
              <van-icon 
              name="bar-chart-o"
              color="#917efc"
              size="50px"
               />
               <span class="fun-item-text"
                :style="{color: '#917efc'}"
               >成绩</span>
          </div>
      </div>
  </div>
  </div>
</template>

<script>
  export default {
    methods: {
      onClassClick () {
        this.$emit('onClassClick')
      },
      onWorkClick () {
        this.$emit('onWorkClick')
      },
      onLeaveClick () {
        this.$emit('onLeaveClick')
      },
      onScoreClick () {
        this.$emit('onScoreClick')
      }
    }
  }
</script>

<style lang="scss" scoped>
  .fun {
    margin-top: 20px;
    padding: 0 20px;
    .fun-wrapper{
      border:5px solid #000099;
      border-radius: 10px;
      box-sizing:border-box;
      padding: 0 20px;
      padding-bottom:20px;
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #fff;
      .fun-row {
        padding-top:20px;
        box-sizing:border-box;
        display: flex;
        align-items: center;
        flex:1;
        width:100%;
        justify-content: space-around;
        .fun-item {
            width:120px;
            height: 120px;
            border-radius: 10px;
            display:flex;
            display: flex;
            justify-content: center;
            flex-direction: column;
            align-items: center;
            .fun-item-text{
                font-size: 20px;
                font-weight: 500;
            }

        }
      }
    }
  }
</style>
