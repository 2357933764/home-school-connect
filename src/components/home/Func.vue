<template>
  <div class="fun">
      <div class="fun-wrapper">
      <div class="fun-row">
          <div class="fun-item" @click="onClassClick">
               <div class="item" :style="{'background-color':'#E8DBA6'}"> 
                <van-icon 
                  name="notes-o"
                  color="#fff"
                  size="25px"
                />
               </div>
               <span class="fun-item-text"
               >课表</span>
          </div>
          <div class="fun-item" @click="onLeaveClick">
               <div class="item" :style="{'background-color':'#20B9cb'}"> 
                <van-icon 
                  name="coupon-o"
                  color="#fff"
                  size="25px"
                />
              </div>
               <span 
               class="fun-item-text"
               >请假</span>
          </div>
          <div class="fun-item" @click="onWorkClick">    
               <div class="item" :style="{'background-color':'#FBAFA2'}"> 
                <van-icon 
                  name="records"
                  color="#fff"
                  size="25px"
                />
              </div>
               <span class="fun-item-text" >作业</span>
          </div>
          <div class="fun-item" @click="onScoreClick" >
              <div class="item" :style="{'background-color':'#00AFA2'}"> 
                <van-icon 
                  name="bar-chart-o"
                  color="#fff"
                  size="25px"
               />
              </div>
               <span class="fun-item-text">成绩</span>
          </div>
      </div>
  </div>
  </div>
</template>

<script>
  export default {
    data () {
    },
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
    margin: 20px 0;
    padding:0 20px;
    .fun-wrapper{
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #fff;
      .fun-row {
        padding-top:5px;
        box-sizing:border-box;
        display: flex;
        align-items: center;
        flex:1;
        width:100%;
        justify-content: space-around;
        .fun-item {
            display: flex;
            justify-content: center;
            flex-direction: column;
            align-items: center;
            .item{
              text-align: center;
              display:flex;
              justify-content: center;
              align-items: center;
              width:50px;
              height: 50px;
              border-radius: 25px;
            }
            .fun-item-text{
                font-size: 16px;
            }

        }
      }
    }
  }
</style>
